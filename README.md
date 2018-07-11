FROM matteofigus/docker-sqitch
LABEL Name=mysql-sqitch-demo Version=0.0.1
RUN mkdir usr/src/sqitch
ENTRYPOINT bash

# run sqitch commands:

## Initialize
```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql init demo-mysql --uri https://github.com/teom10/mysql-sqitch-demo.git --engine mysql
```

## Configuration

```bash
docker run -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql config --user engine.mysql.client /usr/local/mysql/bin/mysql
```

```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql config --user user.name 'Omar Teodoro Oropeza'
```

docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql config --user user.mail 'oteodoro@gbm.com.mx'