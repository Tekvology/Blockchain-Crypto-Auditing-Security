# Roadmap for Auditing Smart Contracts by Tekvo

## Initial Internal Security Audit
 - ### Documentation : 
   Document everything properly, because that is the starting point for auditing your code
    - Business Requirements Documentation
    - Techical Requirements Documents
    - Logic Expected & Code written for it
    - Test Cases ( Try to automate test cases ), Maintain a log of test cases executed
    - Test Results from the test net
    - Maintain versioning of each document to make sure that if any changes done in the requirements document or logic, then is your code also reflecting the same changes.
    - Code should be done strictly as per the definition or logic defined in the requirements document
 - ### Test using Auding tools
    -  https://bscheck.eu/
    - 
   ### Bug Testing
    - Is there any harmful transaction in your contract? Transaction Ordering Dependency, Stack Size limits, Integer overflow etc.
     [Refer - Type of attacks](https://github.com/Tekvology/Blockchain-Crypto-Auditing-Security/blob/main/001%20Type%20of%20Blockchain%20Attacks.md)
    - Are you using a safe Token minting process?
    - If contract is enabled for pause then make sure to test the rug pull scenerios? 
    - Is there any delegate call, proxy contract, thirdparty function call done inside the contract?
    - Is factory pattern implemented correctly? https://blog.logrocket.com/cloning-solidity-smart-contracts-factory-pattern/
    - Contract should not contain a migrator code, in 1000's of cases it resulted in rugpull. https://rugdoc.io/education/migrator/
    - Make sure that the renounce ownership function is implemented for the right reasons and correctly. https://eips.ethereum.org/EIPS/eip-173
    - Solidity does not contain a emergency withdraw code
    - The contract not used locktime function
    - There is no Liquidity remove function
    - Solidity does not contain a change strategies function
    - Make sure that burn function is not suspicious
    - Make sure that each function performs exactly the same action as expected from it.
    - Perform input validation under byzantine threat model
    - Test dependency on external contracts/libraries and oracles
   ### Tax and Gas related functions
    - No redundant call, make sure the functions are optimized for less gas utilization
    - No Honey pot: Make sure that the token is sellable
    - Make sure that you can sell and buy tokens
    - Sell and Buy tax should remain less then 5%
   ### Top holders
    - locked / burned token should be > 95%
    - top 5 to 10 holders should not have more then 5% of circulating supply
    
## Thirt Party Audit - Industry Standard