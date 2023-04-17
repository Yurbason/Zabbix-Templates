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

![Template Macros](https://user-images.githubusercontent.com/52459938/232587780-35d9751c-83bf-40b8-83ad-8cb83ce5764d.png)

7. link template to validator host

## some screenshots
***monitoring values***

![Fetch monitoring values](https://user-images.githubusercontent.com/52459938/232587888-0b6a2eb3-bd9e-4f55-99fa-345dc9c9fb9f.png)



***triggers***

![FetchTriggers](https://user-images.githubusercontent.com/52459938/232587983-2c3d61a0-5c5b-4bcb-be7d-f1d68a947103.png)
