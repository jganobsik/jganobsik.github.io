---
layout: post
title:      "Basic Blockchains with Go, Part 2"
date:       2019-09-23 23:08:26 +0000
permalink:  basic_blockchains_with_go_part_2
---


[Part 1](http://http://joeganobsik.com/basic_blockchains_with_go_part_1)

In my  last blog on Basic Blockchains with Go, we began to model the basic elements of a blockchain. Now, we will write some functions to add new blocks to the blockchain. First, let's write a function to create a block:

```
func CreateBlock(data string, prevHash []byte) *Block {
	block := &Block{[]byte{}, []byte(data), prevHash}
	block.DeriveHash()
	//return value is new block
	return block
}
```

We start by declaring the function and inputs. Our very basic CreateBlock function takes some form of data as string, and the hash of the previous block. Once the function has recieved the inputs, it assigns the data to the block as well as the previous hash, creates the hash of the current block, and returns the new block. We will quickly see how this block is used in our AddBlock function, which will add a new block to the blockchain:

```
func (c *BlockChain) AddBlock(data string) {
	//get last block in chain
	prevBlock := c.blocks[len(c.blocks)-1]
	//create new block
	new := CreateBlock(data, prevBlock.Hash)
	//add new block to chain
	c.blocks = append(c.blocks, new)
}
```

This function is called on a blockchain, and takes the data for the new block as an input. It takes the most recent block from the blockchain, and passes the data input and hash of the most recent block to the CreateBlock function. It then appends this data to the end of the blockchain.

These two functions comprise the primary functionality of a blockchain: sequentially adding blocks of data containing references to the previous block's hash. As noted in the previous blog post, blocks are "chained" together with the hash of the previous block. As such, we can verify the order in which blocks were created, giving us an idea of the chronological order in which events were recorded. This allows us to prove immutability, which is a very important principle of blockchains. Immutability means that nobody can go back and alter or delete data written to a blockchain. While we could write functions to update the data in our example blockchain,  production blockchains such as Bitcoin do not allow individuals to alter data recorded to the blockchain. 

We have now implemented the basic functions our blockchain needs to record new data. Stay tuned for part 3, where we will write several functions to initiate a new blockchain.


