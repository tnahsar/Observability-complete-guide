
---

# 📘 Chapter 16: SLIs, SLOs, SLAs & Error Budgets

---

## 16.1 Why SLIs/SLOs/SLAs Matter

Monitoring shows **what is happening**.
Observability explains **why it is happening**.

But businesses ask:

* *Is the system reliable enough?*
* *Are users satisfied?*
* *When do we stop deploying and fix stability?*

➡️ **SLIs, SLOs, SLAs answer these questions.**

---

## 16.2 Service Level Indicator (SLI)

### What is an SLI?

An **SLI** is a **quantitative measurement** of a service’s performance.

📌 Think of it as:

> **A metric that directly reflects user experience**

---

### Common SLIs

* Availability (% of successful requests)
* Latency (request response time)
* Error rate
* Throughput

📌 Example:

```
SLI = Successful HTTP requests / Total HTTP requests
```

---

### Good vs Bad SLIs

❌ Bad:

* CPU usage
* Memory utilization

✅ Good:

* Request success rate
* P95 latency

📌 Rule:

> SLIs must be **user-centric**, not infrastructure-centric.

---

## 16.3 Service Level Objective (SLO)

### What is an SLO?

An **SLO** is a **target value** or **range** for an SLI.

📌 Think of it as:

> **How reliable we want the service to be**

---

### Example SLOs

* 99.9% availability per month
* P95 latency < 300ms
* Error rate < 0.1%

📌 SLOs are **internal goals**, not customer promises.

---

## 16.4 Service Level Agreement (SLA)

### What is an SLA?

An **SLA** is a **contractual commitment** to customers.

📌 If breached → penalties / credits.

---

### SLA vs SLO

| SLA          | SLO          |
| ------------ | ------------ |
| External     | Internal     |
| Legal        | Engineering  |
| Penalties    | No penalties |
| Conservative | Aggressive   |

📌 Best Practice:

> SLOs should be **stricter** than SLAs.

---

## 16.5 Relationship Between SLI, SLO, SLA

```
Metric → SLI → SLO → SLA
```

Example:

* Metric: HTTP response time
* SLI: P95 latency
* SLO: P95 < 300ms
* SLA: 99.5% monthly uptime

---

## 16.6 Error Budget (Most Important Concept)

### What is an Error Budget?

An **error budget** is the **allowed amount of unreliability**.

```
Error Budget = 100% − SLO
```

Example:

* SLO = 99.9%
* Error Budget = 0.1%

---

### Error Budget in Time

Monthly:

* 99.9% SLO ≈ 43 minutes downtime
* 99.99% SLO ≈ 4.3 minutes downtime

📌 Error budget gives teams **permission to fail safely**.

---

## 16.7 Why Error Budgets Are Powerful

Error budgets balance:

* Innovation (deploy fast)
* Stability (avoid outages)

📌 Rules:

* Budget remaining → deploy freely
* Budget exhausted → stop features, fix reliability

---

## 16.8 Error Budgets in DevOps & CI/CD

Real-world usage:

* Block deployments if error budget exhausted
* Trigger reliability reviews
* Prioritize tech debt

📌 This creates **data-driven DevOps decisions**.

---

## 16.9 Implementing SLIs & SLOs (Practical)

### Step-by-Step:

1. Identify user journeys
2. Select meaningful SLIs
3. Set realistic SLOs
4. Monitor continuously
5. Alert on SLO burn rate

---

## 16.10 SLO Alerting (Burn Rate Alerts)

Instead of alerting on:

* CPU spikes
* Pod restarts

Alert on:

* Fast error budget burn
* Slow error budget burn

📌 This avoids alert fatigue.

---

## 16.11 Example (End-to-End)

Service:

* E-commerce checkout

SLIs:

* Request success rate
* P95 latency

SLOs:

* 99.95% success rate
* P95 < 400ms

Error Budget:

* 0.05% failures per month

Actions:

* Burn fast → incident
* Burn slow → investigate

---

## 16.12 Common Mistakes (Interview Gold)

❌ Using infra metrics as SLIs
❌ Setting unrealistic SLOs (100%)
❌ Alerting on everything
❌ Ignoring error budgets

---

## 16.13 Key Takeaways (Interview-Friendly)

* SLIs measure user experience
* SLOs define reliability targets
* SLAs are legal promises
* Error budgets enable safe innovation

---

## 🔑 One-Line Interview Answer

> **SLIs measure service performance, SLOs define reliability targets, SLAs are customer commitments, and error budgets define how much failure is acceptable.**

---

## 📌 Must-Remember Statement

> **Error budgets turn reliability into a business decision.**

---