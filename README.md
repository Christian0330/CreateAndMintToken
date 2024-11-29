# EcoGem Token Smart Contract

**EcoGem** is an ERC20-compliant token with functionality for minting, burning, and transferring tokens. Built with OpenZeppelin's ERC20 library, the contract enforces a strict maximum supply to maintain token scarcity.  

---

## Features

1. **Minting Tokens**  
   - Only the admin can mint tokens.  
   - Total supply cannot exceed a predefined maximum of **500,000 EGM**.

2. **Burning Tokens**  
   - Token holders can burn their tokens to permanently reduce the circulating supply.

3. **Token Transfers**  
   - Supports standard ERC20 token transfers between users.

---

## Contract Details

- **Token Name**: EcoGem  
- **Symbol**: EGM  
- **Maximum Supply**: 500,000 EGM  
- **Initial Supply**: Configurable during deployment  

---

## Functions

### **constructor(uint256 initialSupply)**  
Initializes the contract, minting the specified `initialSupply` to the deployer's address.  

**Parameters**:  
- `initialSupply` (uint256): Number of tokens to mint upon deployment.  

---

### **mintTokens(address recipient, uint256 amount)**  
Allows the admin to mint tokens and transfer them to the specified `recipient`, subject to the maximum supply limit.  

**Modifiers**:  
- `onlyAdmin`: Restricts function access to the admin.  
- `mintLimit`: Ensures total supply does not exceed `MAX_SUPPLY`.  

**Parameters**:  
- `recipient` (address): Address to receive the minted tokens.  
- `amount` (uint256): Number of tokens to mint.  

---

### **sendTokens(address to, uint256 amount)**  
Transfers tokens from the sender's address to the specified `to` address.  

**Parameters**:  
- `to` (address): Recipient address.  
- `amount` (uint256): Number of tokens to transfer.  

**Returns**:  
- `bool`: Returns `true` if the transfer is successful.  

---

### **burnTokens(uint256 amount)**  
Enables a token holder to burn a specified amount of their own tokens, reducing the total supply.  

**Parameters**:  
- `amount` (uint256): Number of tokens to burn.  

---

## Events

1. **TokenMinted(address indexed recipient, uint256 amount)**  
   - Emitted whenever new tokens are minted.  

2. **TokenBurned(address indexed burner, uint256 amount)**  
   - Emitted whenever tokens are burned.  

---

## Usage Notes

- Ensure the deployer specifies an appropriate initial supply during deployment.  
- Only the admin can mint tokens, and the total supply cannot exceed **500,000 EGM**.  
- Token holders have full control over transferring and burning their tokens.  

### Deployment Example (Remix)
1. Compile the contract using Solidity version `0.8.18`.  
2. Deploy with an initial supply (e.g., `10000` for 10,000 EGM).  
3. Use the admin address to mint or manage additional tokens as necessary.  

---

### Authors  
Metacrafter Chris_Narumi.  

#### License: This project is licensed under the MIT License. See the LICENSE.md file for details.
