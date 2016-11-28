nmcli general status
nmcli connection show (-a)
nmcli device status
nmcli device disconnect eno16777736
nmcli device connect eno16777736

nmcli connection add type ethernet con-name NEW ifname eno16777736 ip4 192.168.1.141 gw4 192.168.1.1

nmcli connection modify NEW ipv4.dns "8.8.8.8 8.8.4.4"

nmcli connection up NEW ifname eno16777736

nmcli -p connection show NEW

nmcli connection add type ethernet con-name NEW_DHCP ifname eno16777736