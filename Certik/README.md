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
   - {$CERTIKDELEGATORWALLET}  = **shentu1xxxxxxx** address of your wallet
   - {$CERTIKDENOM}            = denom value (**uctk**)
   - {$CERTIKED25519PUBKEY}    = key info from `shentud tendermint show-validator`
   - {$CERTIKPORT}             = RPC port of your validator (**26657** default)

   - {$CERTIKVALOPER}          = **shentuvaloper1xxxxxxx** address of your validator

![Template Macros](https://user-images.githubusercontent.com/52459938/229214680-73b143cc-5d8e-4602-85a3-52dafd91be62.png)

7. link template to validator host

## some screenshots
***monitoring values***

![Certik monitoring values](https://user-images.githubusercontent.com/52459938/229214993-1dfea5a9-26f4-4032-a472-192ff11018fd.png)


***triggers***

![Certik Triggers](https://user-images.githubusercontent.com/52459938/229214802-0e2c0433-1fc3-41f9-856f-8c730ea11b21.png)
