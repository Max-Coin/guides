MaxCoin wallet usage in Windows
===============================

The MaxCoin wallet is supplied in both graphical and command-line form. This file provides instructions for using both wallets. Also included is an example maxcoin.conf file. This allows the wallet to initially synchronise with the network, along with allowing configuration options to be specified by advanced users. The RPC username and password fields MUST BE CHANGED for your security.

For both users of Windows 7 and 8, this should be placed in <code>C:\Users\<username>\AppData\Roaming\MaxCoin\maxcoin.conf</code>.

Installation
------------

To install the wallet, simply copy the contents of this folder to any location you desire on your computer. You can create a desktop shortcut by right-clicking on maxcoin-qt.exe and selecting Send > To desktop (create shortcut).

Upgrading your wallet
---------------------

If you are upgrading from a previous version of MaxCoin, you'll need to ensure you make a back up of your wallet file. This is located at C:\Users\<username>\AppData\Roaming\MaxCoin\wallet.dat. Make a copy of this and store it in a safe location - this is the file that allows you to access your coins, it contains your private keys - in the unlikely event that something goes wrong with the install, you'll need this. Now, install the new version as per the instructions above. This should overwrite the existing version, whilst keeping the data intact. Finally, run the wallet and confirm that the update has occurred by viewing the version in the Debug window (Help > Debug window). It should read v0.9.0.0-xxxxxxxx-beta.

If you find you no longer have access to your old addresses or coins, copy the wallet.dat file back to the original location, C:\Users\<username>\AppData\Roaming\MaxCoin\, and restart your MaxCoin wallet.

Graphical wallet (maxcoin-qt.exe)
---------------------------------

The graphical wallet can be run by double-clicking on maxcoin-qt.exe. A splash screen should display the loading status of the wallet.

Use of the graphical wallet is fairly self-explanatory. The balance, along with recent transactions, can be seen in the Overview page. You can send and receive coins using their respective pages, specifying an address manually or using an address from the address book, found in the Addresses page. A complete list of transactions can be seen in the Transactions page.

To mine using the graphical wallet, the Mining page is used. You can specify two modes here, Solo or Pool. Solo mining uses an inbuilt CPU miner to try and find blocks - the chances of this happening are very slim however, and it isn't recommended. Pool mining uses the minerd.exe CPU miner (available from [here](https://github.com/Max-Coin/cpuminer/releases)) to mine using a mining pool (see [here](www.maxcoin.co.uk/pools) for a list of mining pools). The miner receives a share of work from the pool and, in exchange, will receive a proportional quantity of MaxCoins when a block is found.

Command-line wallet (maxcoind.exe)
----------------------------------

The command-line wallet can be run by typing <code>maxcoind</code> into a command-prompt when in the same directory as maxcoind.exe. You can optionally add the directory to the PATH environment variable so this can be run anywhere. Double-clicking run.bat will open a command prompt in the current directory.

To use the command-line wallet, a second command-prompt is used, also in the same directory as maxcoind.exe (or by double-clicking run.bat). This second command-prompt can then be used to issue commands to the wallet by typing <code>maxcoind COMMAND [OPTIONS]</code>. Typing <code>maxcoind help</code> will display a full list of available commands.

Common commands are:

+ <code>getbalance [account]</code> - displays the balance of your MaxCoin wallet or, optionally, an account
+ <code>getnewaddress [account]</code> - creates a new MaxCoin address and optionally adds it to an account
+ <code>backupwallet <destination></code> - backs up the wallet to a specified destination
+ <code>getccount <maxcoinaddress></code> - returns the account an address belongs to
+ <code>getaccountaddress <account></code> - returns the current MaxCoin address for an account
+ <code>getinfo</code> - displays information about the wallet and the network
+ <code>getpeerinfo</code> - displays information about connection nodes on the network
+ <code>getmininginfo</code> - displays information related to mining MaxCoins
+ <code>setgenerate <true|false></code> [processlimit] - turns on or off mining
+ <code>stop</code> - shuts down the MaxCoin wallet
+ <code>walletpassphrase <passphrase> <timeout></code> - unlocks an encrypted wallet for a specified number of seconds
+ <code>walletlock</code> - locks an encrypted wallet
+ <code>validateaddress <maxcoinaddress></code> - returns information about a specified address
+ <code>sendtoaddress <maxcoinaddress> <amount> [comment]</code> - sends MaxCoins to an address
+ <code>listaccounts</code> - displays accounts within the wallet
+ <code>listreceivedbyaccount</code> - lists the received transactions, grouped by the account
+ <code>listreceivedbyaddress</code> -lists the received transactions, grouped by the address

Advanced commands are:

+ <code>makekeypair</code> - generates a public-private keypair for MaxCoin address creatio
+ <code>signmessage</code>
+ <code>verifymessage</code>

A list of commands for Bitcoin can be found at https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_calls_list. A MaxCoin-specific list is being compiled and will be available soon.
