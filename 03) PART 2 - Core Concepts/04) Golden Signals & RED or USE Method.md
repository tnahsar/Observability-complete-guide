
---

# 📘 Chapter 7: Golden Signals & RED / USE Method

---

## 7.1 Why Monitoring Methodologies Matter

Modern systems generate **thousands of metrics**.

Without a strategy:

* Dashboards become noisy
* Alerts become useless
* Important issues are missed

📌 Monitoring methodologies help you:

* Focus on what matters
* Reduce alert fatigue
* Detect user-impacting issues fast

---

## 7.2 The Golden Signals (Google SRE)

Google SRE defined **four Golden Signals** to monitor any user-facing system.

### 1️⃣ Latency

* Time taken to serve a request
* Most important user experience metric

📌 Example:

> API response time > 2s

---

### 2️⃣ Traffic

* How much demand the system is handling
* Requests per second

📌 Example:

> Sudden traffic spike after a campaign

---

### 3️⃣ Errors

* Requests that fail
* Includes application & system errors

📌 Example:

> HTTP 5xx error rate increased

---

### 4️⃣ Saturation

* How “full” the system is
* Resource exhaustion indicator

📌 Example:

> CPU usage near 100%, queue full

---

## 7.3 Why Golden Signals Are Powerful

* Cover both **performance and reliability**
* User-centric
* Technology agnostic
* Easy to explain in interviews

📌 Interview Tip:

> Start monitoring with Golden Signals before anything else.

---

## 7.4 RED Method (Request-Focused Monitoring)

The **RED Method** is ideal for **microservices and APIs**.

### RED stands for:

### 🔹 R – Rate

* Requests per second

### 🔹 E – Errors

* Failed requests

### 🔹 D – Duration

* Time taken per request

📌 Example:

> API request rate ↑, error rate ↑, latency ↑

---

## 7.5 When to Use RED Method

Best for:

* HTTP services
* APIs
* Microservices
* Load-balanced services

📌 RED is essentially a **refinement of Golden Signals** for services.

---

## 7.6 USE Method (Resource-Focused Monitoring)

The **USE Method** focuses on **infrastructure resources**.

### USE stands for:

### 🔹 U – Utilization

* Percentage of time resource is busy

### 🔹 S – Saturation

* Queue length or backlog

### 🔹 E – Errors

* Resource-level errors

📌 Example:

> Disk I/O saturation causing delays

---

## 7.7 When to Use USE Method

Best for:

* Servers
* Nodes
* Storage
* Network interfaces

📌 USE helps identify **resource bottlenecks**.

---

## 7.8 Golden Signals vs RED vs USE

| Method         | Focus Area       | Best For       |
| -------------- | ---------------- | -------------- |
| Golden Signals | User experience  | Overall system |
| RED            | Request behavior | Microservices  |
| USE            | Resource health  | Infrastructure |

📌 Interview Line:

> Use RED for services and USE for resources.

---

## 7.9 Real-World Monitoring Strategy

1. Start with **Golden Signals**
2. Apply **RED** for applications
3. Apply **USE** for infrastructure
4. Add custom business metrics

📌 This approach prevents metric overload.

---

## 7.10 Key Takeaways (Interview-Friendly)

* Golden Signals are SRE best practice
* RED focuses on services
* USE focuses on resources
* Together they form a complete monitoring strategy
* Help reduce alert fatigue

---

## 🔑 One-Line Interview Answers

**Golden Signals:**

> Four key metrics—latency, traffic, errors, and saturation—that indicate system health and user experience.

**RED Method:**

> A monitoring approach focusing on request rate, errors, and duration for services.

**USE Method:**

> A resource monitoring approach focusing on utilization, saturation, and errors.

---

## 📌 Must-Remember Interview Statement

> **Monitor what users experience first, then drill down into resources.**

---