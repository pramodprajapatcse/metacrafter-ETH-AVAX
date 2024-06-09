=

```markdown
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

## Help

For common problems or issues, ensure you have the correct version of Solidity and Hardhat installed. If issues persist, try the following command for more information:
```bash
npx hardhat help
```

## Authors

Contributors names and contact info:

- Pramod Prajapat

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
```
