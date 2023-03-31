# Template for monitoring the validator in the Shentu network


## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[shentud*]
AllowKey=system.run[curl*]
```
2. restart zabbix agent daemon
3. copy **shentud** binary to **/usr/local/bin** or **/usr/bin**
4. copy **$HOME/.shentud/config/app.toml client.toml config.toml** files to **$HOME/.shentud/config/** directory of the user under which the zabbix agent daemon is running
5. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/main/Certik/Certik.xml) and import template to zabbix server (Configuration-->Templates-->Import)
6. configure template Macros
   - {$CERTIKDELEGATORWALLET}  = **certik1xxxxxxx** address of your wallet
   - {$CERTIKDENOM}            = denom value (**uctk**)
   - {$CERTIKED25519PUBKEY}    = key info from `shentud tendermint show-validator`
   - {$CERTIKPORT}             = RPC port of your validator (**26657** default)
   - {$CERTIKVALOPER}          = **certikvaloper1xxxxxxx** address of your validator

![Template Macros]()

7. link template to validator host

## some screenshots
***monitoring values***

![Certik monitoring values]()



***triggers***

![Certik Triggers]()