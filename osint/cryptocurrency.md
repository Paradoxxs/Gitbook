---
description: Method for investigating cryptocurrency
---

# Cryptocurrency

## What is the blockchain

it works by having a public distributed ledger system, which everyone can read from, making every transaction transparent to everyone. To write to the ledger, you need to be in possession of a wallet private key. When you add a transaction to the ledger, it needs to verify, this is often done by the miners which are compute power that is rented out to the ledger and in exchange, the miner gets a fee for handling the verification process.

By joining as a node on the specific blockchain, which will allow you to pull down the ledger, to see all the transaction that have happened.

When you create an wallet you get an key pair an private and an public.\
The private key need to be protected, as it gives access to send money.\
The public key is the one you share with others as it allow people to send money to you.\
Hardware device can to used to contain the private key, in a secure way,\
e.g. [https://www.ledger.com/](https://www.ledger.com/)

Exchanges are custodian of cryptocurrency, they allow one to buy and sell crypto.\
It also allow you to send currency within the exchange to other for a minimal fee, as everything is within the same ledger.\
Exchanges will group multiple transactions together into one block, making it hard to trace

## Investigation

Because of the nature of the blockchain of open ledger, everyone have the possibility to view the transaction that have happened.
This allow you to investigate when money gets transferred to another wallet.
The problem is that wallets can not be directly linked to an identity.
One way is to wait for the wallet to transfer money to an crypto exchange for exchanging the crypto.

One way people try to hide their track is using crypto tumbler (mixer). 
The way it works is by pooling together funds from multiple sources. Then splitting them back out to the destination addresses, distributed at random times, making it diffcult to trace the funds.

People are seems to moving away from the traditional mixer and going toward privacy wallet which is using an method called CoinJoin transaction.

CoinJoin is when multiple people combines their transaction into one transaction making it unclear for outsider to determine which crypto is owned by who after the transaction.

One common way for identifying the owner of the owner of the wallet is when they do an privacy error.

#### Tools

* blockchain.com
* Chainalysis
* Maltego
  * Allow to visualization the investigation of bitcoin blockchain by using the blockchain.info transform.

