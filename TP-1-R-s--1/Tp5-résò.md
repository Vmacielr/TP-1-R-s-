# TP5 : Un ptit LAN à nous


## I. Setup

### ☀️ Uniquement avec des commandes, prouvez-que :

```c
[root@lan ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:42:4a:d1 brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.254/24 brd 10.5.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe42:4ad1/64 scope link
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:c5:86:bc brd ff:ff:ff:ff:ff:ff

```
```c
vicenzzo@client1:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:0f:06:40 brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.11/24 brd 10.5.1.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::ce11:171c:c121:78b/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
```
```c
vicenzzo@client2:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:68:0b:c3 brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.12/24 brd 10.5.1.255 scope global enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe68:bc3/64 scope link
       valid_lft forever preferred_lft forever
```
- Les pings 
```c
--- 10.5.1.12 ping statistics ---
9 packets transmitted, 9 received, 0% packet loss, time 8027ms
rtt min/avg/max/mdev = 1.600/3.586/11.271/3.072 ms
[root@lan ~]# ping 10.5.1.11 ; ping 10.5.1.12
PING 10.5.1.11 (10.5.1.11) 56(84) bytes of data.
64 bytes from 10.5.1.11: icmp_seq=1 ttl=64 time=1.62 ms
64 bytes from 10.5.1.11: icmp_seq=2 ttl=64 time=1.06 ms
64 bytes from 10.5.1.11: icmp_seq=3 ttl=64 time=1.26 ms
^C
--- 10.5.1.11 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2005ms
rtt min/avg/max/mdev = 1.062/1.316/1.624/0.232 ms
PING 10.5.1.12 (10.5.1.12) 56(84) bytes of data.
64 bytes from 10.5.1.12: icmp_seq=1 ttl=64 time=2.00 ms
64 bytes from 10.5.1.12: icmp_seq=2 ttl=64 time=2.56 ms
64 bytes from 10.5.1.12: icmp_seq=3 ttl=64 time=1.07 ms
^C
--- 10.5.1.12 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2007ms
rtt min/avg/max/mdev = 1.071/1.877/2.557/0.613 ms
```
## II. Accès internet pour tous

### 1. Accès internet routeur

#### ☀️ Déjà, prouvez que le routeur a un accès internet

```c
[root@lan ~]# ping www.ynov.com
PING www.ynov.com (172.67.74.226) 56(84) bytes of data.
64 bytes from 172.67.74.226 (172.67.74.226): icmp_seq=1 ttl=57 time=16.7 ms
64 bytes from 172.67.74.226 (172.67.74.226): icmp_seq=2 ttl=57 time=18.9 ms
```

```c
[root@lan ~]# sudo firewall-cmd --add-masquerade --permanent
success
[root@lan ~]# sudo firewall-cmd --reload
success
```
```c
--- www.ynov.com ping statistics ---
6 packets transmitted, 6 received, 0% packet loss, time 5006ms
rtt min/avg/max/mdev = 15.272/17.953/24.366/3.017 ms
[root@lan ~]# ping www.ynov.com
PING www.ynov.com (104.26.10.233) 56(84) bytes of data.
64 bytes from 104.26.10.233 (104.26.10.233): icmp_seq=1 ttl=57 time=16.0 ms
64 bytes from 104.26.10.233 (104.26.10.233): icmp_seq=2 ttl=57 time=16.0 ms
```

#### ☀️ Activez le routage
```c
[root@lan ~]# sudo firewall-cmd --add-masquerade --permanent
success
[root@lan ~]# sudo firewall-cmd --reload
success
```
### 2. Accès internet clients

#### ☀️ Prouvez que les clients ont un accès internet

```c
vicenzzo@client1:~$ ping www.ynov.com
PING www.ynov.com (172.67.74.226) 56(84) bytes of data.
64 bytes from 172.67.74.226: icmp_seq=1 ttl=56 time=20.8 ms
64 bytes from 172.67.74.226: icmp_seq=2 ttl=56 time=27.0 ms
```
#### ☀️ Montrez-moi le contenu final du fichier de configuration de l'interface réseau

```c
vicenzzo@client2:/etc/netplan$ cat 01-netcfg.yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s8:
      dhcp4: no
      addresses: [10.5.1.12/24]
      gateway4: 10.5.1.254
      nameservers:
        addresses: [1.1.1.1]
```
## III. Serveur SSH

#### ☀️ Sur routeur.tp5.b1, déterminer sur quel port écoute le serveur SSH
```c
[root@lan ~]# sudo ss -npt | grep 22
ESTAB 0      0         10.5.1.254:22       10.5.1.1:3736 users:(("sshd",pid=1271,fd=4),("sshd",pid=1267,fd=4))
```

#### ☀️ Sur routeur.tp5.b1, vérifier que ce port est bien ouvert

```c
[root@lan ~]# sudo ss -lnpt | grep 22
LISTEN 0      128          0.0.0.0:22        0.0.0.0:*    users:(("sshd",pid=701,fd=3))
LISTEN 0      128             [::]:22           [::]:*    users:(("sshd",pid=701,fd=4))
```



## IV. Serveur DHCP

###


