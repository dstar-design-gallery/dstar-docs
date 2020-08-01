# Installation Guide

***

There are two ways to install D.Star for development:

1. Install D.Star UI with Remote Server
2. Install D.Star UI with Local Server

## 1. with Remote Server

1. Install the latest version of **Node** for your system at [here](https://nodejs.org/en/download/). This also installs **npm** (*node package manager*) automatically.

?> **tip**: make sure that `node` and `npm` are installed by typing on command line:

```bash
node -v
(v10.15.0)
npm -v
(6.11.3)
```

2. Clone `designgallery`.

```bash
git clone https://csil-git1.cs.surrey.sfu.ca/shovonr/designgallery.git
```

3. Create your own branch.

```bash
git checkout -b myBranch master
```

4. Locate the installation directory. Then install the project dependencies. 

```bash
npm install
```

5. Finally, run:

```bash
npm start
```

A browser window will open and redirect to `http://localhost:3000`

## 2. with Local Server

Do steps **1.** to **5.** above. Then:

1. To run your own server, you will need to install the latest version of MongoDB. Installation 
guides are offered at [here](https://docs.mongodb.com/manual/installation/) for **Windows**, **MacOS** and **Linux** users

?> **tip**: after setup, make sure `mongodb` is installed by typing: 

```bash
mongo --version
```

2. Clone `designgallery-server`.

```bash
git clone https://csil-git1.cs.surrey.sfu.ca/vzahedne/designgallery-server.git
```

3. Create your own branch.

```bash
git checkout -b myBranch master
```

4. Locate the installation directory. Then install the project dependencies.

```bash
npm install
```

5. In `designgallery`, locate to `url.js`, under `src/constants`. There, replace:

```javascript
const host = 'sr-02645.iat.sfu.ca:5050';
```

with

```javascript
const host = ‘localhost:5050';
```

6. In terminal, run mongoDB’s host process deamon, `mongod`, by typing:

```bash
mongod
```

7. Next, you'll need to install `Redis`. Download it from [here](https://redis.io/download). Then, in terminal, run:

```bash
redis-server
```

Open another terminal tab, then run:

```bash
redis-cli
set untitlednum 0
```

8. You will now need a database dump to populate your local server. Extract `dump.zip` and use:

```bash
mongorestore dump
```

9. Finally, in `designgallery-server` folder, run:

```bash
npm run start:dev
```

10. Refresh `http://localhost:3000` and you should now see some collections and alternatives on the UI.
