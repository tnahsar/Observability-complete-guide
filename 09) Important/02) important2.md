Nice summary 👌 — you’re **very close**. I’ll review it line-by-line, correct a few things, and fill the gaps **without changing your mental model**.

I’ll use **✅ correct**, **⚠️ tweak**, **❌ incorrect**, and **➕ add** so it’s easy to scan.

---

## 1️⃣ Observability pillars

> For observability we need three things: metrics, logs and traces

✅ **Correct**

Datadog also adds **profiles** and **RUM**, but the core 3 are right.

---

## 2️⃣ Metrics

### 2.1 System metrics

> Datadog agent collecting cluster metrics via kube-api-server and kube-state-metrics

⚠️ **Mostly correct – small clarification**

* **Cluster Agent** (not the node agent) collects:

  * Kubernetes **state metrics**
  * From **kube-api-server**
  * And **kube-state-metrics**

Examples:

* deployments desired vs available
* pod status
* HPA replicas

✅ Conceptually right.

---

> Datadog agent will collect worker node metrics from OS kernel

✅ **Correct**

* Source: Linux kernel (`/proc`, `/sys`)
* Metrics:

  * CPU, memory, disk, network
* In k8s: **node = host**

---

> Datadog agent will collect container metrics from container runtime and cAdvisor

✅ **Correct**

* Source:

  * container runtime (Docker / containerd)
  * cgroups
  * cAdvisor
* Metrics:

  * container CPU, memory, IO, network

---

> Datadog agent will collect pod metrics from kubelet

✅ **Correct**

* Source:

  * kubelet
  * cAdvisor
* Pod metrics are **aggregated container metrics + metadata**

---

### 2.2 Application metrics

> APM integration will collect application metrics

⚠️ **Partially correct (important nuance)**

APM **does collect some metrics**, but:

* APM **primarily collects traces**
* It **derives metrics from traces** (latency, error rate, throughput)

➕ **Application metrics actually come from 3 places:**

1. **APM-derived metrics**

   * request latency
   * error rate
   * request count

2. **Custom metrics**

   * DogStatsD
   * OpenTelemetry
   * Datadog SDKs

3. **Integration / Prometheus metrics**

   * `/metrics` endpoints
   * NGINX, Redis, DBs, etc.

💡 So:
**APM ≠ all application metrics**, but it’s one big source.

---

## 3️⃣ Logs

This is the part you were unsure about — let’s lock it in 🔒

### 3.1 System logs

> Don’t know how we collect

➕ **Here’s the answer**

**Datadog Agent collects logs by tailing files or container stdout/stderr**

Sources:

* `/var/log/*.log`
* systemd journal
* Kubernetes node logs
* Container logs (`stdout` / `stderr`)

How:

* Agent runs as a **DaemonSet**
* Reads logs on each node
* Sends them to Datadog Logs

Examples:

* kubelet logs
* node OS logs
* container runtime logs

---

### 3.2 Application logs

> I forgot

➕ **Same mechanism as system logs**

Two common ways:

#### Option 1: Container stdout/stderr (most common)

* App writes logs to console
* Kubernetes captures them
* Datadog Agent collects them

#### Option 2: Log files

* App writes to a file
* Agent tails that file

➕ Logs get **enriched automatically** with:

* pod name
* container name
* service
* environment
* version

---

## 4️⃣ Traces

> System and application traces will be collected by Tracer

⚠️ **Small correction**

* **There are no “system traces”**
* Traces are **application-level only**

Traces are collected by:

* Datadog APM libraries (Tracer)
* Sent to Datadog Agent
* Then to Datadog backend

Examples:

* HTTP requests
* DB queries
* External API calls

---

> if we need code information also in traces we need to install profiler

⚠️ **Almost correct — clarify purpose**

* **Tracer (APM)** → request flow, latency, errors
* **Profiler** → CPU usage, memory allocation, hot methods

They are:

* Independent
* Complementary

💡 You can have traces **without** profiler
💡 Profiler adds **code-level performance insights**

---

## 5️⃣ Clean corrected summary (final mental model)

Here’s your summary, **cleaned up but unchanged in spirit**:

> * Observability = metrics, logs, traces
> * System metrics:
>
>   * Cluster metrics collected by **Cluster Agent** via kube-api-server and kube-state-metrics
>   * Node metrics collected by **Agent** from OS kernel
>   * Container metrics collected by **Agent** from container runtime and cAdvisor
>   * Pod metrics collected by **Agent** from kubelet
> * Application metrics:
>
>   * Collected via **APM-derived metrics**, **custom metrics**, and **integrations**
> * Logs:
>
>   * System and application logs collected by **Agent** from log files or container stdout/stderr
> * Traces:
>
>   * Application traces collected by **APM Tracer**
>   * Profiler is optional and provides code-level performance data

✅ That is a **solid, correct Datadog mental model**.

If you want next:

* I can draw a **one-page diagram**
* Or map **Agent vs Cluster Agent vs Tracer** in one table
* Or explain **what to enable first in a real cluster**

Just say the word.
