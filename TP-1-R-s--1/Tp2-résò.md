# Tp 2 résò

## I. Simplest LAN
### 1. Quelques pings

#### 🌞 Prouvez que votre configuration est effective

```powershell

vicenzzo@vicenzzo-VirtualBox:~$ ip addr show enp0s8
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:34:51:22 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.101/24 brd 192.168.56.255 scope global dynamic noprefixroute enp0s8
       valid_lft 491sec preferred_lft 491sec
    inet6 fe80::2391:5b63:a458:71b0/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
```

#### 🌞 Tester que votre LAN + votre adressage IP est fonctionnel

```Powershell
PS C:\Users\hpvic> ping 192.168.56.101

Envoi d’une requête 'Ping'  192.168.56.101 avec 32 octets de données :
Réponse de 192.168.56.101 : octets=32 temps=1 ms TTL=64
Réponse de 192.168.56.101 : octets=32 temps<1ms TTL=64
Réponse de 192.168.56.101 : octets=32 temps=1 ms TTL=64
Réponse de 192.168.56.101 : octets=32 temps=2 ms TTL=64

Statistiques Ping pour 192.168.56.101:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 2ms, Moyenne = 1ms
```
#### 🌞 Capture de ping

```
```
## II. Utilisation des ports
### 1. Animal numérique
#### 🌞 Sur le PC serveur

```C
vicenzzo@vicenzzo-VirtualBox:~$ nc -l 9999
```
#### 🌞 Sur le PC serveur toujours

- utiliser une commande pour voir qu'il y a désormais un port en écoute

```c
vicenzzo@vicenzzo-VirtualBox:~$ sudo ss -lnpt
```
- on verra que c'est le programme nc qui a ouvert le port et qui attend la connexion d'un client
```c
LISTEN       0            1                        0.0.0.0:9999                    0.0.0.0:*
```
#### 🌞 Sur le PC client
- l'autre, c'est donc le client !
utilisez la commande netcat suivante :
```powershell
 PS C:\Users\hpvic\Downloads\netcat-win32-1.12> .\nc.exe 192.168.56.101 9999
```
#### 🌞 Echangez-vous des messages

```c
vicenzzo@vicenzzo-VirtualBox:~$ nc -l 9999
bon salut mon pote virtuel
slt toi
```

#### 🌞 Faites une capture Wireshark complète d'un échange

[Capture NetCat 1](./netcat1.pcap)

## III. Analyse de vos applications usuelles

### 1. Serveur web

#### 🌞 Utilisez Wireshark pour capturer du trafic HTTP

[Capture HTTP](./http.pcap)

### 2. Autres services

#### 🌞 Pour les 5 applications

