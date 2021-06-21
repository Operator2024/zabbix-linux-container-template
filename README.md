# Zabbix LXC (Proxmox) container template

Changes by compared with original version "kvarps":
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

For Zabbix version 5.4 and higher, you can use original zabbix template that are available here - https://www.zabbix.com/ru/integrations/linux
The link also provides descriptions of all macros and discovery rules the above.

Original README file by "kvarps" available [here](README_kvaps.md "README_kvarps.md")
