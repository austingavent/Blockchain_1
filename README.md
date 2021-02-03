# Blockchain_1

Welcome to the Jackal network where you'll have an infinite amount of pretend money to send around!

### Getting ready
First, you'll need to download several packages.
 GoEthereum- this will create your network and/or nodes to link to a blockchain or create your own.
 MyCrypto- this will allow you to send and view wallets you have linked to the nodes you created.

#Creating a POA blockchain
1. First create two new nodes using the geth command
  a. enter your goethereum folder in a terminal window
  b. type the following command to create a node-
  ./geth --datadir node1 account new
  ./geth --datadir node2 account new

2. Now that you have your nodes set up, you'll have to create a new genesis using proof of authority
  a. run the ./puppeth command in your geth folder
  b. Select configure new genesis, then create new genesis, then select clique- proof-of-authority
  c. Create a chain idea of your choosing

3. Now we need json files to set up our nodes
  a. while in the geth configuration, select manage exisiting gensis the choose export gensis configurations

4. Now lets initalize the nodes to our network's json!
  a. use this command to initalize each node
  ./geth --datadir node1 init jackal.json
  ./geth --datadir node2 init jackal.json
 
5. Lets start mining.....
  a. Run this command to connect the nodes together
  ./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
  ./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
  
 ###Start sending
  Now that we have a network set up, lets link the prefunded nodes to our MyCrypto account
 1. Under network, choose custom then right in your network/node name then type in the chain ID and the default RPC port for URL
  a. for my network, it is called Jackal
  b. My Chain ID is 333
  c. I am using ETH as currency
 
 2. After clicking the save and use button for both nodes, we're ready to send money
  a. Go to the view and send tab on the left, click keystore File
  b. Navigate to your keystore file under your node's folder
  c. After entering your passphrase, you should be in your node's wallet and see ETH already ther
  d. Enter your other node's address and chooose an amount to send. Then send!
 
 3. After you send, your wallet's account balance should change and you can confirm the transaction status by the CheckTXStatus button
  (sidenote: I didnt get a successful transaction screen even though the currency was exchanged
