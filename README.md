# Errors and Functions
this is a simple Soldity code for error handling mechanisms. 

**Description:** This Solidity code defines a smart contract named funcanderror with functions demonstrating error handling mechanisms. It stores an owner's address and a public number. The settingnum function allows setting the number but requires it to be greater than zero using a require statement, throwing an error if not met. The assertfunc uses an assert statement for a similar check, but its failure is silent in non-debug mode. Finally, revertfunc employs an if statement and revert to throw a custom error message if the input is zero.

**Getting Started:**
1. Set Up the Environment
Make sure you have a Solidity development environment set up. You can use tools like Remix IDE (https://remix.ethereum.org/) or Truffle Suite (https://www.trufflesuite.com/) for compiling and deploying Solidity contracts.

2. Contract Compilation
Open Remix IDE: Go to https://remix.ethereum.org/.
Create a New File: Name it funcanderror.sol.

**code:**

    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.18;
    contract funcanderror {
        address public owner;
        uint public number;

    constructor() {
        owner = msg.sender;
    }

    // Function for setting a number using require
    function settingnum(uint _numb) public {
        require(_numb > 0, "Number is not greater than zero");
        number = _numb;
    }

    // Function for assert
    function assertfunc(uint y) public pure returns (uint) {
        assert(y > 0);
        return y;
    }

    // Function for revert
    function revertfunc(uint z) public pure returns (uint) {
        if (z == 0) {
            revert("Input should not be zero");
        }
        return z;
    }
    }

3. Contract Deployment

Compile the Contract:
Click on the "Solidity Compiler" tab.
Make sure the compiler version matches ^0.8.18.
Click "Compile funcanderror.sol".

Deploy the Contract:
Go to the "Deploy & run transactions" tab.
Ensure that you are connected to a suitable Ethereum network (like JavaScript VM for local testing).
Deploy the contract by clicking on the "Deploy" button.

4. Interacting with the Contract

Set number using settingnum function:
After deployment, in the "Deployed Contracts" section, find the deployed funcanderror contract instance.
Use the settingnum function to set the number variable. Enter a positive integer greater than zero and click "transact".

Test assertfunc and revertfunc:
In Remix IDE, you can call the assertfunc and revertfunc functions directly:
assertfunc: Enter a positive integer greater than zero and click "transact". This should return the same number.
revertfunc: Enter 0 as input and click "transact". This should revert with the message "Input should not be zero".

5. Verify Outputs
After each interaction, check the output in the "Transactions" section at the bottom of Remix IDE.
Confirm that the functions behave as expected:
settingnum sets number correctly when input is greater than zero.
assertfunc passes with a positive input and fails (reverts) with a non-positive input.
revertfunc reverts with a specific message when input is zero.

6. License
Ensure the SPDX license identifier MIT is present at the beginning of your Solidity file to comply with licensing requirements.
