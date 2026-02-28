
---

# 📘 Chapter 13: Observability in Kubernetes

---

## 13.1 Why Observability is Critical in Kubernetes

Kubernetes is:

* Highly dynamic
* Distributed
* Declarative
* Ephemeral

📌 Challenges:

* Pods restart frequently
* Containers are short-lived
* IPs change constantly
* Many layers (node, pod, service)

➡️ Traditional monitoring **fails** in Kubernetes.

---

## 13.2 What Needs to Be Observed in Kubernetes

Kubernetes observability spans **multiple layers**:

1. Cluster level
2. Node level
3. Pod & container level
4. Application level
5. Control plane level

---

## 13.3 Kubernetes Metrics Categories

### 🔹 Node Metrics

* CPU usage
* Memory usage
* Disk pressure
* Network I/O

📌 Tool:

> Node Exporter

---

### 🔹 Pod & Container Metrics

* CPU & memory per container
* Restart count
* Resource limits & requests

📌 Tool:

> cAdvisor

---

### 🔹 Kubernetes State Metrics

* Pod status
* Deployment replicas
* Job completion
* Node conditions

📌 Tool:

> kube-state-metrics

---

## 13.4 Key Kubernetes Metrics to Monitor (Interview-Focused)

* Pod restart count
* CrashLoopBackOff
* Node NotReady
* CPU / memory throttling
* OOMKilled events
* Deployment availability

📌 These metrics indicate **real problems**.

---

## 13.5 Kubernetes Logging

### Logging Challenges

* Containers are ephemeral
* Logs disappear when pods restart

### Best Practice

* Applications log to stdout/stderr
* Log collectors capture logs

📌 Kubernetes Logging Flow:

> App → stdout → Fluent Bit → Elasticsearch → Kibana

---

## 13.6 Kubernetes Distributed Tracing

Tracing helps:

* Understand service-to-service calls
* Debug latency across pods
* Analyze network issues

📌 Common Tools:

* Jaeger
* OpenTelemetry

---

## 13.7 Kubernetes Control Plane Monitoring

Control plane components:

* API Server
* Scheduler
* Controller Manager
* etcd

📌 Monitor:

* API server latency
* etcd disk usage
* Leader election failures

---

## 13.8 Observability Architecture in Kubernetes

Typical stack:

* Prometheus → metrics
* Grafana → dashboards
* Fluent Bit → logs
* Elasticsearch → log storage
* Jaeger / OTel → traces

📌 All three pillars must work together.

---

## 13.9 Common Kubernetes Observability Issues

* Missing metrics after pod restart
* High cardinality labels
* Noisy logs
* Misconfigured alerts

📌 Solution:

> Follow Kubernetes observability best practices.

---

## 13.10 Kubernetes Observability Best Practices

* Monitor Golden Signals
* Use labels carefully
* Centralize logs
* Enable tracing
* Set resource limits
* Use SLO-based alerts

---

## 13.11 Kubernetes Observability in DevOps Day-to-Day

* Monitor cluster health
* Debug pod crashes
* Analyze latency issues
* Investigate scaling behavior
* Respond to alerts

---

## 13.12 Key Takeaways (Interview-Friendly)

* Kubernetes is dynamic
* Observability is mandatory
* Metrics, logs & traces are all required
* kube-state-metrics is critical
* Prometheus is standard

---

## 🔑 One-Line Interview Answer

> **Kubernetes observability provides visibility into cluster, node, pod, and application behavior using metrics, logs, and traces.**

---

## 📌 Must-Remember Interview Statement

> **Running Kubernetes without observability is flying blind.**

---