
**<u>Create A Bitcoin address with Bitcore</u>**

I like Bitcore because it is javascript based.

I think Bitcore provides a great platform to build services that interact with the Bitcoin blockchain



Follow to install NVM, Node, Bitcore and create a bitcoin address

NVM install instructions:
https://github.com/creationix/nvm#install-script

curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash

* close and open terminal

* install node v4.2

nvm install v4.2

* check the version

node --version

* install bitcore globally

npm install -g bitcore

* make project directory

mkdir my_bitcoin_project

* enter directory

cd my_bitcoin_project

* launch npm new project wizard

npm init

* please answer defaults to all questions, if you want to change it, edit package.json

* install bitcore-lib 

npm install bitcore-lib --save

* enter interactive node shell

node

* load the lib

var bitcore = require('bitcore-lib');

* random 32 byte number

var rand_buffer = bitcore.crypto.Random.getRandomBuffer(32);

* convert to number

var rand_number = bitcore.crypto.BN.fromBuffer(rand_buffer);

* output number

rand_number

* print decimal

rand_number.toString()

* use that number to create a fake Bitcoin address not to be used on any public network

var address = new bitcore.PrivateKey(rand_number).toAddress();

* make a test network address

var address = new bitcore.PrivateKey(rand_number).toAddress(‘testnet’);
