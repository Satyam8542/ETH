# SOLIDITY BEGINNER ASSESSMENT

This repository contains the implementation of a simple token contract written in Solidity. The token is named "METACRAFT" with the abbreviation "META".

## Description


This smart contract includes basic functionalities to mint and burn tokens. It maintains a mapping of addresses to their respective token balances and tracks the total supply of tokens.

## Getting Started

### FEATURE

#### Token Details: Public variables to store the token name, abbreviation, and total supply.
#### Balances Mapping: A mapping of addresses to their token balances.
#### Mint Function: A function to mint new tokens, increasing the total supply and the balance of the specified address.
#### Burn Function: A function to burn tokens, decreasing the total supply and the balance of the specified address, with a condition to ensure sufficient balance.

# Contract Details
## Public Variables
string public tokenName = "METACRAFT";
string public tokenAbbrv = "META";
uint public totalSupply = 0;
## Mapping
mapping(address => uint) public balances;

# Mint Function
The mint function increases the total supply by the specified value and adds that value to the balance of the given address.

function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
# Burn Function
The burn function decreases the total supply by the specified value and deducts that value from the balance of the given address. It includes a condition to ensure that the balance of the address is greater than or equal to the value to be burned.

function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
# Usage
To use this contract, deploy it to a compatible Ethereum network using a tool like Remix, Truffle, or Hardhat. Once deployed, you can interact with the contract functions to mint and burn tokens.

## Example

// Minting 100 tokens to address 0x123...
myToken.mint(0x123..., 100);

// Burning 50 tokens from address 0x123...
myToken.burn(0x123..., 50);

# Additional Information
For any questions or contributions, please open an issue or submit a pull request. Contributions are welcome!

Feel free to customize this README file further based on your project's specific needs and details.







