# Lighting Network


Current status

https://explorer.acinq.co/

![](https://ln.bitfinex.com/img/WhatIsLn.svg)

image::https://ln.bitfinex.com/img/WhatIsLn.svg[]


## What is the Lightning Network

The most popular cryptocurrency in the world today is, of course, the oldest one, Bitcoin. But there is still the question, "Will Bitcoin be able to handle millions of daily transactions as more people adopt the cryptocurrency?"
The answer to this question might come in the form of the Lightning Network. The second layer technology for Bitcoin has the capability of boosting the number of transactions on the cryptocurrency per second while keeping the fees minuscule. The Lightning Network does this by creating a second layer on Bitcoin's blockchain to handle transactions independently without having them recorded on the blockchain every single time. This way, a vast amount of transactions are off-loaded from Bitcoin's blockchain, leaving the bandwidth with free spaces.

Bitfinex is excited about the many possibilities of the Lightning Network. We believe it will boost Bitcoin's competitiveness as a means of payment, which will bring us closer to achieving mass adoption.



## Nodes in Bitcoin & the Lightning Network

There are two kinds of nodes in the Bitcoin network.

* *Full node*
A full node keeps a copy of every transaction on the network, verifies transactions,  accepts new blocks, and then broadcasts the new transaction to other nodes.

* *Light node*
A light node doesn’t store the whole blockchain, only a tiny part of it. Light nodes download block headers (a section in a block that summarizes the rest of the block) to verify data and then transactions.




## Nodes in the Lightning Network

A Lightning node is software that connects and interacts with the main blockchain network and also within the Lightning Network itself. The main blockchain here refers to any blockchain network, on which LN is applicable, such as Bitcoin and Litecoin.

Nodes in the Lightning Network differ from those in the Bitcoin network, mainly in how they verify transactions. Nodes in the Bitcoin network must verify every transaction on the blockchain, while the Lightning nodes only verify the transaction that is interacting directly with it.

A Lightning node is the gateway into the Lightning Network. You need to have at least one node running to be able to explore the LN technology and enjoy everything it has to offer. Thanks to decentralisation, anyone can run a node, regardless of the network they’re using.

What are the advantages of running a node?

1. You contribute to the network.

2. You will have full custody of your crypto.

By running your node, there’s no need to trust intermediaries with the custody of your coins. Moreover, you don’t have to worry about trusting another node’s information because you will download the blockchain’s entire history into your node.

3. You can earn some sats by routing payments.


Once you start running your node, you could pass Lightning payments across the network and earn a few sats in exchange.


## Learn how to run a Lightning Node

Thanks to the innovation and development built on top of the Lightning Network, running a node is not as hard as it seems. Here’s the step-by-step guide:


### Step 1: Get the hardware and equipment

Running your node requires an initial investment in hardware.There are quite a few options out there—one of the most user-friendly ones is Raspberry Pi.

Other equipment that you need to prepare are:

* Micro SD card and 1 terabyte SSD hard drive for data storage
* LCD screen 3.5″ RPi Display, GPIO connection, XPT2046 Touch Controller
* 5FT Ethernet cable
* Power source

Please note that you don’t have to buy a Raspberry Pi device to run your node; you can do it with your computer. However, running your node on a dedicated device will minimize the attack surface of the software environment. Attack surfaces can be digital and physical, therefore a computer that is also used for navigating through the internet will be more vulnerable to a digital attack.

### Step 2: Install the software.

The Raspberry Pi needs to be loaded with a specific software—RaspiBlitz—and written on the memory card.

Raspberry Pi Imager is the easiest way to install the software into your Raspberry Pi device. Look for a tutorial online for your operating system and follow the instructions. Here’s also a video that will help you use Imager.


As an alternative to RaspiBlitz, separate software such as Umbrel can also be installed on a Raspberry Pi computer or a regular PC.

### Step 3: Connect to the network

Once you have installed the software, a step-by-step guide will take you through setting up a wallet and load it.

The next step would be to download the blockchain. Keep in mind that this process can take several hours to a couple of days.

Finally, open a lightning channel, connect to a node, and that’s it. You’re all set to start sending BTC from your node!

Connect to Bitfinex Lightning nodes to route payments

When you run a Lightning node, you must then open one or more payment channels to another node to route payments through them, otherwise, the node will not be able to send payments.

Pro tip: You need to open a channel to a reputable node with an excellent capacity to send BTC over the network.

A node with high capacity means more bitcoin is locked into that node than other nodes. Here you can see a visualisation of the subset of nodes and their payment channels with each other.

With two Lightning nodes, Bitfinex has, at this date, a combined public capacity of over 260 BTC. These nodes provide the network with two payment routing services with low fees.

 Connect to Bitfinex Lightning nodes!

https://ln.bitfinex.com/