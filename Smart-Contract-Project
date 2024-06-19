// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Checks {
    // Limit in Ether
    uint public limit = 10;

    // Function to get the balance of an address in Ether
    function getBalance(address _address) public view returns (uint256) {
        return _address.balance / 1 ether;
    }

    // Function to change the limit
    function changeLimit(uint newLimit) public {
        // This should assert that newLimit is less than or equal to 10
        assert(newLimit <= 10);
        limit = newLimit;
    }

    // Custom error for exceeding single transfer limit
    error SingleTransferLimit(string message, uint limit);

    function transfer(address payable _receiver) public payable {

        // Require at least 1 Ether to be sent
        require(msg.value >= 1 ether, "At least 1 ether should be sent");

        // Check if the sent amount exceeds the limit and revert if true
        if (msg.value > limit * 1 ether) {
            revert SingleTransferLimit("Single Transfer Limit Exceeded!", limit);
        }

        // Transfer the sent amount to the receiver
        _receiver.transfer(msg.value);
    }
}
