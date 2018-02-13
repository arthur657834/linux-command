```
ip netns
ip netns exec qdhcp-6e056e41-e48d-4119-b970-55ff7bae6f2d ping 192.168.100.2 

ip addr flush br-ex <==> ovs-vsctl del-br be-ex
ip a | grep br-ex
ifconfig eth0 promisc
```
