# Requirements

You need to install the following packages:
- [node.js](https://tecadmin.net/install-nodejs-with-nvm/): ^10.x`
- [docker](https://docs.docker.com/install/linux/docker-ce/debian/): ^19.x

# Deployment

1\. Execute sequentially:
```
npm run volume:create
npm run docker:build
npm run docker:run
```
If you need, you can use `sudo` before every command.

2\. Set MySQL user password (this is required step!):
```
mysql -h0.0.0.0 -P3307 -uroot -e "ALTER USER 'root'@'%' IDENTIFIED BY '1';FLUSH PRIVILEGES;"
```

Now you can connect to MySQL service inside of container using the following command:
```
mysql -h0.0.0.0 -P3307 -uroot -p1
```

###### Notice
All databases will be permanently stored in `/var/lib/docker/volumes/mysqldata/_data` folder. By default you will not be able to get access to that folder: you have to add "read" credentials. 
