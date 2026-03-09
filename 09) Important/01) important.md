Totally fair confusion — Datadog feels like magic until you see **who collects what and from where**. Let’s demystify it layer by layer 🧩

Think of Datadog as **one Agent, multiple data sources**.

---

# Big Picture (one-line mental model)

**Datadog Agent runs on each node** ➜
it **pulls metrics from the OS, container runtime, kubelet, cAdvisor, Kubernetes API, and your apps** ➜
then sends them to Datadog.

---

# 1️⃣ Node / Host Metrics (VMs, bare metal, k8s nodes)

📍 **Source:**

* Linux kernel (/proc, /sys)
* System calls
* OS utilities

📦 **Collected by:**
**Datadog Agent (host mode)**

### Examples

* CPU: `system.cpu.user`, `system.cpu.idle`
* Memory: `system.mem.used`, `system.mem.free`
* Disk: `system.disk.used`, `system.io.read_bytes`
* Network: `system.net.bytes_rcvd`

👉 These are **host-level metrics**.
In Kubernetes, a **node = a host**.

---

# 2️⃣ Container Metrics (Docker / containerd)

📍 **Source:**

* Container runtime
* cgroups
* cAdvisor

📦 **Collected by:**
**Datadog Agent + container runtime socket**

### Examples

* CPU: `container.cpu.usage`
* Memory: `container.memory.usage`
* Network: `container.net.sent`
* IO: `container.io.read_bytes`

👉 This is **per-container resource usage**, regardless of Kubernetes.

---

# 3️⃣ Pod Metrics (Kubernetes abstraction)

📍 **Source:**

* cAdvisor
* Kubelet
* Kubernetes API Server

📦 **Collected by:**
**Datadog Agent running as a DaemonSet**

### Examples

* `kubernetes.pod.cpu.usage`
* `kubernetes.pod.memory.usage`
* `kubernetes.pod.restarts`
* `kubernetes.pod.ready`

👉 Pods are **grouped containers**, so these metrics are **aggregations + metadata**.

---

# 4️⃣ Cluster Metrics (Kubernetes control plane)

📍 **Source:**

* Kubernetes API Server
* kube-state-metrics

📦 **Collected by:**
**Datadog Cluster Agent**

### Examples

* `kubernetes.nodes.ready`
* `kubernetes.deployments.desired`
* `kubernetes.replicaset.available`
* `kubernetes.hpa.current_replicas`

👉 These are **state metrics**, not resource usage.

---

# 5️⃣ Application Metrics (your services)

This is where *you* come in.

## Option A: Auto-discovered integrations

📍 **Source:** App endpoints (e.g. `/metrics`)

Examples:

* NGINX
* Redis
* PostgreSQL
* Kafka

Collected via:

* Datadog integration checks
* OpenMetrics / Prometheus scrape

---

## Option B: Custom metrics (StatsD / DogStatsD)

📍 **Source:** Your app code

```text
request.count
request.latency
error.rate
```

Sent via:

* DogStatsD (UDP)
* OpenTelemetry
* Datadog SDKs

---

# 6️⃣ APM / Traces (not metrics, but related)

📍 **Source:** Instrumented app code

Examples:

* Request latency
* DB calls
* Error traces

Collected via:

* Datadog APM libraries
* Sent to Agent → Datadog

---

# Who Collects What (cheat table)

| Level       | Source                      | Collected By  |
| ----------- | --------------------------- | ------------- |
| Cluster     | K8s API, kube-state-metrics | Cluster Agent |
| Node        | OS / kernel                 | Node Agent    |
| Container   | cgroups / runtime           | Node Agent    |
| Pod         | kubelet / cAdvisor          | Node Agent    |
| App metrics | App endpoints / SDKs        | Agent         |
| Traces      | App instrumentation         | Agent         |

---

# Common “aha” moments

💡 **Datadog does NOT magically read your application metrics**
→ you must expose or emit them.

💡 **Pod metrics ≠ container metrics**
→ pods are logical groupings.

💡 **Cluster metrics are state, not performance**
→ desired vs running, ready vs not.

---

# TL;DR

* **Agent on node** → system + containers + pods
* **Cluster Agent** → Kubernetes state
* **Your app** → business & app metrics
* **Everything flows through the Agent**

If you want, tell me:

* EKS / AKS / GKE?
* Docker or containerd?
* What app (Java, Python, Node, Go)?

I’ll map **exact metric names** you should expect and where to find them in Datadog.
