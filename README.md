# Project: Create a Token

This Solidity program is a simple simulation of how a smart contract mint or burn a certain kind of token. It demonstrates some basic variable & function declaration. 

## Description

This program is a simple contract written in Solidity programming language. The contract has two functions such as mint and burn function respectively. The main purpose of this program is to imitate how to add(mint) and remove(burn) a token from a user(address). This program serves as my introduction to Solidity programming and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    string public tokenName = "SAITAM";
    string public tokenAbbrv = "STM";
    uint public totalSupply = 0;
    mapping(address => uint) public balances;

    function mintToken(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    function burnToken(address _address, uint _value) public {
        if(balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

## Authors

Mark Joseph Pardiñas

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
