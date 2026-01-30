
---

# 📘 Chapter 10: Alerting Concepts & Alertmanager

---

## 10.1 What is Alerting?

**Alerting** is the process of **notifying engineers when a system requires attention** based on defined conditions.

In simple words:

> **Alerting answers:**
> “Who needs to act right now?”

Alerts are **signals for human intervention**.

---

## 10.2 Monitoring vs Alerting

| Monitoring             | Alerting          |
| ---------------------- | ----------------- |
| Continuous observation | Action-triggering |
| Dashboards & metrics   | Notifications     |
| Passive                | Active            |
| Always on              | Only when needed  |

📌 Interview Tip:

> Not every metric needs an alert.

---

## 10.3 What Makes a Good Alert?

A good alert:

* Indicates **user impact**
* Is **actionable**
* Has **clear severity**
* Avoids noise

📌 Golden Rule:

> Alert on symptoms, not causes.

---

## 10.4 Common Alert Types

### 🔹 Availability Alerts

* Service down
* Endpoint unreachable

📌 Example:

> Health check failing

---

### 🔹 Performance Alerts

* High latency
* Slow response times

📌 Example:

> P95 latency > 2s

---

### 🔹 Error Alerts

* Increased error rate
* Failed requests

📌 Example:

> HTTP 5xx errors > 5%

---

### 🔹 Saturation Alerts

* Resource exhaustion

📌 Example:

> Disk usage > 90%

---

## 10.5 Alert Severity Levels

Common severity levels:

| Level    | Meaning                   |
| -------- | ------------------------- |
| Critical | Immediate action required |
| Warning  | Needs attention           |
| Info     | Informational             |

📌 Best Practice:

> Not everything is critical.

---

## 10.6 Alert Fatigue (Very Important)

**Alert fatigue** occurs when:

* Too many alerts
* Non-actionable alerts
* Repeated alerts

📌 Consequences:

* Alerts ignored
* Slower response
* Missed incidents

📌 Solution:

* Fewer, better alerts

---

## 10.7 Alertmanager (Prometheus Component)

**Alertmanager** handles alerts sent by Prometheus.

### Responsibilities:

* Group alerts
* Deduplicate alerts
* Silence alerts
* Route notifications

📌 Alertmanager **does not evaluate alerts**—Prometheus does.

---

## 10.8 Alert Flow (Prometheus → Alertmanager)

1. Prometheus evaluates alert rules
2. Alert is triggered
3. Alert sent to Alertmanager
4. Alertmanager processes alert
5. Notification sent (Slack, Email, PagerDuty)

---

## 10.9 Alert Routing & Grouping

Alertmanager can:

* Route alerts based on labels
* Group related alerts
* Send to different teams

📌 Example:

> DB alerts → Database team
> App alerts → Dev team

---

## 10.10 Silences & Maintenance Windows

Silences:

* Temporarily suppress alerts
* Used during maintenance

📌 Best Practice:

> Silence alerts before planned downtime.

---

## 10.11 Alerting Best Practices (Interview Gold)

* Alert on user impact
* Use SLO-based alerts
* Avoid static thresholds
* Include runbooks
* Test alerts regularly

---

## 10.12 Alerting in DevOps Day-to-Day

* Respond to production alerts
* Acknowledge incidents
* Investigate root cause
* Improve alert rules
* Reduce noise over time

---

## 10.13 Key Takeaways (Interview-Friendly)

* Alerts trigger human action
* Alertmanager manages notifications
* Good alerts reduce MTTR
* Alert fatigue is dangerous
* Alerts should be actionable

---

## 🔑 One-Line Interview Answer

> **Alerting is the process of notifying teams when systems breach defined conditions, and Alertmanager handles alert routing, grouping, and notifications.**

---

## 📌 Must-Remember Interview Statement

> **If an alert wakes you up, it must be worth waking up for.**

---