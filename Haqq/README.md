# Template for monitoring the validator in the Haqq network


## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[haqqd*]
AllowKey=system.run[curl*]
```
2. restart zabbix agent daemon
3. copy **haqqd** binary to **/usr/local/bin** or **/usr/bin**
4. copy **$HOME/.haqqd/config/app.toml client.toml config.toml** files to **$HOME/.haqqd/config/** directory of the user under which the zabbix agent daemon is running
5. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/main/Haqq/Haqq.xml) and import template to zabbix server (Configuration-->Templates-->Import)
6. configure template Macros
   - {$HAQQDELEGATORWALLET}  = **haqq1xxxxxxx** address of your wallet
   - {$HAQQDENOM}            = denom value (**aISLM**)
   - {$HAQQED25519PUBKEY}    = key info from `haqqd tendermint show-validator`
   - {$HAQQPORT}             = RPC port of your validator (**26657** default)
   - {$HAQQVALOPER}          = **haqqvaloper1xxxxxxx** address of your validator

![Template Macros](https://user-images.githubusercontent.com/52459938/190162377-83d7f39f-e681-4e5f-b10a-1422abf63d2f.png)

7. link template to validator host

## some screenshots
***monitoring values***

![monitoring values](https://user-images.githubusercontent.com/52459938/190163450-854c551f-772a-40a3-aa7b-238aaf92b275.png)



***triggers***

![HaqqTriggers](https://user-images.githubusercontent.com/52459938/190162680-800c8772-91ba-4267-9f9b-16d4cf209e68.png)
