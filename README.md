# Points Token Smart Contract

## Overview

This Solidity smart contract implements the Points token, which is an ERC-20 compliant token with additional functionality. The contract is designed to be used for a token system where users can redeem and transfer tokens, and each user has a designated level based on their token holdings.

## Features

1. **ERC-20 Compliance**: The Points token adheres to the ERC-20 standard, providing basic functionality for transfer, balance inquiry, and approval.

2. **Levels System**: Users are assigned one of three levels (Level1, Level2, Level3) based on the amount of tokens they hold. The levels are determined during token redemption, with different thresholds for each level.

3. **Ownership Control**: The contract includes the `Ownable` feature from the OpenZeppelin library, ensuring that only the contract owner (deployer) has the authority to mint new tokens.

## Token Functionality

### `redeemTokens(uint256 _value)`

Allows users to redeem tokens, burning the specified amount from their balance. The user's level is then determined based on the redeemed token amount.

### `mint(address to, uint256 amount)`

Enables the owner to mint new tokens and allocate them to a specified address.

### `getBalance()`

Returns the token balance of the caller.

### `transferTokens(address _rec, uint256 _value)`

Allows users to transfer tokens to another address, provided they have a sufficient balance.

### `burnTokens(uint256 _value)`

Allows users to burn (destroy) a specified amount of their own tokens, reducing their balance.

### `getUserLevel(address user)`

Returns the level of a given user based on their token holdings.

## Installation and Dependencies

Ensure that the contract is compiled using Solidity version 0.8.9. Additionally, the contract relies on the OpenZeppelin library for ERC-20 implementation and ownership control. The following dependencies are required:

- `@openzeppelin/contracts/token/ERC20/ERC20.sol`
- `@openzeppelin/contracts/access/Ownable.sol`

## Deployment

Deploy the contract to the Ethereum blockchain, specifying the initial token name as "Degen" and symbol as "DGN." The deployer will become the owner of the contract with exclusive minting rights.

## License

This smart contract is released under the MIT License. See the [LICENSE](LICENSE) file for more details.
