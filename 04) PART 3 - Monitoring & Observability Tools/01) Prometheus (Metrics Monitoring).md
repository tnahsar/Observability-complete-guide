
---

# 📘 Chapter 8: Prometheus (Metrics Monitoring)

---

## 8.1 What is Prometheus?

**Prometheus** is an **open-source metrics monitoring and alerting system** designed for **cloud-native and dynamic environments**.

In simple words:

> **Prometheus collects, stores, queries, and alerts on metrics.**

Originally developed at **SoundCloud**, now part of **CNCF**.

---

## 8.2 Why Prometheus is So Popular

Prometheus is widely used because:

* Built for microservices
* Works well with Kubernetes
* Pull-based metrics collection
* Powerful query language (PromQL)
* Simple and reliable

📌 Industry Standard:

> Prometheus is the default metrics solution in Kubernetes.

---

## 8.3 Prometheus Architecture (High-Level)

Main components:

1. **Prometheus Server**

   * Scrapes metrics
   * Stores time-series data
   * Evaluates alert rules

2. **Targets**

   * Applications exposing metrics

3. **Exporters**

   * Convert system/app data into Prometheus format

4. **Alertmanager**

   * Handles alerts & notifications

5. **Grafana** (Visualization)

---

## 8.4 Pull-Based Metrics Collection

Prometheus uses a **pull model**.

📌 How it works:

* Applications expose `/metrics` endpoint
* Prometheus scrapes metrics at intervals

📌 Benefits:

* Better reliability
* Easy service discovery
* No dependency on agents pushing data

---

## 8.5 Exporters (Very Important)

Exporters expose metrics for systems that don’t natively support Prometheus.

### Common Exporters:

* Node Exporter → OS metrics
* kube-state-metrics → Kubernetes state
* cAdvisor → Container metrics
* MySQL Exporter → Database metrics

📌 Interview Tip:

> Exporters translate metrics into Prometheus format.

---

## 8.6 Prometheus Data Model

Metrics consist of:

* Metric name
* Labels (key-value pairs)
* Timestamp
* Value

📌 Example:

```
http_requests_total{method="GET",status="200"} 1024
```

📌 Labels enable flexible querying but increase cardinality.

---

## 8.7 PromQL (Query Language)

PromQL is used to:

* Query metrics
* Create dashboards
* Define alert rules

📌 Examples:

* CPU usage
* Request rate
* Error percentage

📌 PromQL is **declarative**, not procedural.

---

## 8.8 Alerting with Prometheus

Prometheus:

* Evaluates alert rules
* Sends alerts to Alertmanager

Alertmanager:

* Groups alerts
* Deduplicates alerts
* Sends notifications (Slack, Email, PagerDuty)

📌 Best Practice:

> Alert on symptoms, not causes.

---

## 8.9 Prometheus in Kubernetes

Prometheus automatically:

* Discovers pods and services
* Scrapes dynamic targets
* Adapts to scaling

📌 Common setup:

> Prometheus + Alertmanager + Grafana

---

## 8.10 Limitations of Prometheus

* Short-term storage
* No built-in long-term retention
* High cardinality issues
* Single-node by default

📌 Solutions:

* Thanos
* Cortex
* Mimir

---

## 8.11 Prometheus in DevOps Day-to-Day

* Monitor application health
* Create dashboards
* Configure alerts
* Investigate incidents
* Capacity planning

---

## 8.12 Key Takeaways (Interview-Friendly)

* Prometheus is metrics-focused
* Pull-based model
* Strong Kubernetes integration
* Uses PromQL
* Foundation for modern monitoring

---

## 🔑 One-Line Interview Answer

> **Prometheus is an open-source monitoring system that collects and stores time-series metrics using a pull-based model and supports powerful querying and alerting.**

---

## 📌 Must-Remember Interview Statement

> **Prometheus is not just a monitoring tool—it’s a metrics database with alerting capabilities.**

---