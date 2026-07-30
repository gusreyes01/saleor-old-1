# Contributing

This fork preserves the application and GraphQL behavior of a 2019 Saleor
release. Keep fixes focused and backwards-compatible. A runtime or framework
upgrade should be proposed separately with a migration and rollback plan.

## Development setup

The pinned development stack is:

- Python 3.7.3
- Django 2.2.4
- Node.js 10.15.2 and npm 6
- PostgreSQL, Redis, and Elasticsearch as configured in `docker-compose.yml`

Docker Compose is the simplest way to provide the required services. Copy and
adjust the environment values in `common.env` for local use; never put
production credentials in that file.

Install the locked Python and JavaScript dependencies in an isolated
environment:

```sh
python -m pip install -r requirements.txt -r requirements_dev.txt
npm ci
```

## Validation

Before opening a pull request, run the checks relevant to the change:

```sh
flake8 saleor tests
python -m compileall -q saleor tests
npm run build-assets
pytest
```

The complete pytest suite expects the backing services configured by the test
settings. Add regression tests for behavior changes and describe schema,
deployment, and data-migration effects in the pull request.
