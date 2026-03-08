
# Gobuster Pentest Playbook

Petit playbook d'utilisation de l'outil **Gobuster** pour l'énumération en pentesting web.

---

# 1. Directory Enumeration (DIR)

Permet de découvrir des dossiers et fichiers cachés sur un site web.

Wordlist utilisée :

/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

Commande :

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

---

# 2. DNS Subdomain Enumeration

Permet de découvrir des sous-domaines via brute force DNS.

Wordlist :

/usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt

Commande :

```bash
gobuster dns --domain target.com -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt
```

---

# 3. Virtual Host Discovery (VHOST)

Permet de découvrir des virtual hosts cachés sur un serveur web.

Wordlist :

/usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt

Commande :

```bash
gobuster vhost -u http://target.com -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt
```

---

# Flags importants

## -x

Permet de chercher des fichiers avec certaines extensions.

Exemple :

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,bak,zip
```

---

## --no-tls-validation

Ignore les erreurs de certificat SSL.

```bash
gobuster dir -u https://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --no-tls-validation
```

---

## --status-codes

Affiche seulement certains codes HTTP.

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --status-codes 200,301,302,403
```

---

## --cookie

Utilise un cookie de session.

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --cookie "PHPSESSID=123456"
```

---

## -H

Permet d'ajouter un header HTTP personnalisé.

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -H "Authorization: Bearer token123"
```

---

## -n

Ne pas afficher la taille des réponses.

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -n
```

---

## -p

Permet d'utiliser un fichier proxy.

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -p proxy.txt
```

---

## -u

Spécifie l'URL cible.

```bash
gobuster dir -u http://target.com -w wordlist.txt
```

---

## -s

Filtrer par codes HTTP spécifiques.

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -s 200,301,403
```

---

# Commande réaliste utilisée en pentest

```bash
gobuster dir -u http://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,bak,zip -s 200,301,403 -t 50
```

# Astuce pour trouver des sous-domaines en passant par le vhost

```bash
gobuster vhost -u http://offensivetools.thm -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt -t 60 --append-domain
```
