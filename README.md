# Safecoin client bot

Enable a simple discord bot via client. The bot should be running with a blockchain explorer but for the moment it uses a exported json file from the client command getmininginfo, it requieres a daemon node with a client available. This tutorial assumes /safecoin is a wallet folder with inner daemon and client. For the safety of your safecoins, don't use your own wallet! 

ssh with your linux VPS and follow this instructions:

## Git files

```
cd safecoin
sudo apt-get install git
git clone https://github.com/baenimus/safecoinbot.git
```


## Install latest version of node.js

```
sudo apt-get install npm

sudo npm install n -g

sudo n stable
```

It needs the last version to run properly


## Run a safecoin node


```
cd safecoin 

sudo npm install nohup

nohup ./safecoind &

```
Let the wallet get synced 


## Run json file generator

A simple script to generate a json file updated every 20 seconds with last block info

```
cd safecoin

nohup bash mininginfo.sh &
```
Now you have a json file mininginfo.json. Check it is not empty.

## Enable discord bot
```
npm init 

npm install discord.js

nohup node app.js &
```

## Create a discord bot

Follow this tutorial 

https://github.com/reactiflux/discord-irc/wiki/Creating-a-discord-bot-&-getting-a-token

## Back to VPS

Change the new token of config.json file

```
cd safecoin
sudo nano config.json
```
## Invite bot to discord server

If you succesfully enabled the bot you should be able to invite it: 

https://discordapp.com/oauth2/authorize?&client_id=INSERTHEREBOTCLIENTID&scope=bot&permissions=0
