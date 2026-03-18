
# Commandes Brim utilisées

## Filtres IP

ip.addr == 172.16.1.102                # tout le trafic lié à cette IP

ip.src == 172.16.1.102                 # trafic depuis cette IP

ip.dst == 172.16.1.102                 # trafic vers cette IP

## Filtres de protocole

http                                    # tout le trafic HTTP

_path == "http"                         # HTTP avec la vue _path

ip.dst == 172.16.1.102 && http          # HTTP vers cette IP

ip.addr == 172.16.1.102 && http         # HTTP lié à cette IP (source ou destination)

_path == "http" && ip.dst == 172.16.1.102   # HTTP vers cette IP avec _path

_path == "http" && ip.addr == 172.16.1.102  # HTTP lié à cette IP avec _path

## Filtres de port

tcp.port == 80                           # trafic TCP sur le port 80

ip.dst == 172.16.1.102 && tcp.port == 80 # port 80 vers cette IP

## Connexions complètes

conn                                     # toutes les connexions

conn && ip.addr == 172.16.1.102          # connexions liées à cette IP

conn && _path == "http"                   # connexions HTTP

conn && ip.addr == 172.16.1.102 && _path == "http"  # connexions HTTP liées à cette IP

## Filtres avancés

(ip.src == 172.16.1.102 || ip.dst == 172.16.1.102) && http  # HTTP source ou destination

http contains "login"                   # HTTP contenant le mot "login"
