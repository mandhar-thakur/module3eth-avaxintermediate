# ETH_Intermediate_proof_ Module_3
In this repo we have tried to understand the types of function.

### contract initialization
```
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.18;

contract Rudra_intermediate_3 {
```
setting of name and abbriuiation variables and a record state variable to store the number of tokens
```
    string public tokenName = "Gol Gpappa";
    string public tokenAbbr = "GG";

    address owner;

    mapping(address => uint) record;
```
constructor to assign the owner's address to a variable named owner
```
constructor(){
        owner = msg.sender;
    }
```
Funtion to print or to get the current balance of the tokens
```
function getBalance() external view returns (uint){
        return record[msg.sender];
    }
```
Mint function to mint the tokens for Owner only
```
function mint(address to, uint amount) external {
        require(msg.sender == owner,"Only the owner can mint tokens");
        record[to] += amount;
    }
```
TransferTo function is used by any address to tranfer the tokens to any account
```
function transferTo(address to, uint amount) external{
        require(record[msg.sender] >= amount,"Insufficient balance in this account");
        record[to] += amount;
        record[msg.sender] -= amount;
    }
```
Burn funtion to burn the tokens minted by user or to burn the token recieved by transferTo function
```
function burn(uint amount) external {
        require(record[msg.sender] >= amount,"Insufficient balance in this account");
        record[msg.sender] -= amount;
    }
}
```
made with ❤️
