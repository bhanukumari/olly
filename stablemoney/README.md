## Introduction


Observability helps understand system behavior via logs, metrics, and traces. It's key for reliability and debugging in microservices. This guide covers setting up an observability stack in Kubernetes using modern tools.


## Core Components of Observability

- **Metrics**:  Quantitative data like CPU usage, memory, latency, and request rates to monitor system performance.

- **Logging**: Event records capturing errors and info messages for context, debugging, and auditing.

- **Traces**: End-to-end request flow across services, revealing latency, bottlenecks, and dependencies.

## Observability Stack (011y) – Prerequisites

![alt text](image-2.png)

![alt text](image-4.png)

## Tools Used in Observability Setup

- **VictoriaMetrics**: High-performance time-series database for storing and querying metrics.

- **Loki**: Scalable log aggregation system for collecting and storing logs efficiently.

- **Alertmanager**: Manages alerts from metrics or logs and notifies relevant teams of system issues.

- **Tempo**: Distributed tracing system for visualizing request flows across microservices.

## Deployment Method

The observability stack is deployed using Helm charts, providing a standardized, repeatable, and scalable approach for managing all components efficiently within the Kubernetes environment.


## Step-by-Step Installation

1 . **VictoriaMetrics Setup**

Clone the Repository and navigate to the VictoriaMetrics Directory

```
git clone https://github.com/ot-client/stablemoney/blob/o11y/README.md

cd VictoriaMetrics
```

## Open the Makefile and Execute Commands

![alt text](image-5.png)

## Verification
- Switch to the Monitoring Namespace
```
kubectl config set-context --current --namespace=monitoring
```
- Check Resources: 
```
kubectl get all -n monitoring 
```

This ensures the successful creation of all required resources in the monitoring namespace.

## Expected output:
![alt text](image-6.png)
![alt text](image-7.png)

2 .  **Logging Setup (Loki)**

Navigate to the Logging Folder

**Open the Makefile and Execute Commands**

![alt text](image-8.png)

## Verification:

```
kubectl config set-context --current --namespace=logging 
```

- Check Resources: 

```
kubectl get all -n logging
```

## Expected Output

![alt text](image-9.png)

3 . **OpenTelemetry (OTel) Setup**

Navigate to OpenTelemetry Folder

**Open the Makefile and Execute Commands**

![alt text](image-10.png)

## Verification:

```
kubectl config set-context --current --namespace=observability
```

```
kubectl get all -n observability
```

## Expected Output

![alt text](image-11.png)


4 . **Tempo Setup**

Navigate to Tempo Folder

**Open the Makefile and Execute Commands**

![alt text](image-12.png)

## Verification:

```
kubectl config set-context --current --namespace=observability
```

```
kubectl get all -n observability
```
## Expected Output

![alt text](image-13.png)




