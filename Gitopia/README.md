# Template for monitoring the validator in the Gitopia network


## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[gitopiad*]
AllowKey=system.run[curl*]
```
2. restart zabbix agent daemon
3. copy **gitopiad** binary to **/usr/local/bin** or **/usr/bin**
4. copy **$HOME/.gitopia/config/app.toml client.toml config.toml** files to **$HOME/.gitopia/config/** directory of the user under which the zabbix agent daemon is running
5. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/main/Gitopia/Gitopia.xml) and import template to zabbix server (Configuration-->Templates-->Import)
6. configure template Macros
   - {$GITOPIADELEGATORWALLET}  = **gitopia1xxxxxxx** address of your wallet
   - {$GITOPIADENOM}            = denom value (**ulore**)
   - {$GITOPIAED25519PUBKEY}    = key info from `gitopiad tendermint show-validator`
   - {$GITOPIAPORT}             = RPC port of your validator (**26657** default)
   - {$GITOPIAVALOPER}          = **gitopiavaloper1xxxxxxx** address of your validator

![Template Macros]( )

7. link template to validator host

## some screenshots
***monitoring values***

![Gitopia monitoring values]( )



***triggers***

![GitopiaTriggers]( )