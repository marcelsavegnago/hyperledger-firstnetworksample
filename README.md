# My First Hyperledger Network

A Commodity Trading network
https://hyperledger.github.io/composer/introduction/introduction.html

## Preparando o ambiente

Installing the pre-requisites for Hyperledger Composer on Mac OS X

https://hyperledger.github.io/composer/installing/prereqs-mac.html

Installing and developing with Hyperledger Composer

https://hyperledger.github.io/composer/installing/development-tools.html

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
npm install -g passport-github
```

### Re-generate your Business Network archive (BNA)

```
composer archive create --sourceType dir --sourceName . -a ./dist/my-network.bna
```

### Executando teste unitário

```
npm test
```

### Deploy the Business Network Definition to the runtime Fabric

```
cd ./dist
composer network deploy -a my-network.bna -p hlfv1 -i PeerAdmin -s randomString
```

### Generate the REST APIs for the updated Business Network

```
cd ..
composer-rest-server -p hlfv1 -n my-network -i admin -s adminpw -a true
```

## Author

* **Marcel Savegnago** - *Initial work*

See my github profile (https://github.com/marcelsavegnago)

