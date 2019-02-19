# Learning locker LRS installation in a Ubuntu 14.04 LTS server

## Requirements
Ubuntu 14.04 server with a minimum of 2 GB RAM.

## Steps

### Update the repositories
```
sudo apt-get update
sudo apt-get upgrade
```
### Install Node.js
```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```
### Install MongoDB
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo service mongod start
```
### Run the install script

```
wget -qO deployll.sh http://lrnloc.kr/installv2
sudo bash deployll.sh
```
## Set up HTTPS
```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install certbot python-certbot-nginx 
sudo certbot --nginx
```
# Extra

## Create a Bookmarklet to record your learning experiences
```
javascript: function rbm() {
    window.rbmAuth = "LRS key", window.rbmEndpoint = "LRS endpoint", window.rbmEmail = "your e-mail", window.rbmName = "your name";
    var a = document,
        b = a.createElement("sc" + "ript"),
        c = a.body,
        d = a.location;
    b.setAttribute("src", "https://tincanapi.com/wp-content/assets/Bookmarklet/3.4.0/bookmarklet-min.js");
    c.appendChild(b)
}
rbm();
void 0
```
