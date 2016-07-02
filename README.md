# Arckaan: postgrest-service

Database logic powered by PostgreSQL and exposed by [postgrest](https://github.com/begriffs/postgrest)

Contains views and procedures to be called from a frontend app.

## Installation

- Clone this repo
- Install [postgrest](https://github.com/begriffs/postgrest) on your dev/production env
- Install [sqitch](https://github.com/theory/sqitch) in your local env

#### Configure skitch

```bash
sqitch config --user user.name 'Your Name'
sqitch config --user user.email 'your email'
sqitch target add production db:pg://[user]:[pass]@[rds url]:5432/[dbname]
sqitch config core.engine pg
sqitch config engine.pg.target production
sqitch config --bool deploy.verify true
sqitch config --bool rebase.verify true

# Deploy your changes
sqitch deploy
```

#### Launch postgrest

```bash
postgrest postgresql://[user]:[pass]@[rds url]:5432/[dbname] --anonymous default_role --jwt-secret secret
```
