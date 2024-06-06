# MyToken Contract

This Solidity program is a simple ERC20-like token contract that demonstrates the basic functionalities of minting and burning tokens. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to understand how to create and manage tokens on the Ethereum blockchain.

## Description

This contract is written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract defines a token with a name, abbreviation, and total supply. It allows the owner to mint new tokens, increasing the total supply and the balance of a specified address. It also allows tokens to be burned, decreasing the total supply and the balance of a specified address, with a check to ensure that the address has enough tokens to burn. This contract serves as an educational example and can be expanded for more complex token functionality.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix](https://remix.ethereum.org/).

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a `.sol` extension (e.g., `MyToken.sol`). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.7;

contract MyToken {

    // public variables here
    string public Token_Name = "META";
    string public Token_Abbv = "MTA";
    uint public Total_supply = 50; 

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint value) public {
        Total_supply += value;
        balances[_address] += value;
    }

    // burn function
    function burn(address _address, uint value) public {
        require(balances[_address] >= value, "Insufficient balance to burn");
        Total_supply -= value;
        balances[_address] -= value;
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions to increase or decrease token balances and total supply.

## Authors

RAFAELLO JOSE VIERA
METACRAFTER STUDENT

