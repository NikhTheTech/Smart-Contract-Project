# SimpleContract

## Overview

`SimpleContract` is a basic smart contract that demonstrates the use of Solidity's `require()`, `assert()`, and `revert()` statements. The contract allows an owner to set, increment, and reset a value with basic validation checks.

## Features

- **Ownership:** Only the contract owner can modify the state.
- **Value Management:** Set, increment, and reset a stored value with safety checks.

## Functions

- `setValue(uint256 _value)`: Sets the value to `_value` if `_value` is greater than zero.
- `incrementValue()`: Increments the value by 1 if the value is greater than zero.
- `resetValue()`: Resets the value to zero if it is not already zero.

## Usage

1. Deploy the contract.
2. Only the contract owner can call the functions to modify the state.
3. Use `setValue`, `incrementValue`, and `resetValue` functions as needed.

## Development

1. Clone the repository.
2. Install Solidity development environment (e.g., Remix, Truffle).
3. Deploy and interact with the contract.

