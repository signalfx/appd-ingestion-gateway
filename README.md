# OpenTelemetry Ingestion Gateway for AppDynamics

This is the release repository. It does not host source code. It contains only release artifacts for the AppDynamics OpenTelemetry Ingestion Gateway (OTIG).

## Overview

OTIG is an ingestion and translation gateway built on the OpenTelemetry Collector. It receives OpenTelemetry data using native OpenTelemetry protocols and semantics, then translates that data into AppDynamics Controller-specific data models through the AppDynamics exporter. This makes OpenTelemetry data, including traces and metrics, available in the Controller UI while preserving familiar AppDynamics concepts such as Business Transactions and Tiers.

## Downloads

Download the package for your architecture from [Releases](https://github.com/signalfx/appd-ingestion-gateway/releases):

- `*_binary-package.zip` includes the `otelcol-appd` binary for standalone execution.
- `*_docker-image-package.zip` includes a saved container image.

Both packages include configuration files and a README with deployment instructions. The docker package in addition contains a kubernetes manifest. GitHub-generated **Source code** archives contain the files in this release repository.

## Release license

Software is provided "as is" under the [Splunk AppDynamics Licnese](LICENSE). The same `LICENSE` is included in the packages and at `/opt/appdynamics/licenses/LICENSE` in the container image.

## Verify downloads

Download `checksums.txt` and `checksums.txt.asc` from the same release as your package. The checksum manifest is signed by Splunk, Inc. (`release@splunk.com`). Use GnuPG and the [Splunk public signing key](https://docs.splunk.com/images/6/6b/SplunkPGPKey.pub), whose primary fingerprint is:

```text
58C3 3310 B7A3 54C1 279D B669 5EFA 01ED B3CD 4420
```

From the download directory, retrieve the key and confirm its fingerprint matches the value above:

```sh
curl --fail --location --output SplunkPGPKey.pub https://docs.splunk.com/images/6/6b/SplunkPGPKey.pub
gpg --show-keys --with-fingerprint SplunkPGPKey.pub
```

Import the key and verify the checksum manifest's signature:

```sh
gpg --import SplunkPGPKey.pub
gpg --verify checksums.txt.asc checksums.txt
```

Continue only after a good signature from the Splunk key above. On Linux, verify the downloaded files:

```sh
sha256sum --ignore-missing --check checksums.txt
```

On macOS, use `shasum -a 256 --ignore-missing --check checksums.txt`. Require an `OK` result for each downloaded package before extracting or using it.

## Prerequisites

Before deploying the Collector-Exporter, ensure your environment meets these requirements from the [Splunk AppDynamics OTIG documentation](https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring/26.4.0/opentelemetry-ingestion-gateway-for-appdynamics)

- **Controller:** AppDynamics On-Premises or SaaS Controller from version 26.4.0.
- **Deployment environment:** AppDynamics On-Premises Virtual Appliance (VA) or cSaaS.
- **Operating system:** Amazon Linux, Red Hat Enterprise Linux (RHEL), or a Debian-based distribution.
- **Architecture:** `amd64` (`x86_64`) or `arm64` (`aarch64`).
- **Kubernetes:** Version 1.20 or later, with `kubectl` and Docker installed.

Consult the linked documentation for recommended resource sizing and deployment instructions for your workload.