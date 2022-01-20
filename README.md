# nginx proxy-app that forwards all /tokenx/*-reqs to pam-samtykke-api

This app makes tokenx enabled endpoints in pam-samtykke-api reachable from GCP
without the use of API gateway.

(We cannot expose the entire pam-samtykke-api directly in GCP, because only a
subset of its endpoints meet the tokenx security requirements.)

## Reachability

Ingresses for this app are setup externally in:

https://github.com/navikt/bigip-iac/tree/main/pub-fss

Dev ingress: https://pam-samtykke-api-tokenx-proxy.dev-fss-pub.nais.io

Prod ingress: https://pam-samtykke-api-tokenx-proxy.prod-fss-pub.nais.io
