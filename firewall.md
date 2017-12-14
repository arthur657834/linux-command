```

systemctl start firewalld  
firewall-cmd --reload

firewall-cmd --permanent --list-port
firewall-cmd --list-all
firewall-cmd --zone=public --list-interfaces
firewall-cmd --list-rich-rules

firewall-cmd --state

firewall-cmd --permanent --add-rich-rule="rule family="ipv4" source address="10.1.251.206" port protocol="tcp" port="22" accept"
firewall-cmd --permanent --remove-rich-rule="rule family="ipv4" source address="10.1.251.206" port protocol="tcp" port="22" accept"

firewall-cmd --permanent --add-rich-rule="rule family="ipv4" port protocol="tcp" port="22" reject"

firewall-cmd --permanent --add-rich-rule="rule family=ipv4 source address=43.229.53.61 reject"

 
firewall-cmd --zone=public --remove-port=80/tcp --permanent
firewall-cmd --zone=public --add-port=4400-4600/udp --permanent
firewall-cmd --zone=public --query-port=80/tcp

firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --zone=public --remove-service=http

firewall-cmd --zone=public --add-masquerade
firewall-cmd --zone=public --add-forward-port=port=22:proto=tcp:toport=2055:toaddr=192.168.1.100


firewall-cmd --zone=external --query-masquerade
firewall-cmd --zone=external --add-masquerade
firewall-cmd --zone=external --remove-masquerade

firewall-cmd --zone=work --add-service=smtp
firewall-cmd --zone=work --remove-service=smtp

firewall-cmd --get-active-zones
firewall-cmd --set-default-zone=public

firewall-cmd --permanent --add-rich-rule="rule family="ipv4" source address="10.1.62.248" port protocol="tcp" port="80" accept"
firewall-cmd --reload
firewall-cmd --list-all

vi /etc/firewalld/zones/public.xml


```
