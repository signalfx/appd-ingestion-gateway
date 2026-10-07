# OpenTelemetry Ingestion Gateway for AppDynamics

This is the release repository for the `appd-collector-exporter` project. It does not host source code. It contains only release artifacts for the AppDynamics OpenTelemetry Ingestion Gateway (OTIG).

## Overview

OTIG is an ingestion and translation gateway built on the OpenTelemetry Collector. It receives OpenTelemetry data using native OpenTelemetry protocols and semantics, then translates that data into AppDynamics Controller-specific data models through the AppDynamics exporter. This makes OpenTelemetry data, including traces and metrics, available in the Controller UI while preserving familiar AppDynamics concepts such as Business Transactions and Tiers.

## Prerequisites

Before deploying the Collector-Exporter, ensure your environment meets these requirements from the [Splunk AppDynamics OTIG documentation](https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring/26.4.0/opentelemetry-ingestion-gateway-for-appdynamics):

- **Controller:** AppDynamics SaaS or On-Premises. The documentation lists version 26.4.0 compatibility; 25.10.0 is the minimum version, while Node-level visibility and Metrics Browser support require 26.4.0.
- **Deployment environment:** AppDynamics On-Premises Virtual Appliance (VA) or cSaaS.
- **Operating system:** Amazon Linux, Red Hat Enterprise Linux (RHEL), or a Debian-based distribution.
- **Architecture:** `amd64` (`x86_64`) or `arm64` (`aarch64`).
- **Kubernetes:** Version 1.20 or later, with `kubectl` and Docker installed.

Consult the linked documentation for recommended resource sizing and deployment instructions for your workload.
