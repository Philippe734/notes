## Run my own local front-end of Tornado Cash with Ubuntu 22.04

### full update for Ubuntu
```
sudo apt update ; sudo apt full-upgrade -y
```

### for the first run, let the magic do the trick
```
sudo apt install nodejs npm curl -y
sudo npm install --global yarn
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt install nodejs -y
sudo dpkg --configure -a
git clone https://development.tornadocash.community/tornadocash/classic-ui.git
cd classic-ui/
cp .env.example .env.local
yarn install --ignore-engines
yarn dev
```

## start Firefox and open
http://localhost:3000

## for the next times, from the directory "interface" execute
```
yarn dev
```
