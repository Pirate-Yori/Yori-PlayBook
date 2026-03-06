# tcpdump

## Description

tcpdump est un outil en ligne de commande utilisé pour **capturer et analyser le trafic réseau**.
Il permet d'inspecter les paquets qui transitent sur une interface réseau en temps réel.

Il est souvent utilisé pour :

* l'analyse réseau
* l'investigation d'incidents
* le debugging réseau
* la détection d'activités suspectes
* la capture de trafic pour analyse forensique

Les captures peuvent être enregistrées dans des fichiers **.pcap** et analysées plus tard avec Wireshark.

---

# Analogie simple

Imagine un **péage sur une autoroute** :

* les voitures = paquets réseau
* l'autoroute = le réseau
* tcpdump = un policier qui observe toutes les voitures qui passent

Le policier peut voir :

* d'où vient la voiture (IP source)
* où elle va (IP destination)
* quel type de véhicule (protocole)
* parfois ce qu'elle transporte (data)

---

# Commandes essentielles

## Voir les interfaces réseau disponibles

```bash
tcpdump -D
```

## Capturer le trafic sur une interface spécifique

```bash
sudo tcpdump -i eth0
```

## Désactiver la résolution DNS et ports

```bash
tcpdump -nn
```

## Capturer seulement un nombre limité de paquets

```bash
tcpdump -c 10
```

---

# Filtres les plus utilisés

## Filtrer par adresse IP

```bash
tcpdump host 192.168.1.10
```

## Filtrer seulement la source

```bash
tcpdump src 192.168.1.10
```

## Filtrer seulement la destination

```bash
tcpdump dst 192.168.1.10
```

---

# Filtrer par port

## HTTP

```bash
tcpdump port 80
```

## HTTPS

```bash
tcpdump port 443
```

## DNS

```bash
tcpdump port 53
```

## SSH

```bash
tcpdump port 22
```

---

# Filtrer par protocole

## TCP

```bash
tcpdump tcp
```

## UDP

```bash
tcpdump udp
```

## ICMP (ping)

```bash
tcpdump icmp
```

---

# Combiner plusieurs filtres

## Trafic HTTP en TCP

```bash
tcpdump tcp port 80
```

## Trafic venant d'une IP spécifique sur HTTPS

```bash
tcpdump src 192.168.1.10 and port 443
```

---

# Sauvegarder une capture réseau

```bash
tcpdump -w capture.pcap
```

Cela crée un fichier :

```
capture.pcap
```

Ce fichier peut être analysé avec **Wireshark**.

---

# Lire une capture enregistrée

```bash
tcpdump -r capture.pcap
```

---

# Afficher le contenu des paquets

```bash
tcpdump -X
```

Cette commande affiche :

* le contenu hexadécimal
* la représentation ASCII


# Afficher le contenu des paquets de maniere tres simplifie

```bash
tcpdump -q
```
---

# Cas d'utilisation en cybersécurité

## Analyse d'attaque réseau

Surveiller les communications suspectes.

## Détection de malware

Observer les connexions vers des serveurs de commande (C2).

## Analyse DNS suspecte

Identifier des requêtes DNS vers des domaines malveillants.

## Investigation d'incident

Capturer le trafic pendant un incident pour analyse forensique.

---

# Exemple pratique SOC

Capturer tout le trafic d'une interface pour analyse :

```bash
sudo tcpdump -i eth0 -w traffic.pcap
```

Ensuite ouvrir la capture dans Wireshark pour analyse approfondie.

---

# Points forts de tcpdump

* très rapide
* très léger
* fonctionne sur serveur sans interface graphique
* outil standard pour les administrateurs réseau et analystes sécurité
