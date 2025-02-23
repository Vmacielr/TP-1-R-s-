# Tp7 résò






## II. Serveur Web

### 1. HTTP

#### B. Configuration



##### 🌞 Lister les ports en écoute sur la machine

```powershell
[root@coucou conf.d]# ss -lnptu | grep 80
tcp   LISTEN 0      511          0.0.0.0:80        0.0.0.0:*    users:(("nginx",pid=11407,fd=6),("nginx",pid=11406,fd=6))
tcp   LISTEN 0      511             [::]:80           [::]:*    users:(("nginx",pid=11407,fd=7),("nginx",pid=11406,fd=7))
```

```powershell
    [root@coucou conf.d]# ss -lnptu | grep 80
tcp   LISTEN 0      511          0.0.0.0:80        0.0.0.0:*    users:(("nginx",pid=11407,fd=6),("nginx",pid=11406,fd=6))
tcp   LISTEN 0      511             [::]:80           [::]:*    users:(("nginx",pid=11407,fd=7),("nginx",pid=11406,fd=7))
```

#### 

#### C. Tests client
```powershell
[root@coucou conf.d]# ss -nptu | grep 80
tcp   ESTAB 0      0          10.7.1.11:80       10.7.1.1:51758 users:(("nginx",pid=1536,fd=3))
```
### 2. On rajoute un S

#### A. Config

##### 🌞 Lister les ports en écoute sur la machine

```powershell
[root@coucou conf.d]# ss -lnptu | grep 443
tcp   LISTEN 0      511        10.7.1.11:443       0.0.0.0:*    users:(("nginx",pid=1614,fd=6),("nginx",pid=1613,fd=6))
```

##### 🌞 Gérer le firewall

#### B. Test test test analyyyze

##### 🌞 Capture tcp_https.pcap

```powershell

```







## III. Serveur VPN


### 1. Install et conf Wireguard

#### 🌞 Prouvez que vous avez bien une nouvelle carte réseau wg0

```powershell
6: wg0: <POINTOPOINT,NOARP,UP,LOWER_UP> mtu 1420 qdisc noqueue state UNKNOWN group default qlen 1000
    link/none
    inet 10.7.200.1/24 scope global wg0
       valid_lft forever preferred_lft forever
```

#### 🌞 Déterminer sur quel port écoute Wireguard

```powershell
[root@vpn ~]# ss -lnptu | grep 51820
udp   UNCONN 0      0            0.0.0.0:51820      0.0.0.0:*
udp   UNCONN 0      0               [::]:51820         [::]:*
```
#### 🌞 Ouvrez ce port dans le firewall

```powershell

```
### 2. Ajout d'un client VPN



```powershell

```




```powershell

```