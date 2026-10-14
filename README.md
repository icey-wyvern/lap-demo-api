# LAP demo API

A tiny workload for demonstrating [Local Application Platform](https://github.com/icey-wyvern/local-application-platform) deployment and rollback.

`success` serves `ok` at `/health`. `unhealthy` passes Kubernetes readiness but fails LAP's external health check, triggering rollback.

Run the healthy branch locally:

```sh
docker build -t lap-demo-api:success .
docker run --rm -p 127.0.0.1:8080:8080 lap-demo-api:success
curl --fail http://127.0.0.1:8080/health
```
