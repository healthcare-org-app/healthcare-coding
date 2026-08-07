# coding-service

coding-service — domain: billing

- **Port:** 8702
- **Language:** Python 3.11 + Flask
- **Database:** `billing` (Postgres, table `coding`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/coding/`          |
| POST      | `/api/coding/`          |
| GET       | `/api/coding/<id>`      |
| PUT/PATCH | `/api/coding/<id>`      |
| DELETE    | `/api/coding/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `diagnosis-codes-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
