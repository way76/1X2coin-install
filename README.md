# 1X2 Coin
Shell script to install a [1X2 Coin Masternode](https://www.1x2coin.net/) on a Linux server running Ubuntu 16.04 or 18.04. Use it on your own risk.

***
## Installation:
```
git clone https://github.com/1X2coin/1X2coin-install/
cd 1X2coin-install
bash 1x2coin-install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet:
1. Open the 1X2 Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **1X2** to **MN1**.
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
startmasternode "alias" "0" "MN1"
```
***

## Usage:
```
1x2coin-cli getinfo
1x2coin-cli mnsync status
1x2coin-cli masternode status
```
Also, if you want to check/start/stop **1X2Coin** , run one of the following commands as **root**:

**Ubuntu 16.04 or 18.04**:
```
systemctl status 1X2Coin # To check the service is running.
systemctl start 1X2Coin # To start 1X2Coin service.
systemctl stop 1X2Coin #To stop 1X2Coin service.
systemctl is-enabled 1X2Coin # To check whether 1X2Coin service is enabled on boot or not.
```
***