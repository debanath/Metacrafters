# Getting Started with Solidity

In this Course, at the end of the course, we were given a certain task to complete

## Task to complete

- Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
- Your contract will have a mapping of addresses to balances (address => uint)
- You will have a mint function that takes two parameters: an address and a value. 
    - The function then increases the total supply by that number and increases the balance of the “sender” address by that amount
- Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
    - It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.
- Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.

## Completed Task

- Public Variables
```sol
    string public tokenName = "PAPER";
    string public tokenAbbrv = "PPR";
    uint public totalSupply = 0;
```
- Mapping Variable
```sol
    mapping (address=> uint) public balances; 
```

- Mint Function
```sol
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
```

- Burn Function
```sol
    function burn (address _address, uint _value) public {
        if(balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
```