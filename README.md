# Checks Smart Contract

This Solidity smart contract is designed to manage Ether transfers with specific limits and balance checks. It includes functions to get the balance of an address, change a transfer limit, and transfer Ether with constraints.

## Contract Overview

The `Checks` contract provides the following functionalities:
- Get the balance of a specified address in Ether.
- Change the Ether transfer limit (with an assertion to prevent exceeding the limit).
- Transfer Ether to a specified address with constraints on the minimum and maximum transfer amounts.

## Functions

### getBalance(address _address) public view returns (uint256)

This function returns the balance of the given address in Ether.

**Parameters:**
- `_address`: The address whose balance you want to check.

**Returns:**
- The balance of the specified address in Ether.

### changeLimit(uint newLimit) public

This function allows changing the transfer limit, ensuring it does not exceed 10 Ether.

**Parameters:**
- `newLimit`: The new transfer limit in Ether.

**Reverts:**
- If the new limit is greater than 10 Ether.

### transfer(address payable _receiver) public payable

This function transfers Ether to the specified receiver address, ensuring the transfer amount is within the specified limits.

**Parameters:**
- `_receiver`: The address to which Ether will be transferred.

**Requires:**
- At least 1 Ether to be sent.

**Reverts:**
- If the transfer amount exceeds the specified limit.

## Custom Error

### SingleTransferLimit

This custom error is used to revert the transaction if the transfer amount exceeds the specified limit.

**Parameters:**
- `message`: The error message.
- `limit`: The maximum transfer limit.

## Usage

1. **Deploy the Contract:**
   Deploy the `Checks` contract on the Ethereum network.

2. **Get Balance:**
   Call the `getBalance` function with an address to check its Ether balance.

3. **Change Limit:**
   Use the `changeLimit` function to set a new transfer limit (must be 10 Ether or less).

4. **Transfer Ether:**
   Use the `transfer` function to send Ether to a specified address, ensuring the amount is at least 1 Ether and does not exceed the limit.
