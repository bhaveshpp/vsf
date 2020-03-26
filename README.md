## Install Vue Storefront in Linux-mint with localhost magento instence

### Install prerequest
------------
> ## Docker Compose

> ### Run every command as sudo user
    
> $ sudo su

> $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

> $ sudo bash -c 'echo "deb [arch=amd64] https://download.docker.com/linux/ubuntu disco stable" > /etc/apt/sources.list.d/docker-ce.list'

> $ sudo apt-get update

> $ apt-cache policy docker-ce

> $ sudo apt-get install -y docker-ce

> $ sudo systemctl status docker
 
> ## Nodejs

> $ curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -

> $ sudo apt install nodejs

> $ node --version

> $ npm --version

> ## yarn

> $ curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -

> $ echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

> $ sudo apt update && sudo apt install yarn

> $ yarn --version

### install vuestorefront
------------
>   $ git clone https://github.com/DivanteLtd/vue-storefront.git vue-storefront

>   $ git clone https://github.com/DivanteLtd/vue-storefront-api.git vue-storefront-api

>   $ cd vue-storefront

>   $ yarn install

>   $ cd vue-storefront-api

>   $ yarn install

>   $ cp /opt/lampp/htdocs/mage234/vue-storefront/config/default.json /opt/lampp/htdocs/mage234/vue-storefront/config/local.json

>   $ cp /opt/lampp/htdocs/mage234/vue-storefront-api/config/default.json /opt/lampp/htdocs/mage234/vue-storefront-api/config/local.json

>   ### Create an integration for magento2 api call and provide details [token info] and [URL] in vue-storefront-api/config/local.json

```
"magento2": {
    "imgUrl": "http://127.0.0.1/mage234/pub/media/catalog/product",
    "assetPath": "/../var/magento2-sample-data/pub/media",
    "api": {
      "url": "http://127.0.0.1/mage234/rest",
      "consumerKey": "byv3730rhoulpopcq64don8ukb8lf2gq",
      "consumerSecret": "u9q4fcobv7vfx9td80oupa6uhexc27rb",
      "accessToken": "040xx3qy7s0j28o3q0exrfop579cy20m",
      "accessTokenSecret": "7qunl3p505rubmr7u1ijt7odyialnih9"
    }
  }, 

```

>   $ docker-compose up -d

>   $ yarn mage2vs import

>   $ cd ..

>   $ cd vue-storefront-api

>   $ yarn dev

>   ### in new tab run

>   $ cd vue-storefront-api

>   $ yarn dev

