E-matadaan, a online E-voting system using blockchain. Multiuser Sign up and authentication for an e-voting system which stores records on Ethereum based blockchain.

## To Compile the contract
```
truffle migrate
```

###### If a Contract is edited
If a Contract is edited, we need to reset the blockchain and deploy our new contract as we cannot make a change in the Blockchain thus we need to reset it using this truffle command.
```
truffle migrate --reset
```
## To Open Truffle Console
```truffle console```

## Exiting Truffle development console
```.exit```

## To use app on blockchain
```Election.deployed().then(function(i) { app=i; }) ``` //fallback function returning value via promise
app variable gets value of our app to act upon various functions. :-

 We can call in-built candidates getter function to get details of a candidate
 
 ```app.candidates(1)``` will return the details about 1st Candidate likewise we can get details of all the candidates.

 We can also store the value of a candidate by this command.
 ```app.candidates(1).then(function(c) { candidate = c; })``` This will store the value in candidate variable. 
 Now if we run this : ```candidate.id``` we will get its id
```candidate[0]``` will also give the candidate id
```candidate[0].toNumber()``` will give candidate id in Number format.
Similarily toString() can be used to get string value.

## Voters Side
Now anyone connected to the blockchain will be able to make a vote 
Voter will be modelled by address to any account given by the ganache in our ganache application.
Addresses can be accessed in truffle console by web3.js
```web3.eth.getAccounts().then(function(acc){ accounts = acc })``` this also returns a promise that is stored in accounts variable

accounts[0] will give the address of 1st account in ganache

## Why Testing is Important ?
In Blockchain project Testing is very important since we know the blochain is immutable and any changes won't ne possible later.

- If contract have bugs we need to deploy its new copy and the new copy won't have the same state and the same address. Then we need to disable the old contract
- Deploying a contract costs gas which costs ether thus increasing overall cost of the application.
- If a function has any bugs then a user sending the transaction will be wasting ether since it will not function as desired.

Truffle comes bundled with **Mocha** testing framework and **Chai** assertion library.

Election.js file is running the test to check correct candidates count.

## Meta Mask 
It is a chrome browser that turns our browser into a blockchain browser that connects to ethereum network and provides web3provider.

## Gas
Whenever account calls a function it has pay its fees.
Ethereum uses gas to calculate how much gas the user has to pay.
Because the reads are free but the writes are chargable.
Gas - unit within itself
Ether = No. of Gas units used X Gas price.

 

