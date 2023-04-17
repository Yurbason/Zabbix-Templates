# Template for monitoring the validator in the Fetch.Ai network


## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[fetchd*]
AllowKey=system.run[curl*]
```
2. restart zabbix agent daemon
3. copy **fetchd** binary to **/usr/local/bin** or **/usr/bin**
4. copy **$HOME/.fetchd/config/app.toml client.toml config.toml** files to **$HOME/.fetchd/config/** directory of the user under which the zabbix agent daemon is running
5. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/main/Fetch/Fetch.xml) and import template to zabbix server (Configuration-->Templates-->Import)
6. configure template Macros
   - {$FETCHDELEGATORWALLET}  = **fetch1xxxxxxx** address of your wallet
   - {$FETCHDENOM}            = denom value (**afet**)
   - {$FETCHED25519PUBKEY}    = key info from `fetchd tendermint show-validator`
   - {$FETCHPORT}             = RPC port of your validator (**26657** default)
   - {$FETCHVALOPER}          = **fetchvaloper1xxxxxxx** address of your validator

![Template Macros]( )

7. link template to validator host

## some screenshots
***monitoring values***

![Fetch monitoring values]( )



***triggers***

![FetchTriggers]( )