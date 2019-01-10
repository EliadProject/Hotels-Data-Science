# Hotels-Data-Science
Classification and clustering data of hotels reservation to produce conclusions and decsions

# Spark using Docker

1. install `cifs` using:

```
sudo apt-get install cifs-utils
```

2. mount a remote notebook using:

```
sudo mount -t cifs -o username<your_username>,password=<your_password>,uid=<your_user_id>,gid=<your_group_id> //<host_ip>/<your_path> /mnt/<your_directory>
```

3. install `Docker` using

```
sudo apt update
```

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

```
sudo apt-get update
sudo apt-get install docker-ce
```

4. run spark container using:

```
docker run --name pyspark --user root -p 8888:8888 -d -e NB_USER=<your_user> -e CHOWN_HOME=yes -e CHOWN_HOME_OPTS='-R' -e GRANT_SUDO=yes -v /mnt/<your_path>:/home/<your_user>/work -w /home/$NB_USER jupyter/pyspark-notebook
```
