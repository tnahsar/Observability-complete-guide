
---

# Observability Vendors by Signal

## 1️⃣ Logs Vendors

These primarily store, index, and query **logs**.

### 🔹 Open-source / Self-hosted

* **Elasticsearch** (ELK / OpenSearch)
* **Grafana Loki**
* **Graylog**

### 🔹 Commercial / SaaS

* **Splunk**
* **Datadog Logs**
* **New Relic Logs**
* **Sumo Logic**
* **Dynatrace Logs**
* **Elastic Cloud**

---

## 2️⃣ Metrics Vendors

These focus on **time-series numeric data**.

### 🔹 Open-source / Self-hosted

* **Prometheus**
* **VictoriaMetrics**
* **InfluxDB**

### 🔹 Commercial / SaaS

* **Datadog Metrics**
* **New Relic Metrics**
* **Dynatrace**
* **Grafana Cloud Metrics**
* **Amazon CloudWatch Metrics**
* **Google Cloud Monitoring**
* **Azure Monitor Metrics**

---

## 3️⃣ Tracing Vendors

These specialize in **distributed tracing**.

### 🔹 Open-source / Self-hosted

* **Jaeger**
* **Zipkin**
* **Tempo (Grafana)**

### 🔹 Commercial / SaaS

* **Datadog APM**
* **New Relic APM**
* **Dynatrace**
* **Lightstep**
* **Honeycomb**
* **AWS X-Ray**

---

## 4️⃣ Unified Observability Platforms (Logs + Metrics + Traces)

Most modern vendors handle **all three signals**.

| Vendor               | Logs | Metrics | Traces |
| -------------------- | ---- | ------- | ------ |
| Datadog              | ✅    | ✅       | ✅      |
| New Relic            | ✅    | ✅       | ✅      |
| Dynatrace            | ✅    | ✅       | ✅      |
| Splunk Observability | ✅    | ✅       | ✅      |
| Grafana Cloud        | ✅    | ✅       | ✅      |
| Elastic              | ✅    | ✅       | ✅      |

---

## 5️⃣ Cloud-provider Native Vendors

| Cloud | Logs               | Metrics               | Traces               |
| ----- | ------------------ | --------------------- | -------------------- |
| AWS   | CloudWatch Logs    | CloudWatch Metrics    | X-Ray                |
| GCP   | Cloud Logging      | Cloud Monitoring      | Cloud Trace          |
| Azure | Azure Monitor Logs | Azure Monitor Metrics | Application Insights |

---
