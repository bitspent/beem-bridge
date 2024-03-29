## Beem Bridge Link
Using Beem Bridge requires to have an ethereum wallet and a steem account.  
Before operating on the bridge a user should predefine or link both addresses.  
* **LINK** operation should match and occur on both blockchains to confirm the wallet - account duality.  
* **UNLINK** operation should match and occur on both blockchains as well to confirm the operation.  

### 1. Ethereum To Steem Link
This will create a one way Link passing from ethereum to steem.  
* To **link** the wallet to a steem account send a transaction to beem contract address with **msg.data** the Steem account
* To **unlink** the wallet and the steem account send a transaction to beem contract address with an empty **msg.data**
* To change the linked steem account you should first unlink the existing steem account.

### 2. Steem To Ethereum Link
This will create a one way Link passing from steem to ethereum.  
* To **link** the steem account to an ethereum wallet send a transaction to @steembeem **memo** as **LINK wallet_address** 
* To **unlink** the steem account and the wallet send a transaction to @steembeem **memo** content **UNLINK**
* To change the linked ethereum wallet you should first unlink the existing wallet.

### 3. Link Matching
Whenever both links are created, the ethereum wallet and steem account are matching on both blockchains, 
the link is activated and the user can post operate over the Beem bridge.

### 4. Unlink & Withdrawal
In the case of a confirmed unlink,  
All user's remaining balances (Ether & ERC-20 Tokens) on the sidechain are withdrawed to the user's ethereum's wallet.
