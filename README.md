FROM matteofigus/docker-sqitch
LABEL Name=mysql-sqitch-demo Version=0.0.1
RUN mkdir usr/src/sqitch
ENTRYPOINT bash

# run sqitch commands:

## Initialize
```bash
docker run -it -v ~/Projects/mysql-sqitch-demo/src:/src docteurklein/sqitch:mysql init --uri https://github.com/teom10/mysql-sqitch-demo.git demo-mysql
```

