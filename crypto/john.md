# John the Ripper

Outil : John the Ripper

## Crack automatique
john hash.txt

## Spécifier le format
john --format=raw-md5 hash.txt
john --format=raw-sha256 hash.txt

## Avec wordlist
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt

## Voir les mots de passe trouvés
john --show hash.txt

## Activer les règles
john --wordlist=rockyou.txt --rules hash.txt

---

## Notes personnelles
Ajouter ici :
- Type de hash rencontré
- Problème rencontré
- Temps de crack
