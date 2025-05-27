# Monoswap Core (MonoXSolidity)

## About

**MonoXSolidity** (Monoswap Core) is the Solidity implementation of the MonoX protocol—a decentralized exchange (DEX) platform designed for efficient single-token liquidity pools. By leveraging a unique design, Monoswap enables users to list new tokens, add/remove liquidity, and swap tokens with optimized capital efficiency and minimal transaction costs. MonoX aims to make DeFi more accessible by simplifying the process of providing liquidity and conducting swaps, with a focus on ERC-20 tokens and Ethereum-compatible networks.

- **Single-Sided Liquidity Pools:** Unlike traditional AMMs, Monoswap allows liquidity providers to add liquidity with just one token, rather than requiring a pair.
- **Capital Efficiency:** The protocol is built to maximize the efficiency of liquidity allocation.
- **Cross-Chain Deployment:** Supports multiple EVM-compatible chains (Ethereum, Polygon, Avalanche, etc.).
- **Upgradeable Architecture:** Uses OpenZeppelin upgrades for safe contract upgrades.
- **Robust Admin Controls:** Set pool admins, whitelist addresses, and manage pool status (official/unofficial).

---

## Features

- **List New Tokens:** Easily create new pools for ERC-20 tokens.
- **Add/Remove Liquidity:** Flexible liquidity management, including ETH and ERC-20 assets.
- **Token Swaps:** Swap between ERC-20 tokens using the Monoswap router.
- **Admin/Pool Management:** Set official pools, manage whitelists, and pool parameters via Hardhat tasks.
- **Test Coverage:** Includes comprehensive Hardhat/Chai test suite for core contract functionality.

---

## Usage

### How to List a New Token

To list a new token, interact with the MonoXPool contract and create a new pool by specifying the token address.

### How to Add Liquidity

Approve the token for the contract, then call:

```javascript
function addLiquidity(address _token, uint256 _amount, address to)
```

For ETH liquidity, use:

```javascript
function addLiquidityETH(address to)
```

### How to Remove Liquidity

Call the remove liquidity function for ERC-20 tokens:

```javascript
function removeLiquidity(address _token, uint256 liquidity, address to, uint256 minVcashOut, uint256 minTokenOut)
```

Or for ETH liquidity:

```javascript
function removeLiquidityETH(address to)
```

### How to Swap Tokens

Use the MonoswapRouter contract to swap between supported tokens.

---

## Deployment

The contracts can be deployed to various EVM networks via Hardhat. Example deployment script can be found in `scripts/deploy-monoswap.js`.

```bash
npx hardhat run scripts/deploy-monoswap.js --network <network_name>
```
Networks supported include Ethereum mainnet, Goerli, Rinkeby, Polygon, Mumbai, and Avalanche.

---

## License

Business Source License 1.1 (BSL-1.1)  
See [LICENSE](LICENSE) for details.  
Licensor: Qntism Foundation Ltd.

---

## Contributing

Pull requests and issues are welcome!

---

## About Section (for GitHub "About" field)

> Decentralized exchange core contracts for MonoX—enabling single-sided liquidity pools, efficient token swaps, and multi-chain support. Powered by Solidity and Hardhat. BSL 1.1 License.
