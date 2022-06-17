# Template for monitoring the validator in the FirmaChain network

## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[firmachaind*]
AllowKey=system.run[curl*]
```
2. restart zabbix agent daemon
3. copy **firmachaind** binary to **/usr/local/bin** or **/usr/bin**
4. copy **$HOME/.firmachain/config/app.toml client.toml config.toml** files to **$HOME/.firmachain/config/** directory of the user under which the zabbix agent daemon is running
5. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/main/FirmaChain/FirmaChain.xml) and import template to zabbix server (Configuration-->Templates-->Import)
6. configure template Macros
   - {$FIRMADELEGATORWALLET}  = **firma1xxxxxxx** address of your wallet
   - {$FIRMADENOM}            = denom value (**ufct**)
   - {$FIRMAED25519PUBKEY}    = key info from `firmachaind tendermint show-validator`
   - {$FIRMAPORT}             = RPC port of your validator (**26657** default)
   - {$FIRMAVALOPER}          = **firmavaloper1xxxxxxx** address of your validator

![Template Macros](https://user-images.githubusercontent.com/52459938/174291436-c030def9-e989-4a6f-bac1-f64f39baa84a.png)

7. link template to validator host

## some screenshots
***monitoring values***

![monitoring values](https://user-images.githubusercontent.com/52459938/174290704-137ba455-7f7e-4b81-8536-d68122d070f0.png)

***triggers***

![FirmaTriggers](https://user-images.githubusercontent.com/52459938/174290841-a185307f-32bb-4884-9dad-b8f13885ca48.png)
