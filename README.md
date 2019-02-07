# GIN Coin
Shell script to install a [GIN Coin Masternode](https://gincoin.io) on a Linux server running Ubuntu 16.04. Use it on your own risk.
This script will install **GIN 1.2.0.0**

***
## Installation:
```
wget -N https://raw.githubusercontent.com/zoldur/GinCoin/master/gin_install.sh
bash gin_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Gin Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **GIN** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Open **Debug Console** and type:
```
startmasternode "alias" "mn1" "mn1"
```
***

## Masternode update:
If you are running an old Gin version, simply running the installer will update you to the latest version.
***

## Usage:
```
gincoin-cli mnsync status
gincoin-cli getinfo
gincoin-cli masternode status
```

Also, if you want to check/start/stop **Gincoin** , run one of the following commands as **root**:

**Ubuntu 16.04**:
```
systemctl status Gincoin #To check the service is running.
systemctl start Gincoin #To start Gincoin service.
systemctl stop Gincoin #To stop Gincoin service.
systemctl is-enabled Gincoin #To check whetether Gincoin service is enabled on boot or not.
```

***

## Donations:

Any donation is highly appreciated.

**GIN**: GbPXbAnBHfjR63uyvMsV2dK6ZhxGoSxyvv
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB

