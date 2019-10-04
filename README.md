# Requirements
You need to install the following packages:
- [node.js](https://tecadmin.net/install-nodejs-with-nvm/): ^10.x`
- [docker](https://docs.docker.com/install/linux/docker-ce/debian/): ^19.x

# Deployment
Execute sequentially:
```
npm run volume:create
npm run docker:build
npm run docker:run
```
###### Notice
If you need, you can use `sudo` before every command.

Now you can connect to MySQL service inside of container using the following command:
```
mysql -h 0.0.0.0 --port=3307 -u root
```
All databases will be permanently stored in `/var/lib/docker/volumes/mysqldata/_data` folder.
