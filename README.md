MyToken Smart Contract

*Overview*

This smart contract implements a basic ERC20-like token named "META" with the abbreviation "META". It includes functionalities to mint and burn tokens, maintaining a balance for each address.

*Public Variables*

string public tokenName: The name of the token.
string public tokenAbbrev: The abbreviation of the token.
uint public totalSupply: The total supply of the token.

*Mapping*

mapping(address => uint) public balances: Stores the balance of each address.

*Functions*

mint(address _address, uint _value)
Increases the total supply and the balance of the specified address.

burn(address _address, uint _value)
Decreases the total supply and the balance of the specified address. Ensures sufficient balance before burning.

*License*

This project is licensed under the MIT License.
