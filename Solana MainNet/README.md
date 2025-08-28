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

**Template Macros**
<img width="945" height="277" alt="SolanaMacros" src="https://github.com/user-attachments/assets/c14c8f8d-b461-4e63-8c93-61e6de17d629" />

6. link template to validator host

## some screenshots
***monitoring values***

<img width="1661" height="1099" alt="SolanaValues" src="https://github.com/user-attachments/assets/8cd5dfe6-cb0b-4da2-9532-70401ef18fd1" />

***triggers***

<img width="374" height="881" alt="SolanaTriggers" src="https://github.com/user-attachments/assets/e87daa85-f672-4eee-96d9-5fbcf9e6c8dc" />
