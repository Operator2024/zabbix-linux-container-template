# Zabbix LXC (Proxmox) container template

Changes by compared with original version "kvaps":
 - Added userparameter ``` UserParameter=ct.cpu.num[*],nproc ```;
 - changed the formula for calculating "memory utilization", parameter "pavailable" was ```pavailable=(($ 6+$ 7)*100/$ 2)``` , now ``` pavailable=(100-($ 7*100/$ 2)) ```.

The templete was exported from version 5 lts.

Template macros:
 - {$LOAD_AVG_PER_CPU.MAX.WARN} - 1.5 - Load per CPU considered sustainable. Tune if needed.
 - {$MEMORY.AVAILABLE.MIN} - 20 - This macro is used as a threshold in memory available trigger.
 - {$SWAP.PFREE.MIN.WARN} - 50

Discovery rules:
 - {#IFNAME} - need to change it to your regex.
 - {#FSTYPE} - need to change it to your regex.

For Zabbix version 5.4 and higher, you can use original zabbix template that are available [here](https://www.zabbix.com/ru/integrations/linux "Zabbix LXC template").

The link also provides descriptions of all macros and discovery rules the above.

Original README file by "kvaps" available [here](https://github.com/Operator2024/zabbix-linux-container-template/blob/master/README_kvaps.md "README_kvaps.md").
