To inject secrets into the API container, create a kubernetes secret with the following keys:

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

Then, pass the name of that secret to `.Values.api.secrets` in this helm chart.

For the web container, create a kubernetes secret with the following keys:

```
API_URL
GRPC_ENDPOINT
AUTH_AUDIENCE
AUTH_CLIENT_ID
AUTH_DOMAIN
AUTH0_ENABLED
OKTA_ENABLED
SAML_ENABLED
SENTRY_ENABLED
HOTJAR_ENABLED
HEAP_ENABLED
USERFLOW_ENABLED
USERFLOW_KEY
ENVIRONMENT
SHIELDRULE_ENVIRONMENT
DB_NAME
LAUNCHDARKLY_CLIENT_ID
```
Then, pass the name of that secret to `.Values.web.secrets` in this helm chart.

The optional `prerequisites-gcp` helm chart installs the External Secrets operator, which can optionally be used to sync secrets from GCP Secret Manager or AWS Secrets Manager..