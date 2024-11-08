# MyToken Smart Contract
This repository contains a basic ERC20-like smart contract named MyToken. This contract defines a token called META with minting and burning functionality, designed for simplicity and easy integration in Ethereum-based projects.

## Table of Contents
Overview
Description
Public Variables
Mappings
Functions
Getting Started
License
### Overview
MyToken is a smart contract that implements an ERC20-like token named META, with the token abbreviation META. This contract provides functionality to mint new tokens, increasing the balance of specified addresses, and to burn tokens, reducing the balance and total supply. It also keeps track of the token balance for each address.

## Description
The MyToken contract is a straightforward Solidity program, ideal for developers seeking to understand or integrate basic tokenomics into their Ethereum projects. It includes:

Minting: Increase the supply of tokens.
Burning: Decrease the supply of tokens, ensuring sufficient balance.
Balance Tracking: Maintain accurate balances for each account.
## Public Variables
string public tokenName — Stores the name of the token, which is set to "META".
string public tokenAbbrev — Stores the abbreviation of the token, which is set to "META".
uint public totalSupply — Tracks the total supply of META tokens in circulation.
## Mappings
mapping(address => uint) public balances — Maps each address to its respective balance of META tokens.
## Functions
mint(address _address, uint _value)
Increases the total supply of tokens by _value and updates the balance of _address by the same amount.

Parameters:
_address: The address that will receive the minted tokens.
_value: The number of tokens to mint.
burn(address _address, uint _value)
Decreases the total supply of tokens by _value and reduces the balance of _address by the same amount. This function checks that _address has a sufficient balance before burning tokens.

Parameters:
_address: The address whose tokens will be burned.
_value: The number of tokens to burn.
## Getting Started
Prerequisites
Remix IDE: Use Remix for easy testing and deployment of this contract.
Solidity Compiler: Version 0.8.0 or higher is recommended.
Steps to Deploy
Open Remix and create a new file named MyToken.sol.
Copy and Paste the contract code:
solidity
code :
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyToken {
    string public tokenName = "META";
    string public tokenAbbrev = "META";
    uint public totalSupply;

    mapping(address => uint) public balances;

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
Compile the contract using the Solidity compiler.
Deploy the contract and use the mint and burn functions to manage token balances.
## License
This project is licensed under the MIT License. See the LICENSE file for details.

This README provides a clear, structured, and beginner-friendly guide to understanding and using the MyToken smart contract.
