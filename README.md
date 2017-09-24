# My First Hyperledger Network 

A Commodity Trading network
https://hyperledger.github.io/composer/introduction/introduction.html

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Exportando variável responsável por determinar o modo de autenticação utilizado pela rede.

```
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
```

### Instalando dependências

```
cd hyperledger-firstnetworksample
npm install
```

### Re-generate your Business Network archive (BNA)

```
composer archive create --sourceType dir --sourceName . -a ./dist/my-network.bna
```

### Executando teste unitário

```
npm test
```

### Deploy the updated Business Network Definition to the runtime Fabric

```
cd ./dist
composer-rest-server -p hlfv1 -n my-network -i admin -s adminpw -a true
```

### Regenerate the REST APIs for the updated Business Network

```
cd ..
composer-rest-server
```

## Author

* **Marcel Savegnago** - *Initial work*

See my github profile (https://github.com/marcelsavegnago)

