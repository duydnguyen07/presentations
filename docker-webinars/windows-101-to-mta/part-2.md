
# Dockerizing .NET Applications

## App V1

Build V1 using MSI:

```
cd \part-2\v1

docker image build -t web .
```

Run SQL Server & app:

```
docker run -d --name db -e ACCEPT_EULA=Y --env-file db-credentials.env microsoft/mssql-server-windows-express

docker run -d -P --env-file db-credentials.env web
```

## App V2

Run from pre-public images:

```
cd \part-2\v2

docker-compose -f .\app\docker-compose-v2.yml up -d

docker inspect app_web_1
```

## App V3

Upgrade from public images:

```
docker-compose -f .\app\docker-compose-v3.yml up -d

docker inspect app_web_1
```

