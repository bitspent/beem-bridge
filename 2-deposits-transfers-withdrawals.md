**LINKED** Ethereum Wallet / Steem Accounts can operate on the **BEEM Bridge**  
#### Supported operations consists:  
* Going on the sidechain via Deposits  
* Fast Token / Ether Transfers on the sidechain    
* Going on the Ethereum blockchain via Withdrawals  
* Checking user's balance on the sidechain
* Detecting user's transfers on the sidechain  

#### Ether / ERC20 Token Deposit
* To deposit Ether or Tokens on the sidechain, the user sends ether, or commit an erc-20  
  token transfer on the ethereum network to the Beem smart-contract address.  
* Once deposited and tx-confirmed the balance will reflect on the beem sidechain  
 and a steem transaction from @steembeem with **memo**: **DEPOSITED TOKEN_NAME AMOUNT ERC20_CONTRACT_ADDRESS** to the linked steem account

#### Sidechain Token / Ether Transfers
* Linked steem accounts can transact freely on the sidechain with nearly 0 fees ( 0.002 STEEM per transaction )
* A sidechain token transfer takes an average of 3 seconds to be done and confirmed.
* A Transfer is a 0.002 STEEM Transfer to @steembeem with **memo**: **TRANSFER TO_ACCOUNT TOKEN_NAME AMOUNT ERC20_CONTRACT_ADDRESS**
* Transfer Result is a double transaction 0.001 STEEM Transfer from @steembeem to both @sender and @receiver   
  about the transfer result e.g. when a sender send 100 USDT to a receiver both will get the feedback transaction reply:  
  **@sender transferred USDT 100 to @receiver 0xb772c656f5021b6f0ab5d701c8e2b3c06735071a remaining balance 2400**  
* Both users balance are updated accordingly 

### Ether / ERC20 Token Withdrawal
* To withdraw Ether or Tokens on the Ethereum Blockchain,  
  the user sends a transaction to @steembeem with **memo**: **WITHDRAW TOKEN_NAME AMOUNT ERC20_CONTRACT_ADDRESS**  
* Beem ethereum smart-contract will send the token / ether on the ethereum blockchain to the linked wallet with **msg.data**: **WITHDRAWED TOKEN_NAME AMOUNT ERC20_CONTRACT_ADDRESS**  
  in case of sufficient funds. in all cases a transaction reply on the sidechain from @steembeem to the @user will be sent with **memo**: **WITHDRAWED TOKEN_NAME AMOUNT ERC20_CONTRACT_ADDRESS**
  in case of sufficient funds, else **WITHDRAW FAILED LOW BALANCE TOKEN_NAME AMOUNT ERC20_CONTRACT_ADDRESS**
