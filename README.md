# Staking Smart Contract

## Overview

This repository contains a Solidity smart contract for a basic staking system with rewards. The contract allows users to stake a specified ERC-20 token and earn rewards over time. The implementation includes protection against reentrancy attacks and utilizes the OpenZeppelin library for ERC-20 token interactions, reentrancy protection, and safe mathematical operations.

## Features

- **Staking**: Users can stake a desired amount of tokens into the contract.
- **Withdrawal**: Users can withdraw their staked tokens at any time.
- **Reward Distribution**: The contract distributes rewards to stakers based on their staked token amounts and the duration of staking.
- **Reentrancy Protection**: The contract incorporates the `ReentrancyGuard` to prevent reentrancy attacks.
- **ERC-20 Interaction**: The contract interacts with ERC-20 tokens for staking and reward distribution.

## Getting Started

### Prerequisites

- Install a Solidity compiler compatible with version 0.8.2.
- Ensure access to an Ethereum development environment for deployment and testing.

### Deployment

1. Deploy the contract to your Ethereum development environment.
2. Initialize the contract with the addresses of the staking and reward tokens.

### Usage

1. **Stake Tokens**: Users can stake tokens using the `stake` function, specifying the amount to stake.
2. **Withdraw Staked Tokens**: Users can withdraw their staked tokens using the `withdrawStakedTokens` function.
3. **Claim Rewards**: Users can claim their earned rewards using the `getReward` function.

## Contract Details

### State Variables

- `s_stakingToken`: ERC-20 token used for staking.
- `s_rewardToken`: ERC-20 token used for reward distribution.
- `REWARD_RATE`: Rate at which rewards are distributed per second.
- `totalStakedTokens`: Total amount of staked tokens across all users.
- `rewardPerTokenStored`: Stored reward per token calculation.
- `lastUpdateTime`: Timestamp of the last contract update.
- `stakedBalance`: Mapping of user addresses to their staked token balances.
- `rewards`: Mapping of user addresses to their accumulated rewards.
- `userRewardPerTokenPaid`: Mapping of user addresses to the last stored reward per token paid to them.

### Functions

- `stake(uint amount)`: Allows users to stake tokens.
- `withdrawStakedTokens(uint amount)`: Allows users to withdraw staked tokens.
- `getReward()`: Allows users to claim their rewards.

### Events

- `Staked(address indexed user, uint256 indexed amount)`: Triggered when a user stakes tokens.
- `Withdrawn(address indexed user, uint256 indexed amount)`: Triggered when a user withdraws staked tokens.
- `RewardsClaimed(address indexed user, uint256 indexed amount)`: Triggered when a user claims rewards.

## License

This smart contract is licensed under the GNU General Public License version 3.0 (GPL-3.0). See the `LICENSE` file for more details.

## Disclaimer

This smart contract is provided as-is and may be subject to further improvements or modifications. Use it at your own risk, and thoroughly test in a safe environment before deploying on the mainnet.
