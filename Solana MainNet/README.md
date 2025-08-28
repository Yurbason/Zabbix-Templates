# Template for monitoring the validator in the Solana MainNet


## installation instructions

1. add to zabbix agent configuration file
```
AllowKey=system.run[curl*]
AllowKey=system.run[solana*]
```
2. restart zabbix agent daemon
3. copy **solana** binary to **/usr/local/bin** or **/usr/bin** with a new name **solanaz**
4. [download](https://raw.githubusercontent.com/Yurbason/Zabbix-Templates/refs/heads/main/Solana%20MainNet/Solana.xml) and import template to zabbix server (Configuration-->Templates-->Import)
5. configure template Macros
   - {$ACCOUNTSHASHCACHEPATH}  = path to accounts-hash-cache-path
   - {$ACCOUNTSINDEXPATH}      = path to accounts-index-path
   - {$IDENTITYPUBKEY}         = identity pubkey
   - {$RAMDISKPATH}            = path to solana ramdisk
   - {$VOTEACCOUNTPUBKEY}      = vote account pubkey

![Template Macros](https://github.com/user-attachments/assets/bb615ab1-63ed-4336-b21d-abb9164497fd.png)

6. link template to validator host

## some screenshots
***monitoring values***

![Solana monitoring values]( )



***triggers***

![SolanaTriggers]( )
