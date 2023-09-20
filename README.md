# Metacrafter_project
My metacrafter project

Tokening Solidity Smart Contract
Introduction to Repository
License and Version:

The SPDX-License-Identifier specifies the MIT License for this code.
pragma solidity ^0.8.0; indicates compatibility with Solidity version 0.8.0 or higher.
Contract Declaration:

# Tokening Smart Contract

![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)

Welcome to the Tokening Smart Contract repository! This Solidity smart contract, named "Tokening," serves as a foundational example for creating custom tokens on the Ethereum blockchain. This README provides an in-depth overview of the project, detailed code explanations, deployment instructions, and insights into the advantages of using this token contract.

## Project Introduction

The Tokening smart contract is a versatile template designed to facilitate the creation and management of tokens on the Ethereum blockchain. Whether you're exploring token development, building a blockchain application, or simply learning Solidity, this contract provides a solid starting point.

## Code Explanation
Let's dive into the code for the Tokening Smart Contract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Tokening {
    string public tokenName = "Code";
    string public tokenSymbol = "Super Code";
    uint256 public totalSupply = 0;
    mapping(address => uint256) public balances;

    function mint(address _to, uint256 _value) external {
        require(_to != address(0), "Invalid address");
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(uint256 _value) external {
        require(balances[msg.sender] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[msg.sender] -= _value;
    }
}

