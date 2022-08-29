# Building and running Bitcoin Core

So we haven’t done anything specifically Bitcoin related so far so let’s put that right. If you are going to join the Bitcoin network, validate transactions and ensure every new block meets the Bitcoin consensus rules you need to set up a Bitcoin full node. Don’t trust, verify! Bitcoin Core is considered by many as the reference client and is certainly the dominant node implementation on the network today. The code repository can be viewed and downloaded on [GitHub](https://github.com/bitcoin/bitcoin). Instructions for how to build Bitcoin Core on MacOS are [here](https://github.com/bitcoin/bitcoin/blob/master/doc/build-osx.md). We’ll pull out the most important instructions below but for additional clarity or troubleshooting refer to that documentation.

You need to install Xcode Command Line Tools if it isn’t installed already by entering the following in the command line:

`xcode-select --install`

Click on `Install` in the popup.

Bitcoin Core requires certain dependencies to be installed first. We will use Homebrew to install them.

`brew install automake libtool boost pkg-config libevent`

A full list of optional dependencies are [here](https://github.com/bitcoin/bitcoin/blob/master/doc/dependencies.md)

Now let’s `git clone` the Bitcoin Core repository:

`git clone git@github.com:bitcoin/bitcoin.git`

or

`git clone git@github.com:bitcoin/bitcoin.git insert_new_directory_name`

if you want it to be cloned in a different directory name to `bitcoin`.

Then `cd` into it:

`cd bitcoin` or `cd insert_new_directory_name`

We are now in a position to build Bitcoin Core.

Enter the following commands:

`./autogen.sh`

`./configure --without-gui`

We won’t build the GUI here but if you want to use the GUI remove the `--without-gui` option or see `./configure --help` for all the possible options.

If this is your first time building Bitcoin Core you don’t need to do the following but it is good practice if you are going to be building Bitcoin Core regularly.

`make clean`

Then

`make -j5`

(Specifying `-j5` should speed up the build but if you have fewer cores and a less powerful laptop you might want to not use `-j5`)

# Running bitcoind (regtest)

If this is your first time running Bitcoin Core (and the Bitcoin daemon bitcoind) you might want to run it first in regtest mode. Unlike mainnet, testnet and signet you won’t connect to any external peers on the network and it is entirely local. In addition you can generate regtest coins yourself without requesting them from somebody else. So while you’re getting comfortable with Bitcoin Core you might want to stay in this mode. To run bitcoind in regtest mode:

`./src/bitcoind -daemon -regtest`

`bitcoin-cli` is the command line interface for Bitcoin Core. You can see all the command line options in the help.

`./src/bitcoin-cli -regtest --help`

To stop the regtest bitcoind daemon:

`./src/bitcoin-cli -regtest stop`

# Monitoring and stopping running bitcoinds

If you are regularly running bitcoind and you forget to stop bitcoind you can see which Bitcoin processes are running using the command:

`ps -ax | grep bitcoin`

This will tell you the number of the Bitcoin process that is running and then you can kill it.

`kill insert_pid_number`

# Running bitcoind (signet)

Once you have played around in regtest the next step up would be to run bitcoind in signet mode and start interacting with external peers that you don't control. Testnet can be used for a similar purpose but signet is a better option for various reasons. It is easier to get signet coins from faucets (there are more signet coins circulating), the signet chain is much smaller and won't take so long to verify and signet block discovery follows a similar pattern to mainnet.

To run bitcoind in signet mode:

`./src/bitcoind -daemon -signet`

Your signet node will start up, connect to signet peers, receive signet blocks and verify those signet blocks. With regtest you had no external peers and had to generate regtest blocks yourself.

To receive signet coins you need to generate a signet address and then request signet coins to it by going to <https://signetfaucet.com/>.

Let's create a signet wallet and generate a signet address:

`./src/bitcoin-cli -signet createwallet "insert_wallet_name"`


 


