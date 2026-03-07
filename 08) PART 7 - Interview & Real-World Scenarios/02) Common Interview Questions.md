
---

# 📘 Chapter 22: Common Interview Questions (Observability & Monitoring)

---

## 22.1 Monitoring vs Observability

**Q:** What is the difference between monitoring and observability?

**Answer:**

> Monitoring tells us **what is wrong** using predefined metrics and alerts, while observability helps us **understand why it is wrong** by analyzing metrics, logs, and traces together.

📌 Interview Tip:

* Monitoring = known problems
* Observability = unknown problems

---

## 22.2 How Do You Debug a Production Issue?

**Answer (Structured):**

1. Check alerts & dashboards (metrics)
2. Identify affected services
3. Check logs for errors
4. Use traces to find bottlenecks
5. Mitigate user impact
6. Perform RCA

📌 Shows calm, methodical thinking.

---

## 22.3 What Metrics Would You Monitor for an API?

**Answer:**

* Request rate (traffic)
* Error rate (4xx/5xx)
* Latency (P95/P99)
* Saturation (CPU, memory, thread pools)

📌 Mention Golden Signals.

---

## 22.4 How Do You Avoid Alert Fatigue?

**Answer:**

* Alert on SLO breaches
* Use symptom-based alerts
* Aggregate alerts
* Silence non-actionable alerts
* Use burn rate alerts

📌 Very strong senior-level answer.

---

## 22.5 Metrics vs Logs vs Traces

**Answer:**

> Metrics show trends and system health, logs provide detailed event context, and traces show request flow and latency across services.

📌 Bonus:

* Metrics detect
* Logs explain
* Traces connect

---

## 22.6 What is High Cardinality and Why Is It Bad?

**Answer:**

> High cardinality occurs when metrics have too many unique labels, which increases storage cost and reduces query performance in monitoring systems.

📌 Mention cost impact.

---

## 22.7 How Do You Monitor Kubernetes?

**Answer:**

* Cluster & control plane metrics
* Node metrics (node-exporter)
* Pod & container metrics (kubelet)
* Application metrics
* Centralized logs & traces

📌 Structured answers win interviews.

---

## 22.8 How Does Prometheus Work?

**Answer:**

> Prometheus scrapes metrics from exporters at regular intervals, stores them as time-series data, and uses Alertmanager for notifications.

---

## 22.9 What is OpenTelemetry?

**Answer:**

> OpenTelemetry is a vendor-neutral standard for collecting metrics, logs, and traces using common APIs, SDKs, and collectors.

📌 Say “vendor-neutral”.

---

## 22.10 How Do You Reduce Observability Costs?

**Answer:**

* Reduce metrics cardinality
* Control log volume
* Sample traces
* Set retention policies

📌 Shows production awareness.

---

## 22.11 What is an SLI, SLO, and SLA?

**Answer:**

* SLI measures service performance
* SLO defines reliability targets
* SLA is a customer-facing commitment

📌 Mention error budgets.

---

## 22.12 How Do You Perform RCA?

**Answer:**

> By correlating metrics, logs, and traces to identify the root cause and implementing preventive actions through blameless postmortems.

---

## 22.13 Observability in AWS?

**Answer:**

* CloudWatch for metrics & logs
* X-Ray for tracing
* CloudTrail for audit
* Hybrid with open-source tools

---

## 22.14 What is MTTR and How Do You Reduce It?

**Answer:**

> MTTR is the time to restore service, and it is reduced using good alerting, dashboards, correlation of observability signals, and runbooks.

---

## 22.15 Final Interview Power Statement

> **Observability enables faster incident response, better reliability, and informed engineering decisions by correlating metrics, logs, and traces.**

---

## 🎯 Congratulations 🎉

You now have:

* End-to-end observability knowledge
* Production-grade understanding
* Interview-ready answers
* Senior DevOps / SRE clarity

---