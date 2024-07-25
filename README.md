# AutoMigrateFromC7ToR9

Ansible script for migration from CentOS7 to Rocky 9 (WITH REBOOT)

# INTRODUCTION

This script uses Leapp (framework of ELevate) to upgrade CentOS7 to Rocky 8 and then Rocky 8 to Rocky 9

# INSTRUCTIONS FOR USE

ansible-playbook -i inventory.ini playbookMain.yml -u userName -Kk

## Curr situation (24.7)

Moze da prebaci na Rocky 8 ali prelazak iz Rocky 8 u 9 te baca na dracut .Samo treba udariti reboot. Moguce greske su privilegije usera koji pokrece skriptu i ulazi u masinu, nesto u skrpti vezano za drugo pozivanje gather_facts (doduse nvrjm).
Moguca resenja, rucno kreirati neki folder koji fali (/etc/leapp/repos.d/system_upgrade/common/files)

## Curr situation (25.7)

Istestirano, izgleda da tranzicija izmedju rada playbook-ova stvara bug koji je vezan za sam sorcecode leapp-a (https://bugzilla.redhat.com/show_bug.cgi?id=1878092), ne user error, pa sam odvojio playbook-ove. Kako mi se cini, sad bi trebalo sve da radi samo se mora pokretati odvojeno.
