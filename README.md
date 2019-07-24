# mn-deploy-script
Automatic MNPRO masternode installation script for ubuntu 16 server

## Installation:
```
 git clone https://github.com/unix-help/mn-deploy-script.git
 cd mn-deploy-script
 chmod -R 755 mnpro.sh
 bash mnpro.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Mnpr Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **REQUIRED-COLLATERAL** **MNPR** to **MN1**.
4. Wait for confirmations.
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
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. SAVE and exit the Wallet.
10. Open MNPR Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If then also not starting then click on >tools>debug console> Type: startmasternode alias false "name of your MN alias"

***

## To check the status in your VPS:
```
mnpro-cli getinfo
mnpro-cli masternode status
mnpro-cli mnsync status
```
Also, if you want to check/start/stop **mnpr** , run one of the following commands as **root**:
```
systemctl status MNPR.service #To check the service is running.
systemctl start MNPR.service #To start mnpr service.
systemctl stop MNPR.service #To stop mnpr service.

```
***
