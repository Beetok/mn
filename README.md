# Beetok
Shell script to install a [Beetok Masternode](https://www.beetok.io/) on a Linux server running Ubuntu 14.04, 16.04 or 18.04.

***
## Update the Beetok Wallet:
```
beetok-cli stop
wget -qO- https://github.com/Beetok/Beetok-Core/releases/download/v1.0.0.2/BEETOK-linux.tar.gz | sudo tar xvz -C /usr/local/bin/
beetokd -daemon
```
***
## Update the Beetok Wallet as a Service:
```
systemctl stop Beetok.service
wget -qO- https://github.com/Beetok/Beetok-Core/releases/download/v1.0.0.2/BEETOK-linux.tar.gz | sudo tar xvz -C /usr/local/bin/
systemctl start Beetok.service
```
***
## Install the Beetok Wallet:
```
git clone https://github.com/Beetok/mn/
bash mn/mn
```

***
## Desktop wallet setup
Steps to install the Windows Wallet
1. Open the Beetok Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **mn1**
3. Send **2000** **BTOK** to **mn1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **mn1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Next, go to our **Discord channel** for detailed instructions: https://discord.gg/xxxxxxx
***

## Usage:
```
beetok-cli getinfo
beetok-cli mnsync status
beetok-cli masternode status
tail -f .beetok/debug.log
```
Also, if you want to check/start/stop **Beetok** , run one of the following commands as **root**:

**Ubuntu 16.04 or 18.04**:
```
systemctl status Beetok #To check the service is running.
systemctl start Beetok #To start Beetok service.
systemctl stop Beetok #To stop Beetok service.
systemctl is-enabled Beetok #To check whetether Beetok service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/Beetok start #To start Beetok service
/etc/init.d/Beetok stop #To stop Beetok service
/etc/init.d/Beetok restart #To restart Beetok service
```
***
