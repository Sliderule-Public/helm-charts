This helm chart expects one kubernetes secret to be passed to the helm chart. The secret should contain the following keys:

```
POSTGRES_USER
POSTGRES_PASSWORD
PROMETHEUS_ACCESS_TOKEN
POSTGRES_PORT
USE_AUTH_0
USE_INSTANCE_PROFILE
USE_SQS
USE_REDIS
DOCUMENT_STORE_TYPE
NO_DB_STARTUP
POSTGRES_USE_GCP
READ_WRITE_SSL_MODE
READ_WRITE_SSL_ROOT_CERT
READ_WRITE_SSL_CLIENT_CERT
READ_WRITE_SSL_CLIENT_KEY
AWS_REGION
API_URL
METRICS_NAMESPACE
POSTGRES_DB
POSTGRES_HOST
POSTGRES_PORT
PUB_SUB_TOPIC_ID
SHIELDRULE_ENVIRONMENT
```

The secret can be named anything, as long as it's in the same namespace as the helm chart installation and is passed to `.Values.api.secrets` and `.Values.web.secrets` in the `values.yaml` file.