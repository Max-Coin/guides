Building on Linux
===============

To install the required dependencies, run the following command:

<code>$ sudo apt-get install git-core build-essential libssl-dev libboost-all-dev libdb5.1-dev libdb5.1++-dev libgtk2.0-dev libminiupnpc-dev qt4-qmake mingw32 synaptic qt-sdk qt4-dev-tools libqt4-dev libqt4-core libqt4-gui libdb++-dev</code>

Then grab the latest version of the MaxCoin source code from Github

<code>$ git clone https://github.com/Max-Coin/maxcoin.git</code>

<code>$ cd maxcoin</code>

To build the GUI run the following commands:

<code>$ qmake</code>

<code>$ make</code>

To build the daemon, run the following commands

<code>$ cd maxcoin/src</code>

<code>$ make -f makefile.unix</code>

Optionally, debugging symbols can be removed from the binary to reduce it's size. This can be done using strip.

<code>$ strip maxcoind</code>

Troubleshooting:
-------------

Building miniupnpc
----------------

If your OS doesn't support libminiupnpc, you can build this manually by performing the following steps:

<code>$ wget 'http://miniupnp.free.fr/files/download.php?file=miniupnpc-1.6.tar.gz' -O miniupnpc-1.6.tar.gz</code>

<code>$ tar -xzvf miniupnpc-1.6.tar.gz</code>

<code>$ cd miniupnpc-1.6</code>
	
<code>$ make</code>

<code>$ make install</code>

Cleaning the build:
----------------

If you have to clean your build environment you may have to rebuild LevelDB manually. This can be done using:

<code>$ cd src/leveldb</code>

<code>$ chmod +x build_detect_platform</code>

<code>$ ./build_detect_platform</code>

Ignore the usage errors (it still builds the relevent file) and now run:

<code>$ make libleveldb.a libmemenv.a</code>
