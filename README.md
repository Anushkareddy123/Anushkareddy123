# SecureFileSharing
Prototype to store files on IPFS and Ethereum Blockchain.

## Requirements
* IPFS 
* Truffle 
* Ganache 
* Web3.js 
* NodeJs 
* Chrome with CORS extension

## Instructions

1) Install IPFS

2) Start IPFS daemon.  

   ipfs daemon

3) Configure config.js variables in Services/config.js.  
   Add Ganache mnemonic to CONFIG.wallet_passphrase. 
   
4) Deploy Smart Contracts using Truffle and Ganache.  
   Configure config.js variables in Services/config.js.  
   
   cd SecureFileSharing.  
   truffle compile -all.  
   truffle migrate -reset.  

4) Use the contract address generated after deployment in config.js, CONFIG.hs_contract_address variable.

5) Start the webapp.  

   npm install.  
   npm start.  

6) Start the React App.    

   cd app.  
   npm install.  
   npm start.  

7) Enable CORS from the Chrome Extension  

Note: The implementation stores the addresses of the authorized accounts in smart contract as per the current Ganache accounts. So, the values would need to be updated as per the blockchain on which the application runs.
 

Screenshots   


![](https://github.com/vaibs28/SecureFileSharingBlockchain/blob/master/img/s1.png).  


![](https://github.com/vaibs28/SecureFileSharingBlockchain/blob/master/img/s2.png).  


![](https://github.com/vaibs28/SecureFileSharingBlockchain/blob/master/img/s3.png).  



![](https://github.com/vaibs28/SecureFileSharingBlockchain/blob/master/img/s4.png).  


![](https://github.com/vaibs28/SecureFileSharingBlockchain/blob/master/img/s5.png).  
Nice — almost there! Now to **start the project**, here's a clean checklist to run everything smoothly step-by-step:

---

### ✅ 1. **Start Ganache**
Make sure your local Ethereum blockchain is running.

If you're using the **Ganache GUI**, just open it and start a workspace.  
If you're using **Ganache CLI**:

```bash
ganache-cli
```

> ⚠️ If you're using a different port than `7545`, update `ETH_URL` in your `.env` or `config.js`.

---

### ✅ 2. **Start the IPFS daemon**

In a separate terminal:

```bash
ipfs daemon
```

You should see something like:
```
Daemon is ready
```

> This makes sure the backend can add/get files from IPFS.

---

### ✅ 3. **Deploy the Smart Contract (if needed)**

If you haven’t already deployed the contract or want to redeploy:

```bash
truffle migrate --reset
```

Then copy the **new contract address** and update it in `config.js`:

```js
CONFIG.hs_contract_address = "0xYourNewContractAddress";
```

Restart the backend if you update this.

---

### ✅ 4. **Start the Backend Server**

In the root folder of the backend:

```bash
node server.js
```

You should see:

```
DocuHash listening on port 3002
```

---

### ✅ 5. **Start the Frontend**

In another terminal, go to your frontend folder and run:

```bash
npm start
```

It should launch on `http://localhost:3003/` (based on your `config.clientUrl`).

---

### ✅ 6. **Test the Flow**

- Upload a file (it should go to IPFS and return IPFS hash + file hash).
- Share the file using an Ethereum address.
- Use private key to retrieve shared files.

---

Want me to walk you through a test scenario now? (e.g. uploading and retrieving a file?)
