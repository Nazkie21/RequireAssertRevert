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

contract GuessingGame {
  uint public answer = 42; // The secret answer
  uint public attempts = 0; // Number of guesses made

  // Function for players to guess the answer
  function guess(uint _guess) public {
    attempts++;

    // Require valid guess range (1-100)
    require(_guess >= 1 && _guess <= 100, "Guess must be between 1 and 100");

    // Check guess
    if (_guess == answer) {
      // Player wins!
      // (Assuming reward logic is implemented elsewhere)
    } else {
      // Assert for unexpected internal error (should never happen)
      assert(attempts <= 10);

      // Revert transaction with a message
      revert("Incorrect guess. Try again!");
    }
  }
}



```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "RAR.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "RAR" contract from the dropdown menu, and then click on the "Deploy" button.

## Authors

Nathaniel John Quilao

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
