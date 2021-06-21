# Zabbix LXC (Proxmox) container template

Changes by compared with original version "kvaps":
 - Added userparameter ``` UserParameter=ct.cpu.num[*],nproc ```;
 - changed the formula for calculating "memory utilization", parameter "pavailable" was ```pavailable=(($ 6+$ 7)*100/$ 2)``` , now ``` pavailable=(100-($ 7*100/$ 2)) ```.

The templete was exported from version 5 lts. Therefore, it was necessary to add global macros and filters to the detection rules.

Macros:
 - {$LOAD_AVG_PER_CPU.MAX.WARN}
 - {$MEMORY.AVAILABLE.MIN}
 - {$SWAP.PFREE.MIN.WARN}
 
Discovery rules:
 - {#IFNAME}
 - {#FSTYPE}

For Zabbix version 5.4 and higher, you can use original zabbix template that are available [here](https://www.zabbix.com/ru/integrations/linux "Zabbix LXC template").

The link also provides descriptions of all macros and discovery rules the above.

Original README file by "kvaps" available [here](https://github.com/Operator2024/zabbix-linux-container-template/blob/master/README_kvaps.md "README_kvaps.md").
