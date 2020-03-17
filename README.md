# sartuno-ltda
enabe
configure terminal
no ip domain-lookup
hostname RT-01
username sarturnoti privilege 15 secret batata*00
enable secret Sarturno*Enable
line console 0
password Sarturno*Console
login
login local
exit
banner motd "ATENCAO! APENAS O DEPARTAMENTO DE TI DA EMPRESA SARTUNO LTDA. TEM A AUTORIZACAO PARA ACESSAR ESSE EQUIPAMENTO!"
ip domain-name sarturno.local
crypto key generate rsa general-keys modulus 1024
service password-encryption
line vty 0 15
transport input ssh
password Sarturno*VTY
login
login local
exit
interface g0/0
description CONECTADA A INTERFACE G0/1 DO SW-01
ip address 172.16.15.1 255.255.255.0
no shutdown
exit
interface g0/1
description CONECTADA A INTERFACE G0/1 DO SW-02
ip address 192.168.0.1 255.255.0.0
no shutdown
exit
interface g0/2
description CONECTADA A INTERFACE G0/1 DO SW-03
ip address 172.16.10.1 255.255.255.0
no shutdown
end 
wr

enable
configure terminal
no ip domain-lookup
hostname SW-01
ip default-gateway 172.16.15.1
username sarturnoti privilege 15 secret batata*00
enable secret Sarturno*Enable
line console 0
password Sarturno*Console
login
login local
exit
banner motd "ATENCAO! APENAS O DEPARTAMENTO DE TI DA EMPRESA SARTUNO LTDA. TEM A AUTORIZACAO PARA ACESSAR ESSE EQUIPAMENTO!"
ip domain-name sarturno.local
crypto key generate rsa general-keys modulus 1024
service password-encryption
line vty 0 15
transport input ssh
password Sarturno*VTY
login
login local
exit
interface vlan 1
description INTERFACE DE GERENCIAMENTO
ip address 172.16.15.1 255.255.255.0
no shutdown
exit
interface fastethernet 0/1
description CONECTADA AO PC-01
exit
interface fastethernet 0/2
description CONECTADA AO PC-02
end 
wr

enable
configure terminal
no ip domain-lookup
hostname SW-02
ip default-gateway 192.168.0.1
username sarturnoti privilege 15 secret batata*00
enable secret Sarturno*Enable
line console 0
password Sarturno*Console
login
login local
exit
banner motd "ATENCAO! APENAS O DEPARTAMENTO DE TI DA EMPRESA SARTUNO LTDA. TEM A AUTORIZACAO PARA ACESSAR ESSE EQUIPAMENTO!"
ip domain-name sarturno.local
crypto key generate rsa general-keys modulus 1024
service password-encryption
line vty 0 15
transport input ssh
password Sarturno*VTY
login
login local
exit
interface vlan 1
description INTERFACE DE GERENCIAMENTO
ip address 192.168.255.254 255.255.0.0
no shutdown
exit
interface fastethernet 0/3
description CONECTADA AO PC-03
exit
interface fastethernet 0/4
description CONECTADA AO PC-04
end 
wr

enable
configure terminal
no ip domain-lookup
hostname SW-03
ip default-gateway 172.16.10.1
username sarturnoti privilege 15 secret batata*00
enable secret Sarturno*Enable
line console 0
password Sarturno*Console
login
login local
exit
banner motd "ATENCAO! APENAS O DEPARTAMENTO DE TI DA EMPRESA SARTUNO LTDA. TEM A AUTORIZACAO PARA ACESSAR ESSE EQUIPAMENTO!"
ip domain-name sarturno.local
crypto key generate rsa general-keys modulus 1024
service password-encryption
line vty 0 15
transport input ssh
password Sarturno*VTY
login
login local
exit
interface vlan 1
description INTERFACE DE GERENCIAMENTO
ip address 192.168.255.254 255.255.0.0
no shutdown
exit
interface fastethernet 0/1
description CONECTADA AO PC-03
exit
interface fastethernet 0/2
description CONECTADA AO PC-04
end 
wr


