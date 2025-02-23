# TP3 : 32°13'34"N 95°03'27"W

## I. ARP basics

#### ☀️ Avant de continuer...
````powershell
 Adresse physique . . . . . . . . . . . : E4-C7-67-B5-A2-3E
````
#### ☀️ Affichez votre table ARP 
```powershell
PS C:\Users\hpvic> arp -a

Interface : 10.33.78.203 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.65.18           34-c9-3d-e4-52-69     dynamique
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique//--> adresse MAC passerellle
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique

Interface : 192.168.56.1 --- 0x29
  Adresse Internet      Adresse physique      Type
  192.168.56.101        08-00-27-34-51-22     dynamique
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
```

#### ☀️ Déterminez l'adresse MAC de la passerelle du réseau de l'école
```powershell
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
```
#### ☀️ Supprimez la ligne qui concerne la passerelle
```powershell
PS C:\Windows\system32> arp -d 10.33.79.254 ; arp -a

Interface : 10.33.78.203 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.65.18           34-c9-3d-e4-52-69     dynamique
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique

Interface : 192.168.56.1 --- 0x29
  Adresse Internet      Adresse physique      Type
  192.168.56.101        08-00-27-34-51-22     dynamique
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
```

#### ☀️ Prouvez que vous avez supprimé la ligne dans la table ARP
```powershell
PS C:\Windows\system32> arp -d 10.33.79.254 ; arp -a

Interface : 10.33.78.203 --- 0x6
  Adresse Internet      Adresse physique      Type
  10.33.65.18           34-c9-3d-e4-52-69     dynamique
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
```
#### ☀️ Wireshark

 la capture [arp1](arp1.pcap)

## II. ARP dans un réseau local

### 1. Basics

#### ☀️ Déterminer
```powershell
Description. . . . . . . . . . . . . . : Intel(R) Wireless-AC 9462
```
```powershell
 Adresse IPv4. . . . . . . . . . . . . .: 172.20.10.3(préféré)
```
```powershell
Adresse physique . . . . . . . . . . . : E4-C7-67-B5-A2-3E
```
#### ☀️ DIY
```powershell
Adresse IPv4. . . . . . . . . . . . . .: 172.20.10.2
```
#### ☀️ Pingz !
```powershell
PS C:\Users\hpvic> ping 172.20.10.13 ; ping 172.20.10.10 ; ping 172.20.10.14 ; ping google.com

Envoi d’une requête 'Ping'  172.20.10.13 avec 32 octets de données :
Réponse de 172.20.10.13 : octets=32 temps=19 ms TTL=128
Réponse de 172.20.10.13 : octets=32 temps=11 ms TTL=128
Réponse de 172.20.10.13 : octets=32 temps=11 ms TTL=128
Réponse de 172.20.10.13 : octets=32 temps=5 ms TTL=128

Statistiques Ping pour 172.20.10.13:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 5ms, Maximum = 19ms, Moyenne = 11ms

Envoi d’une requête 'Ping'  172.20.10.10 avec 32 octets de données :
Réponse de 172.20.10.10 : octets=32 temps=36 ms TTL=128
Réponse de 172.20.10.10 : octets=32 temps=45 ms TTL=128
Réponse de 172.20.10.10 : octets=32 temps=17 ms TTL=128
Réponse de 172.20.10.10 : octets=32 temps=10 ms TTL=128

Statistiques Ping pour 172.20.10.10:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 10ms, Maximum = 45ms, Moyenne = 27ms

Envoi d’une requête 'Ping'  172.20.10.14 avec 32 octets de données :
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Réponse de 172.20.10.2 : Impossible de joindre l’hôte de destination.
Réponse de 172.20.10.2 : Impossible de joindre l’hôte de destination.

Statistiques Ping pour 172.20.10.14:
    Paquets : envoyés = 4, reçus = 2, perdus = 2 (perte 50%),

Envoi d’une requête 'ping' sur google.com [2a00:1450:4007:807::200e] avec 32 octets de données :
Réponse de 2a00:1450:4007:807::200e : temps=52 ms
Réponse de 2a00:1450:4007:807::200e : temps=36 ms
Réponse de 2a00:1450:4007:807::200e : temps=58 ms
Réponse de 2a00:1450:4007:807::200e : temps=51 ms

Statistiques Ping pour 2a00:1450:4007:807::200e:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 36ms, Maximum = 58ms, Moyenne = 49ms
```

### 2. ARP

#### ☀️ Affichez votre table ARP !

```powershell
PS C:\Users\hpvic> arp -a

Interface : 172.20.10.2 --- 0x6
  Adresse Internet      Adresse physique      Type
  172.20.10.13          98-bd-80-d5-2b-bd     dynamique
  172.20.10.14          c0-35-32-1c-af-a9     dynamique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 192.168.56.1 --- 0x29
  Adresse Internet      Adresse physique      Type
  192.168.56.101        08-00-27-34-51-22     dynamique
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
```

#### ☀️ Capture arp2.pcap

[]()

### 3. Bonus : ARP poisoning

