---
layout: post
title:      "Basic Blockchains with Go, Part 1"
date:       2019-09-09 19:38:05 +0000
permalink:  basic_blockchains_with_go_part_1
---


Blockchain is a topic that generates quite a bit of buzz in the technology world. You may have heard of Bitcoin, a digital currency which is probably the most famous example of blockchain technology. Bitcoin and cryptocurrency are examples of blockchain technology in action, much like Facebook is an example of various web technologies in action.

With that said, there is a key question that we need to answer to improve our understanding of blockchain and related concepts: What is a blockchain? 

A blockchain, in it's simplest form, is a collection of sequential objects, or blocks, that can be appended to but not modified. Blocks are typically "chained" together by linking the cryptographic hash of the previous block to a new block which will be appended to the blockchain. To demonstrate how this works, we will examine a simple blockchain written in Go, a popular language for writing blockchains due to its combination of performance and ease of use.

To start defining our blockchain, let's create some Go structs. Go is not a purely object-oriented language, but it does utilize a pseudo-object called a struct, which behave a lot like objects. First, let's define a block, which will contain its own hash, the hash of the block before it, and some sort of data. We will represent all of these fields as arrays of bytes:

```
type Block struct {
	Hash     []byte
	Data     []byte
	PrevHash []byte
}
```

Next, let's define a blockchain struct, which is going to be a Slice of blocks. Go arrays must be of a fixed length, but slices do not have this limitation. However, slices can only contain the type of data specified when they are declared. This data can be a built in type such as String, Bool, Float, etc., or a Struct (You can learn more about slices [Here](https://gobyexample.com/slices)). Since our blockchain will contain an unspecified number of Block structs, a slice of blocks is the right choice here. Let's declare a blockchain to be a slice of blocks:

```
type BlockChain struct {
	blocks []*Block
}
```

Now we have the two basic structs we need to build our blockchain. Stay tuned for part 2, where we will write several functions relating to adding blocks to the blockchain.

The completed blockchain can be found at: https://github.com/jganobsik/Go_Blockchain
