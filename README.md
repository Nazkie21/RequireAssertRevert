# Require Assert Revert

This Solidity program is a simple "Require Assert Revert" program that demonstrates the basic syntax and functionality of the a Solidity Contract. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., RAR.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyContract {
    address public owner;
    uint256 public value;

    constructor() {
        owner = msg.sender;
    }

    function setValue(uint256 _newValue) external {
        // Require that the caller of this function is the owner
        require(msg.sender == owner, "Caller is not the owner");

        // Ensure that the new value is not zero
        require(_newValue != 0, "Value cannot be zero");

        // Ensure that the new value is greater than the current value
        require(_newValue > value, "New value must be greater than current value");

        // Update the value
        value = _newValue;
    }

    function assertExample(uint256 _x, uint256 _y) external pure returns (uint256) {
        // Ensure that _x is less than _y, otherwise trigger an assertion error
        assert(_x < _y);

        // Return the result of _y - _x
        return _y - _x;
    }

    function revertExample() external pure {
        // Revert the transaction with a custom error message
        revert("This transaction is reverted");
    }
}



```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "RAR.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "RAR" contract from the dropdown menu, and then click on the "Deploy" button.

## Authors

Nathaniel John Quilao

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
