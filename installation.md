# Installation Guide

***

## Setup

1. Clone dstar-client in Windows using git `bash`:

```bash  
git clone https://github.com/dstar-design-gallery/dstar-client.git  
cd dstar-client  
git checkout develop  
```

1. Clone dsar-server in Windows using git `bash`:

```bash
git clone https://github.com/dstar-design-gallery/dstar-server.git 
cd dstar-server
git checkout develop
```

1. Install Node.js and NPM in WSL: [instructions](https://www.rosehosting.com/blog/install-npm-on-ubuntu-16-04/).  

1. Install MongoDB in WSL:: [instructions](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

```bash
sudo apt-get install -y mongodb-org=4.2.5 mongodb-org-server=4.2.5 mongodb-org-shell=4.2.5 mongodb-org-mongos=4.2.5 mongodb-org-tools=4.2.5
```

1. After that:

```bash
tar -xzvf dump.tar.gz  
cd dump  
mongorestore
```

This will restore the existing database.

> :warning: Do not empty the database with Mongo Shell commands like `db.collections.remove({})`. This will clear the layout as well. Instead, delete all alternatives/collections *using the front-end only*.

1. Install **Redis** in WSL:

```bash
sudo apt install redis-server
```

1. Install **NPM** packages for `dstar-client`

```bash
cd dstar-client
npm install
```

1. Install **NPM** packages for `dstar-server`

```bash
cd dstar-server
npm install
```

> :information_source: You may have package specific problems, but they can only be solved case-by-case.

## Running

*All instructions in WSL bash (separate Ubuntu terminals).*

1. Run **Redis**. You need to do this only once per session.

```bash
sudo service redis-server start
```

Then:

```bash
redis-cli
SET untitlednum 0
```

1. Running the server in WSL:  

```bash
dstar-server
npm start
```

1. Running the client in WSL:  

```bash
cd dstar-client  
npm start run:dev
```

1. Check if **Mongo** is running. Again, in a new terminal.

```bash
mongo
```

At the prompt, type `use gallery_dev`. Then type `db.alternatives.find({})`.

If you see a whole lot of alternatives data, it means your mongo restore was successful. You may close this window now.

1. Proceed to running the **Grasshopper**. Instructions are to be found in the DStar repo README.md.
