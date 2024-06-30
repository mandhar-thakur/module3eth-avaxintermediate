The SimpleToken contract is a basic implementation of an ERC-20 token on the Ethereum blockchain. It provides functionalities for token minting by the contract owner, token transfers between users, and token burning by individual holders.

Functionalities Showcased
Only Contract Owner Can Mint Tokens:

The contract includes a modifier onlyOwner that restricts the mint function to be callable only by the contract owner (owner). This ensures that new tokens can only be created by the designated owner.
Any User Can Transfer Tokens:

The transfer function allows any token holder to transfer tokens to another address (to). It checks if the sender has sufficient balance before transferring tokens.
Any User Can Burn Tokens:

The burn function allows any token holder to burn (destroy) their own tokens, reducing the total supply. It ensures that the token holder has enough balance to burn the specified amount.
