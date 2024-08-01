# DOCKER DB
``` 
docker run --name postgres12golang -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres:13 
```
# CONNECT TO DB
```
docker exec -it postgres12golang psql -U root
```

# CREATE A MIGRATION FILE
```
migrate create -ext sql -dir [folder] -seq [schema name]
```
### EXAMPLE
```
migrate create -ext sql -dir db/migration -seq init_schema
```

## RUN A MIGRATION SCRIPT
```
migrate -path db/migration -database "postgresql://[USERNAME]:[PASSWORD@localhost:5432/simple_bank?sslmode=disable" -verbose up
```

### EXAMPLE
```
migrate -path db/migration -database "postgresql://root:secret@localhost:5432/simple_bank?sslmode=disable" -verbose up
``

# SQLC
USES 
- ```sqlc generate``` - generate a new sqlc

# CREATE OUR MODULE
`go mod [github project url]`
install dependencies `go mod tidy`

after install docker

docker exec -it postgres12 psql -U root

install golang-migrate
brew install golang-migrate

Generate migration files
inside db folder
migrate create -ext sql dir db/migration -seq init_schema

Migrate Tables
migrate -path db/migration -database "postgresql://root:secret@localhost:5432/simple_bank?sslmode=disable" -verbose up

Install SQLC
brew install sqlc

make sqlc

go mod init github.com/ivanxtr/simplebank
go mod tidy

go get github.com/lib/pq
go get github.com/s
tretchr/testify

