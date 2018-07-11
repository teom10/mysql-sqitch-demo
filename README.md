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
docs: https://github.com/sqitchers/sqitch/blob/master/lib/sqitchtutorial-mysql.pod

```bash
docker run -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql config --user engine.mysql.client /usr/local/mysql/bin/mysql
```

```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql config --user user.name 'Omar Teodoro Oropeza'
```
```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql config --user user.mail 'oteodoro@gbm.com.mx'
```

```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql add appuser -n 'Creates a an application user.'
```

```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/database:/src docteurklein/sqitch:mysql deploy db:mysql://root:123456@localhost:3306/CRM
```
