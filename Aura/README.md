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

![Template Macros](https://user-images.githubusercontent.com/52459938/229200176-96d29d80-af15-4d2f-9ddb-58b06bd4b856.png)

7. link template to validator host

## some screenshots
***monitoring values***

![Aura monitoring values](https://user-images.githubusercontent.com/52459938/229312009-022734c4-8fec-4a5d-a06c-02ef2d3a2b03.png)



***triggers***

![AuraTriggers](https://user-images.githubusercontent.com/52459938/229200250-823bfc89-fb5f-4dd0-a957-2c786b78a5e0.png)
