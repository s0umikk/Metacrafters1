
# Creating A Token Using Solidity

This Solidity program is built to mint and burn tokens on ethereum.
It can be also used to check the balance of the token in your account.

## Getting Started

Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at 
https://remix.ethereum.org/

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
string public tokenname = "token1";
string public tokenAbbrv = "t1";
uint public totalsupply = 0;
    // mapping variable here
mapping(address => uint) public balances;
    // mint function
function mint (address _address, uint _value) public {
    totalsupply += _value;
    balances[_address] += _value;
}
    // burn function
function burn (address _address, uint _value) public {
    if (balances[_address] >= _value) {
       totalsupply -= _value;
       balances[_address] -= _value;
    }
}
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. 
Make sure the "Compiler" option is set to 
"0.8.18" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken"  and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by using functions such as mint,burn and balance. 

The steps to interact with the program are given below:

1.Select MyToken from the contracts list.

2.Copy the account address you want the Transactions to take place.

3.Under deployed contracts. Youll find mainly 3 functions.
  >mint
  >burn
  >balances

4.Beside each function,paste the account address and input the value that you want to mint or burn.

5.To check the balance, simply put the account address and run the balance function and it will show the balance of tokens in your account.


## Author

Soumik Das
@s0umikk - GitHub
