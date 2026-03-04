# Pour avoir des informations sur une cle private ( lire )

openssl rsa -in privatekey.pem -text -noout

# Pour avoir des informations sur les clee public( lire)

openssl rsa -pubin -in pubkey.pem -text -noout

