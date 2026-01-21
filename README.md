# Observo-Preflight-Check

A helpful shell script to run before a POC to ensure your VM is able to download and install all dependancies. 


### The Observo Site installer requires communication to download dependencies. As many environments are bespoke, this simple test will ensure your VM is able to communicate with external systems. 

#### A list of requried ports can be found here. 
- https://docs.observo.ai/6S3TPBguCvVUaX3Cy74P/deployment/sizing-and-compute-cost-planning/ports-protocols

##### If you need specific URLs, see this list below: 

- get.k3s.io:443
- update.k3s.io:443
- github.com:443
- release-assets.githubusercontent.com:443
- get.helm.sh:443
- auth.docker.io:443
- registry-1.docker.io:443
- production.cloudflare.docker.com:443
- quay.io:443
- cdn01.quay.io:443
- *.cloudfront.net:443 
 - public.ecr.aws:443
- *.ubuntu.com or any destination used to update/upgrade the OS components
- registry.k8s.io:443
- *.dkr.ecr.us-east-1.amazonaws.com:443
- prod-registry-k8s-io-eu-south-1.s3.dualstack.eu-south-1.amazonaws.com:443
- europe-west8-docker.pkg.dev:443
- prod-us-east-1-starport-layer-bucket.s3.us-east-1.amazonaws.com:443
