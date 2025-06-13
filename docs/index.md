# abc Service Documentation

## Overview

A containerized Python Flask application that provides pod details and health status information. This service demonstrates cloud-native patterns including health checks, observability, and GitOps deployment.

## Quick Links

- **Live Service**: [abc.azurelaboratory.com](https://abc.azurelaboratory.com)
- **Health Check**: [/api/v1/healthz](https://abc.azurelaboratory.com/api/v1/healthz)
- **Argo CD**: [Application Status](https://argocd.azurelaboratory.com/applications/abc)
- **Source Code**: [GitHub Repository](https://github.com/rodmhgl/abc)

## Service Endpoints

### `/api/v1/details`

Returns detailed information about the running pod instance.

**Response Format:**

```json
{
  "time": "02:30PM on January 15, 2025",
  "hostname": "abc-7d4f8b9c-x8k2l",
  "message": "You are doing well, human!!"
}
```

**Use Cases:**

- Debugging pod-specific issues
- Verifying deployment success
- Load balancer health verification

### `/api/v1/healthz`

Standard Kubernetes health check endpoint.

**Response Format:**

```json
{
  "status": "up"
}
```

**Integration:**

- Used by Kubernetes liveness/readiness probes
- Monitored by external health checkers
- Part of service mesh health verification
