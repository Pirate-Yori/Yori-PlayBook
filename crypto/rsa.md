# Hashcat

Outil : Hashcat

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
