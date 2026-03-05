
---

# **Observability: Before and After OpenTelemetry**

## **Before OpenTelemetry**

Before OpenTelemetry, developers used **vendor-specific SDKs** separately for logs, metrics, and traces.

**Examples of vendors:**

* **Logs:** Elasticsearch, Splunk, Dynatrace
* **Metrics:** InfluxDB, Dynatrace
* **Tracing:** Jaeger, Zipkin

This created a significant challenge: if an organization wanted to switch observability vendors, developers had to **re-instrument the application code** for that particular signal—or for all three signals if changing vendors for the entire observability stack. This was **time-consuming and error-prone**.

OpenTelemetry was introduced to solve this problem. It provides **vendor-neutral APIs and SDKs** for logs, metrics, and traces. Developers can instrument their applications **once** using OpenTelemetry and later select or change vendors by **reconfiguring exporters or collectors**, without modifying application code.

---

## **How OpenTelemetry fits with vendors**

### Before OpenTelemetry

```text
App → Vendor-specific SDK → Vendor backend
```

### With OpenTelemetry

```text
App → OpenTelemetry SDK → Exporter → Any vendor
```

---

### **Vendors with first-class OpenTelemetry support**

* Datadog
* New Relic
* Dynatrace
* Splunk
* Grafana Cloud
* Honeycomb
* Lightstep
* Elastic

---

## **Important nuances**

Even though many vendors support OpenTelemetry:

* They may still provide **proprietary SDKs**.
* OpenTelemetry is the **recommended approach** for portability across vendors.
* Some advanced features may remain **vendor-specific**.

---

## **One-line summary (interview-ready)**

> **Logs, metrics, and traces were historically vendor-specific. OpenTelemetry unified instrumentation, allowing applications to send telemetry to any observability vendor without code changes.**

---