## List of changes made to the helm charts

- Removed External-secrets and replaced with SecretProviderClass to sync KeyVault with K8s secret
- Removed nginx ingress helm install as we will be using Application Gateway ingress controller
- ingress.yaml updated ingressClassName set to azure-application-gateway, removed tls section and using SSL cert uploaded to keyvault
- Removed cert manager issuer as KeyVault uploaded cert will be used
- Removed PersistentVolume as its not used in the statefulset.
- Removed ServiceAccount, role and rolebinding creation as duplo autocreates a Service account for the tenant. This is referred in statefulset
