# UNISWAP-DEFI

The Liquidity Examples Solidity smart contract provides various functions to interact with the Uniswap V3 liquidity pool. It allows users to create, manage, and collect fees from liquidity positions in the pool. The contract uses the Uniswap V3 core and periphery contracts, as well as OpenZeppelin ERC721 receiver interface for NFT handling.

## Contract Details

- **License**: GPL-2.0-or-later
- **Solidity Version Compatibility**: >=0.7.6 < 0.9.0
- **Abi Coder Version**: 2

## State Variables

- `DAI` (address): The address of the DAI token.
- `USDC` (address): The address of the USDC token.
- `poolFee` (uint24): The pool fee represented as a percentage (0.01% in this case).
- `nonfungiblePositionManager` (INonfungiblePositionManager): The Uniswap V3 nonfungible position manager contract used to interact with liquidity positions.
- `tokenId` (uint): The token ID used in this example.

## Struct

- `Deposit`: Represents the deposit of an NFT. It contains the following fields:
  - `owner` (address): The address of the owner of the NFT.
  - `liquidity` (uint128): The liquidity amount of the NFT.
  - `token0` (address): The address of token0 in the liquidity position.
  - `token1` (address): The address of token1 in the liquidity position.

## Functions

1. `onERC721Received`: Implements the ERC721 receiver interface to receive custody of ERC721 tokens. It creates a deposit for the received NFT.

2. `_createDeposit`: Internal function to create a deposit for an NFT. It stores the NFT's details in the `deposits` mapping.

3. `mintNewPosition`: Creates a new liquidity position by minting NFTs representing liquidity in the Uniswap V3 pool.

4. `collectAllFees`: Collects all fees earned from the liquidity position represented by the specified token ID.

5. `increaseLiquidityCurrentRange`: Increases liquidity in the current tick range for the liquidity position represented by the specified token ID.

6. `getLiquidity`: Returns the liquidity amount for the specified token ID.

7. `decreaseLiquidity`: Decreases liquidity for the liquidity position represented by the specified token ID.

## Note

This documentation provides an overview of the Liquidity Examples smart contract and its functionalities. Before deploying or interacting with any smart contract, it is crucial to conduct a thorough code review, audit the contract's security, and understand the implications of each function. The contract uses the Uniswap V3 core and periphery contracts, and it references the DAI and USDC tokens, which should be properly verified for use.
