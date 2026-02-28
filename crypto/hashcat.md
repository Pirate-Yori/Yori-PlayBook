# Hashcat
# Syntaxe de base
Hashcat utilise la syntaxe de base suivante: 

hashcat -m <hash_type> -a <attack_mode> hashfile wordlist
EX:
-m <hash_type> spécifie le type de hachage au format numérique. Par exemple, est pour NTLM. Consultez la documentation officielle () et la page d’exemple pour trouver le code de type de hachage à utiliser.-m 1000man hashcat
-a <attack_mode> spécifie le mode attaque. Par exemple, est pour straight, c’est-à-dire essayer un mot de passe de la liste de mots après l’autre.-a 0
hashfile est le fichier contenant le hachage que vous souhaitez craquer.
wordlist c’est la liste de mots de sécurité que vous souhaitez utiliser dans votre attaque.


## MD5
hashcat -m 0 hash.txt rockyou.txt

## SHA256
hashcat -m 1400 hash.txt rockyou.txt

## Voir tous les modes
hashcat --help

## Attaque brute force masque
hashcat -m 0 -a 3 hash.txt ?a?a?a?a?a?a

## Afficher les mots trouvés
hashcat -m 0 hash.txt rockyou.txt --show

---

## Notes personnelles
- GPU utilisé
- Performance
- Difficulté rencontrée



