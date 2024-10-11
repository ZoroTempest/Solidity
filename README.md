# MyToken

This Solidity program is a simple token contract that demonstrates basic token functionality, including minting and burning tokens. This serves as an introductory project for those learning about Ethereum smart contracts and token standards.

## Description

This program implements a basic ERC-like token contract in Solidity. The contract features public variables for the token's name, abbreviation, and total supply. It includes a mapping to keep track of each address's balance. Users can mint new tokens or burn existing ones, allowing for dynamic supply management.

## Getting Started

### Executing the Program

To run this program, you can use Remix, an online Solidity IDE. Follow these steps:

1. Go to the Remix website: [Remix IDE](https://remix.ethereum.org/).
2. Create a new file by clicking the "+" icon in the left-hand sidebar. Save it with a `.sol` extension (e.g., MyToken.sol).
3. Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyToken {

    // Public variables
    string public tokenName = "Luffy";
    string public tokenAbbrv = "Rimuru";
    uint public totalSupply = 0;

    // Mapping variable for balances
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile MyToken.sol" button.


Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.


After the contract is deployed, you can interact with it by calling the mint function to create new tokens. Enter an address and the amount of tokens you want to mint, then click on the "transact" button to execute the function.


You can also use the burn function to destroy tokens. Enter the address and the amount you wish to burn, and then click on the "transact" button to execute this function.


# Authors
Justin Bulot

Email - 202110965@fit.edu.ph

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
