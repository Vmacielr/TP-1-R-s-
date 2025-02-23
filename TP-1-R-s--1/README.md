




I. Récolte d'informations


🌞 Adresses IP de ta machine
affiche l'adresse IP que ta machine a sur sa carte réseau WiFi

``
PS C:\Users\hpvic> ipconfig /all
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Intel(R) Wireless-AC 9462
   Adresse physique . . . . . . . . . . . : E4-C7-67-B5-A2-3E
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::12a2:61b4:3463:df68%6(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.74.251(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Bail obtenu. . . . . . . . . . . . . . : vendredi 27 septembre 2024 13:57:42
   Bail expirant. . . . . . . . . . . . . : samedi 28 septembre 2024 13:57:43
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
   Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
   IAID DHCPv6 . . . . . . . . . . . : 82102119
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2E-4C-7F-7C-00-E0-4C-74-53-20
   Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8`

``

``
🌞 Si t'as un accès internet normal, d'autres infos sont forcément dispos...

*affiche l'adresse IP de la passerelle du réseau local

*affiche l'adresse IP du serveur DHCP que connaît ton PC


Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Intel(R) Wireless-AC 9462
   Adresse physique . . . . . . . . . . . : E4-C7-67-B5-A2-3E
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::12a2:61b4:3463:df68%6(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.74.251(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Bail obtenu. . . . . . . . . . . . . . : vendredi 27 septembre 2024 13:57:42
   Bail expirant. . . . . . . . . . . . . : samedi 28 septembre 2024 13:57:43
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
   Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
   IAID DHCPv6 . . . . . . . . . . . : 82102119
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2E-4C-7F-7C-00-E0-4C-74-53-20
   Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8
                                       1.1.1.1
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé

``

II. Utiliser le réseau

🌞 Envoie un ping vers...

toi-même !

``
PS C:\Windows\system32> ping 10.33.74.251

Envoi d’une requête 'Ping'  10.33.74.251 avec 32 octets de données :
Réponse de 10.33.74.251 : octets=32 temps<1ms TTL=128
Réponse de 10.33.74.251 : octets=32 temps<1ms TTL=128
Réponse de 10.33.74.251 : octets=32 temps<1ms TTL=128
Réponse de 10.33.74.251 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 10.33.74.251:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
``

vers l'adresse IP 127.0.0.1

``
PS C:\Windows\system32> ping 127.0.0.1

Envoi d’une requête 'Ping'  127.0.0.1 avec 32 octets de données :
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 127.0.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
``

🌞 On continue avec ping. Envoie un ping vers...

ta passerelle

``
Envoi d’une requête 'Ping'  10.33.79.254 avec 32 octets de données :
Délai d’attente de la demande dépassé.

Statistiques Ping pour 10.33.79.254:
    Paquets : envoyés = 1, reçus = 0, perdus = 1 (perte 100%),
``

un(e) pote sur le réseau

``
PS C:\Windows\system32> ping 10.33.66.78

Envoi d’une requête 'Ping'  10.33.66.78 avec 32 octets de données :
Réponse de 10.33.66.78 : octets=32 temps=98 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=104 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=116 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=28 ms TTL=64

Statistiques Ping pour 10.33.66.78:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 28ms, Maximum = 116ms, Moyenne = 86ms
``

un site internet

``
PS C:\Windows\system32> ping www.ynov.com

Envoi d’une requête 'ping' sur www.ynov.com [104.26.10.233] avec 32 octets de données :
Réponse de 104.26.10.233 : octets=32 temps=16 ms TTL=55
Réponse de 104.26.10.233 : octets=32 temps=16 ms TTL=55
Réponse de 104.26.10.233 : octets=32 temps=16 ms TTL=55
Réponse de 104.26.10.233 : octets=32 temps=16 ms TTL=55

Statistiques Ping pour 104.26.10.233:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 16ms, Maximum = 16ms, Moyenne = 16ms

``

🌞 Faire une requête DNS à la main

``
PS C:\Windows\system32> nslookup ynov.com
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    ynov.com
Addresses:  2606:4700:20::681a:be9
          2606:4700:20::ac43:4ae2
          2606:4700:20::681a:ae9
          172.67.74.226
          104.26.10.233
          104.26.11.233
``

effectue une requête DNS à la main pour obtenir l'adresse IP qui correspond aux noms de domaine suivants:

www.thinkerview.com
www.wikileaks.org
www.torproject.org

``
PS C:\Windows\system32> nslookup www.thinkerview.com
>>
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.thinkerview.com
Addresses:  2a06:98c1:3120::7
          2a06:98c1:3121::7
          188.114.96.7
          188.114.97.7

PS C:\Windows\system32> nslookup www.wikileaks.org
>>
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    wikileaks.org
Addresses:  80.81.248.21
          51.159.197.136
Aliases:  www.wikileaks.org

PS C:\Windows\system32> nslookup www.torproject.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.torproject.org
Addresses:  2a01:4f8:fff0:4f:266:37ff:feae:3bbc
          2620:7:6002:0:466:39ff:fe32:e3dd
          2620:7:6002:0:466:39ff:fe7f:1826
          2a01:4f9:c010:19eb::1
          2a01:4f8:fff0:4f:266:37ff:fe2c:5d19
          95.216.163.36
          204.8.99.146
          116.202.120.166
          116.202.120.165
          204.8.99.144

``
III. Sniffer le réseau

``
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::12a2:61b4:3463:df68%6
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.78.203
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
``
 