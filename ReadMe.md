# FreeMintToken Contract

**Contract Address:** [To be deployed]  
**Author:** [@Manish](https://github.com/manish2889)  
**License:** MIT

## Overview

`FreeMintToken` is an ERC-721A smart contract that allows users to mint NFTs for free. This contract is optimized for gas efficiency, making it cost-effective for both the user and the network. The contract is designed with the following features:

- **User Limit:** Each address can mint up to 10 tokens.
- **Max Supply:** A maximum of 10,000 tokens can be minted in total.
- **Base URI:** Metadata is stored off-chain and referenced via IPFS.

## Key Features

- **Free Minting:** Users can mint tokens without any cost, subject to the supply and user limitations.
- **Gas Efficient:** Built using ERC-721A, which is optimized for batch minting to save on gas fees.
- **Supply Constraints:** The contract ensures that no more than the maximum supply can be minted, and individual user limits are strictly enforced.

## Functions

### 1. `mint(uint256 quantity)`

- **Description:** Allows users to mint a specified number of tokens.
- **Parameters:**
  - `quantity`: The number of tokens to mint.
- **Requirements:**
  - The total minted tokens must not exceed the `MAX_SUPPLY`.
  - The user's total minted tokens must not exceed the `USER_LIMIT` of 10 tokens.
  - An allowlist verification can be added here for access control (commented in the code).
- **Access:** Only callable by external addresses (EOA).

### 2. `_baseURI()`

- **Description:** Returns the base URI used to retrieve metadata for the tokens.
- **Returns:** A string representing the base URI for the metadata stored on IPFS.

## Usage

1. **Deploy the Contract:** Use a tool like Remix, Hardhat, or Truffle to deploy the `FreeMintToken` contract to your desired network.
2. **Mint Tokens:** Call the `mint` function with the desired quantity, adhering to the `USER_LIMIT` and `MAX_SUPPLY` constraints.
3. **Metadata:** The base URI points to an IPFS address where the metadata for the NFTs is stored.

## Notes

- **Allowlist Verification:** For enhanced access control, you can integrate an allowlist verification mechanism within the `mint` function. This is particularly useful for restricting minting to specific addresses during early access phases.
- **Gas Fees:** Although minting is free in terms of token cost, users will still need to pay for gas fees associated with the minting transaction.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
