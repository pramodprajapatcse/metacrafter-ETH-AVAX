
# Error Handler Smart Contract

This project demonstrates the use of error handling in Solidity using assert, require, and revert statements.

## Description

The `errorHandler` smart contract allows you to set an age and then check if the age is at least 21. It includes three different functions (`testAssert`, `testRequire`, and `testRevert`) to demonstrate various error handling mechanisms in Solidity. Additionally, it uses `console.log` for debugging purposes with Hardhat.

## Getting Started

### Installing

* Clone the repository:
  ```bash
  git clone https://github.com/yourusername/error-handler.git
  ```
* Navigate to the project directory:
  ```bash
  cd error-handler
  ```
* Install the necessary dependencies:
  ```bash
  npm install
  ```

### Executing program

* Compile the smart contract:
  ```bash
  npx hardhat compile
  ```
* Deploy the smart contract:
  ```bash
  npx hardhat run scripts/deploy.js --network <network-name>
  ```
* Interact with the smart contract using Hardhat Console:
  ```bash
  npx hardhat console --network <network-name>
  ```
* Example commands in the Hardhat console:
  ```javascript
  const ErrorHandler = await ethers.getContractFactory("errorHandler");
  const errorHandler = await ErrorHandler.deploy();
  await errorHandler.deployed();

  // Set age
  await errorHandler.setAge(25);

  // Test assert
  await errorHandler.testAssert();

  // Test require
  await errorHandler.testRequire();

  // Test revert
  await errorHandler.testRevert();
  ```

## Smart Contract Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

// Import Hardhat console for debugging
import "hardhat/console.sol";

// Define the contract
contract errorHandler {
    // Declare a public state variable of type uint to store the person's age
    uint public PersonAge;

    // Function to set the age, taking a uint as an argument
    function setAge(uint _age) public {
        PersonAge = _age;
    }

    // Function using assert to check if PersonAge is at least 21
    function testAssert() public view {
        assert(PersonAge >= 21);
        console.log("You are eligible to access this service.");
    }

    // Function using require to check if PersonAge is at least 21
    function testRequire() public view {
        require(PersonAge >= 21, "Access restricted to adults only");
        console.log("You are eligible to access this service.");
    }

    // Function using if-else and revert to check if PersonAge is at least 21
    function testRevert() public view {
        if (PersonAge >= 21) {
            console.log("You are eligible to access this service.");
        } else {
            revert("Access restricted to adults only");
        }
    }
}
```

## Help

For common problems or issues, ensure you have the correct version of Solidity and Hardhat installed. If issues persist, try the following command for more information:
```bash
npx hardhat help
```

## Authors

Contributors names and contact info:

- Pramod Prajapat
- instagram pramodprajapatcse

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
```
