
# DENNE APPLIKASJONEN ER ARKIVERT
pam-samtykke-api har flyttet til GCP, og vi trenger ikke lenger en tokenx-proxy

# nginx proxy-app that forwards all /tokenx/*-reqs to pam-samtykke-api

This app makes tokenx enabled endpoints in pam-samtykke-api reachable from GCP
without the use of API gateway.

(We cannot expose the entire pam-samtykke-api directly in GCP, because only a
subset of its endpoints meet the tokenx security requirements.)

It only forwards request with path prefix `/tokenx`, and for those it targets
path `/pam-samtykke-api/tokenx` on `pam-samtykke-api`.

## Reachability

Ingresses for this app are setup externally in:

https://github.com/navikt/bigip-iac/tree/main/pub-fss

Dev ingress: https://pam-samtykke-api-tokenx-proxy.dev-fss-pub.nais.io

Prod ingress: https://pam-samtykke-api-tokenx-proxy.prod-fss-pub.nais.io
