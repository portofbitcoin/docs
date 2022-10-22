# Building and running Core Lightning

When the Bitcoin software was first released by Satoshi Nakamoto in 2009 the only transactions it supported were onchain transactions, transactions that are verified by the entire network of full nodes and are stored in the blockchain for the rest of Bitcoin’s history. It became clear to Bitcoin wizards (and perhaps was clear to Satoshi all along) that this approach doesn’t scale to onboard the global population of billions of people. So the race was on to create a protocol on top of Bitcoin that allowed people to transact without needing to continuously bloat the underlying blockchain. In 2017 a bunch of those wizards coalesced around such a protocol that was named “Lightning”. Some Bitcoin wizards became Lightning wizards and they were joined by a long term Linux kernel contributor, Rusty Russell. Different implementations grew out of the specification process: Core Lightning, LND, Eclair, LDK, Electrum etc. We will focus on Core Lightning.

Core Lightning is written in the C language, a long term predecessor to C++ that Bitcoin Core is written in. Core Lightning is very modular, customizable and supports a plugin ecosystem where you can switch on additional functionality as you need it. To run Core Lightning you need to have your mainnet/testnet/signet/regtest Bitcoin Core node running in the background as the Bitcoin protocol is a dependency of the Lightning protocol.

Ok so let’s get Core Lightning running, we will run it in signet mode and hence your Bitcoin Core node needs to be running in signet mode also.