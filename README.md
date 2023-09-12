# Token Swap

This is a simple Ethereum smart contract for creating an exchange where users can add liquidity, swap Ether for tokens, and swap tokens for Ether. The contract allows users to add liquidity to the exchange pool and swap between Ether and an ERC20 token.

## Features

- Add liquidity to the exchange.
- Swap Ether for tokens.
- Swap tokens for Ether.
- View the total supply of the ERC20 token.
- Get the address of the ERC20 token.
- Check the token and Ether reserves in the contract.

## Getting Started

### Prerequisites

- You should have an Ethereum development environment set up.
- The contract uses the OpenZeppelin ERC20 interface, so make sure you have OpenZeppelin installed in your project.

### Deployment

1. Deploy the contract to an Ethereum network, passing the address of the ERC20 token as a constructor parameter.

constructor (address _tokenAddress) {
    require(_tokenAddress != address(0), "address(0) cannot be used");
    tokenAddress = _tokenAddress;
}

## Usage

The contract provides the following functions:

- **getTotalSupplyOfToken**: Returns the total supply of the ERC20 token.

- **getTokenAddress**: Returns the address of the ERC20 token.

- **addLiquidity(uint _tokenAmount)**: Adds liquidity to the exchange by sending tokens to the contract and receiving Ether. The exchange rate is initially set to 1 Ether for 10,000 tokens.

- **changeEtherToToken()**: Swaps Ether for tokens based on the current exchange rate.

- **changeTokenToEther(uint _inputTokenAmount)**: Swaps tokens for Ether based on the current exchange rate.

- **getTokenReserve**: Returns the token reserve in the contract.

- **getEtherReserve**: Returns the Ether reserve in the contract.

- **getTokenAmount(uint _inputEthAmount, uint EthReserve, uint tokenReserve)**: Calculates the amount of tokens that will be received for a given amount of Ether.

- **getEtherAmount(uint _inputTokenAmount, uint tokenReserve, uint EthReserve)**: Calculates the amount of Ether that will be received for a given amount of tokens.

## License

This smart contract is open-source software licensed under the GPL-3.0 License.
