# simple-blockchain
A simple Python project to explore the concepts of blockchain technology. This blockchain follows proof-of-work methodology.  
  
## General concepts:  
1. **genesis**: On init, we create a ✨genesis block✨ (ooooh, fancy). This is our first ever block on the chain. All of the block's information is serialized into a string, encrypted, and stored on the block as a hash. Then, the genesis block is added to the chain (at index zero).
2. **store data**: We tell the chain we want to add data, which is stored as unconfirmed_data until a block can be mined.
3. **mine**: Mining is the process of adding a block to the chain. The following information will be stored on the block:
    * **index**: Increments as each new block is created.  
    * **data**: At the time a block is created, unconfirmed_data will be added to the block. Once the block is added to the chain, we can consider the data confirmed - 100% legit and in the books. 💪  
    * **timestamp**: The date/time at which the block was created.  
    * **hash**: This along with previous_hash are what make the blockchain secure. All of the data on the block is encrypted into this hash. In a proof of work system, this data is encrypted in a way that is very computationally heavy. If someone were to tamper with a block on the chain, they would have to recreate the hash of every following block. Since this is so computationally heavy, it is not possible to modify a block, re-compute all following hashes, and still keep up with all legitimate data being added to the blockchain.
    * **previous_hash**: The hash of the previous block on the chain.  
  
## Some of my own questions about blockchain:
**Q**: How do we know the transactions being added are legitimate? Meaning, how do we prevent someone from adding a transaction that says, "Bob gave me 50 BTC" when Bob didn't actually agree to do this?  
**A**: Different blockchains will have different methods of doing this. However, with the BTC example - BTC utilizes public and private keys. The public key is the address at which one can specify where they would like to send their BTC. The private key, which should never be shared, is used to prove ownership of the wallet in which BTC is being sent from. In order for Bob to send BTC, he must add a transaction to "unconfirmed_data" which involves those things. Then, it will be verified and added to the blockchain via mining.

**Q**: Since blockchains are fully distributed and open source, how do we know someone is executing a legitimate version of the code?  
**A**: ?  

_Built with the help of https://www.activestate.com/blog/how-to-build-a-blockchain-in-python/_
