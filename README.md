# ErrorHandling Smart Contract

## Overview

The `ErrorHandling` smart contract is a Solidity contract designed to demonstrate error handling using `require()`, `revert()`, and `assert()` statements. The contract contains functions to check if numbers are even or odd, and a function to verify if a number meets a specific condition. The results of these checks can be displayed using another function.

## Features

- **Require Statement**: Ensures a condition is met before executing further code.
- **Revert Statement**: Reverts the transaction with a custom error message if a condition is not met.
- **Assert Statement**: Used for internal errors to check invariants.
- **Result Display**: Provides the result of a specific check performed by the contract.

## Contract Details

### State Variables

- `bool public result`: A boolean variable to store the result of the `fun3` function. It is initialized to `false`.

### Functions

1. **fun1(uint num1) public pure returns (string memory)**:
    - Uses `require` to ensure the input number is even.
    - Returns "Number is even." if the condition is met.
    - Reverts with "Number must be even, Try! another value." if the condition is not met.

2. **fun2(uint num2) public pure returns (string memory)**:
    - Uses `revert` to ensure the input number is odd.
    - Returns "Number is odd." if the condition is met.
    - Reverts with "Number must be odd. Try another value." if the condition is not met.

3. **fun3(uint num) public**:
    - Uses `assert` to check if the input number is greater than or equal to 100.
    - Sets the `result` variable to `true` if the condition is met.
    - If the condition is not met, the transaction is reverted with an assertion error.

4. **disp() public view returns (string memory)**:
    - Returns a message based on the value of the `result` variable.
    - If `result` is `true`, returns "Number is greater than or equal to 100."
    - If `result` is `false`, returns "Number must be greater than or equal to 100."

## Deployment and Usage

### Deployment

To deploy the `ErrorHandling` contract, follow these steps:

1. Open [Remix IDE](https://remix.ethereum.org/).
2. Create a new file named `ErrorHandling.sol` and paste the contract code.
3. Compile the contract using the Solidity compiler.
4. Deploy the contract using the "Deploy & Run Transactions" panel.

### Usage

After deploying the contract, you can interact with it through the deployed contract instance in Remix.

1. **fun1(uint num1)**:
    - Call with an even number to receive "Number is even."
    - Call with an odd number to trigger the require error and receive "Number must be even, Try! another value."

2. **fun2(uint num2)**:
    - Call with an odd number to receive "Number is odd."
    - Call with an even number to trigger the revert error and receive "Number must be odd. Try another value."

3. **fun3(uint num)**:
    - Call with a number greater than or equal to 100. This sets `result` to `true`.
    - Call with a number less than 100 to trigger an assertion error.

4. **disp()**:
    - Call to see the result of the `fun3` function.
    - If `fun3` was called with a number greater than or equal to 100, returns "Number is greater than or equal to 100."
    - Otherwise, returns "Number must be greater than or equal to 100."

### Contact

For any inquiries, please contact [Tanmay Garg] at [gargtanmay32@gmail.com].
