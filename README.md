# CREATING INTER-VLAN TRUNK SWITCH AND ROUTER
CREATING INTER-VLAN TRUNK SWITCH AND ROUTER 
-------------

hostname SW-1
vlan 10
name IT
vlan 20
name HR
vlan 30
name Finance
exit
------

Accessports
-------------
int range fa0/1-2
switchport mode access 
SW-1(config-if-range)#w
switchport access vlan 10
exit
int range fa0/3-4
switchport mode access 
switchport access vlan 20
exit
int range fa0/5-6
switchport mode access 
switchport access vlan 30
exit


inter-vlan trunk switch
------------------
int range fa0/7
SWitchport mode trunk

inter-vlan trunk router 
------------------

int g0/0
no shutdown 
int g0/0.10
encapsulation dot1Q 10
ip address 10.0.0.10 255.0.0.0
int g0/0.20
encapsulation dot1Q 20
ip address 20.0.0.10 255.0.0.0
int g0/0.30
encapsulation dot1Q 30
ip address 30.0.0.10 255.0.0.0
exit
![CREATING INTER-VLAN TRUNK SWITCH AND ROUTER](https://user-images.githubusercontent.com/106605770/177989445-1d67e262-0868-4a6e-bdcf-062103b1cff8.jpg)
