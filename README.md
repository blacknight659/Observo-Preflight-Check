# Observo-Preflight-Check

A helpful shell script to run before a POC to ensure your VM is able to download and install all dependencies. Information will support an Observo Proof of Concept. While production will share similar requirements, it is best to validate with your Observo account team before entering production.

### Reference Architecture

![Observo Architecture](https://514451292-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fsm4MnqGTVzcqoII0M7Mx%2Fuploads%2Fgit-blob-b8380599321be2c6671fd88d19c60c6e5721a83e%2Fobservo%20saas%20detail.drawio.png?alt=media)



# Your VM must freely communicate to both the Manager and the Install files. Allowing communication to the resources below is required.


### Manager to Site Communication
**Observo Manager** The manager is the UI and control plane of your Observo deployment. The URLs and IPs below will allow communication from your self-hosted Site(s) to the Observo SaaS Manager hosted by Observo (SaaS/Hybrid deployment types).

**Outgoing traffic from a self-hosted site (VM/K8s):**

| Endpoint | Port | Description |
| :--- | :--- | :--- |
| `sb-metrics.observo.ai` | 443 | Sends Observo Site metrics to the Manager/UI |
| `sb-logs.observo.ai` | 443 | Sends Observo Site logs to the Manager/UI |
| `sb-api.observo.ai` | 443 | Primary API Endpoint for the Manager (used for site configuration) |
| `sb-auth.observo.ai` | 443 | Authentication for the Site |

**Incoming traffic from the Manager to site (VM/K8s):**

| IP Address | Description |
| :--- | :--- |
| `3.22.184.24` | Nat Gateway IP: Your site will receive updates from this IP |

### Site to Installer Communication
**Observo Site** is the Data Plane and is responsible for receiving, processing, and routing data. The information below is useful for VM-based deployments which are considered self-hosted sites. Your VM will need open communication to these ports.

A list of required ports can be found in our documentation here:
- https://docs.observo.ai/6S3TPBguCvVUaX3Cy74P/deployment/sizing-and-compute-cost-planning/ports-protocols

#### Required URLs
If you need specific URLs for whitelisting, please utilize the list below:

```text
get.k3s.io:443
update.k3s.io:443
github.com:443
release-assets.githubusercontent.com:443
get.helm.sh:443
auth.docker.io:443
registry-1.docker.io:443
production.cloudflare.docker.com:443
quay.io:443
cdn01.quay.io:443
*.cloudfront.net:443
public.ecr.aws:443
*.ubuntu.com (or any destination used to update/upgrade the OS components)
registry.k8s.io:443
*.dkr.ecr.us-east-1.amazonaws.com:443
prod-registry-k8s-io-eu-south-1.s3.dualstack.eu-south-1.amazonaws.com:443
europe-west8-docker.pkg.dev:443
prod-us-east-1-starport-layer-bucket.s3.us-east-1.amazonaws.com:443
