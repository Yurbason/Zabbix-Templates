# Template for monitoring the validator in the Aura network


## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[aurad*]
AllowKey=system.run[curl*]
```
2. restart zabbix agent daemon
3. copy **aurad** binary to **/usr/local/bin** or **/usr/bin**
4. copy **$HOME/.aura/config/app.toml client.toml config.toml** files to **$HOME/.aura/config/** directory of the user under which the zabbix agent daemon is running
5. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/main/Aura/Aura.xml) and import template to zabbix server (Configuration-->Templates-->Import)
6. configure template Macros
   - {$AURADELEGATORWALLET}  = **aura1xxxxxxx** address of your wallet
   - {$AURADENOM}            = denom value (**uaura**)
   - {$AURAED25519PUBKEY}    = key info from `aurad tendermint show-validator`
   - {$AURAPORT}             = RPC port of your validator (**26657** default)
   - {$AURAVALOPER}          = **auravaloper1xxxxxxx** address of your validator

![Template Macros](https://user-images.githubusercontent.com/52459938/174291436-c030def9-e989-4a6f-bac1-f64f39baa84a.png)

7. link template to validator host

## some screenshots
***monitoring values***

![Aura monitoring values](https://user-images.githubusercontent.com/52459938/174290704-137ba455-7f7e-4b81-8536-d68122d070f0.png)



***triggers***

![AuraTriggers](https://user-images.githubusercontent.com/52459938/174290841-a185307f-32bb-4884-9dad-b8f13885ca48.png)