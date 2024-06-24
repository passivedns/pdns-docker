# Development environment setup

## Installation and Setup

```bash
./init.sh
```

```bash
git checkout -b <branch-name>

```

## Running the application

```bash
docker-compose up
```

## Runing web server and frontend

In api container:

```bash
poetry run uvicorn passiveDNS.webserver:app --reload --host 0.0.0.0 --port 8080
```

In frontend container:

```bash
npm install && npm run dev
```

## Add a User to admin

In API container:

```bash
../docker-entrypoint.sh create-user Admin admin passivedns.dev@gmail.com --admin

```
