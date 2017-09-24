# My Commodity Trading network


## Exporta variavel responsavel por determinar o modo de autenticação

export COMPOSER_PROVIDERS='{
  "github": {
    "provider": "github",
    "module": "passport-github",
    "clientID": "97147032757a7a372762",
    "clientSecret": "1c1d174d749515721d6d79387d71d4c6d0c4d49c",
    "authPath": "/auth/github",
    "callbackURL": "/auth/github/callback",
    "successRedirect": "/",
    "failureRedirect": "/"
  }
}'



'''
composer-rest-server -p hlfv1 -n my-network -i admin -s adminpw -a true
'''