# STP Portfast, BPDU Guard, Root Guard Configs & STP Attacks Prevention Configuration
**S1
en
config t
hostname S1
int range f0/23-24
switchport mode trunk 
exit
int range f0/1-22, g0/1-2
switchport mode access
spanning-tree portfast
spanning-tree portfast bpduguard enable
exit 
spanning-tree portfast default
spanning-tree portfast bpduguard default
do wr

**S2
en
config t
hostname S2
int range f0/23-24
switchport mode trunk 
exit
int range f0/1-22, g0/1-2
switchport mode access
spanning-tree portfast
spanning-tree portfast bpduguard enable
exit 
spanning-tree portfast default
spanning-tree portfast bpduguard default
do wr

**S3
en
config t
hostname S3
int range f0/23-24
switchport mode trunk 
exit
int f0/22
switchport mode trunk
spanning-tree guard root 
exit
do wr
