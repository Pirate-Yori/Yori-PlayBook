# Attaques RSA

## Calculer d avec p, q, e (Python)

from Crypto.Util.number import inverse
phi = (p-1)*(q-1)
d = inverse(e, phi)

## Vérifier si n est factorisable
Utiliser factordb.com

## Vérifier si e est trop petit
e = 3 → attention attaque low exponent
