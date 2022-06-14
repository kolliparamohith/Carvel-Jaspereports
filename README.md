# Carvel-Jaspereports

JasperReports Server is a stand-alone and embeddable reporting server. It is a central information hub, with reporting and analytics that can be embedded into web and mobile applications.

## Configuration Reference

You can configure the following:

### JasperReports parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.registry|JasperReports image registry|string|docker.io|
|image.repository|JasperReports image repository|string|bitnami/jasperreports|
|image.tag|JasperReports image tag (immutable tags are recommended)|string|8.0.0-debian-10-r33|
|image.pullPolicy|JasperReports image pull policy|string|IfNotPresent|
|jasperreportsUsername|JasperReports user|string|jasperadmin|
|jasperreportsPassword|JasperReports password|string|""|
|jasperreportsEmail|JasperReports user email|string|user@example.com|
|allowEmptyPassword|Set to yes to allow the container to be started with blank passwords|string|no|
|smtpHost|SMTP host|string|""|
|smtpPort|SMTP port|string|""|
|smtpEmail|SMTP email|string|""|
|smtpUser|SMTP user|string|""|
|smtpPassword|SMTP password|string|""|
|smtpProtocol|SMTP protocol [ssl,none]|string|""|
|extraEnvVarsCM|Name of existing ConfigMap containing extra env vars|string|""|
|extraEnvVarsSecret|Name of existing Secret containing extra env vars|string|""|
|updateStrategy.type|StrategyType|string|RollingUpdate|

### Jasperreports deployment parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|containerPorts.http|HTTP port to expose at container level|integer|8080|
|podSecurityContext.enabled|Enable pod's Security Context|string|true|
|podSecurityContext.fsGroup|Set pod's Security Context fsGroup|integer|1001|
|containerSecurityContext.enabled|Enable container's Security Context|string|true|
|containerSecurityContext.runAsUser|Set container's Security Context runAsUser|integer|1001|
|containerSecurityContext.runAsNonRoot|Set container's Security Context runAsNonRoot|string|true|
|resources.limits|The resources limits for the Jasperreports container|string|{}|
|resources.requests|The requested resources for the Jasperreports container|string|{}|
|startupProbe.enabled|Enable startupProbe|string|false|
|startupProbe.path|Request path for startupProbe|string|/jasperserver/login.html|
|startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|450|
|startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|startupProbe.failureThreshold|Failure threshold for startupProbe|integer|6|
|startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|livenessProbe.enabled|Enable livenessProbe|string|true|
|livenessProbe.path|Request path for livenessProbe|string|/jasperserver/login.html|
|livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|450|
|livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|6|
|livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|readinessProbe.enabled|Enable readinessProbe|string|true|
|readinessProbe.path|Request path for readinessProbe|string|/jasperserver/login.html|
|readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|30|
|readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|5|
|readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|6|
|readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|customStartupProbe|Override default startup probe|string|{}|
|customLivenessProbe|Override default liveness probe|string|{}|
|customReadinessProbe|Override default readiness probe|string|{}|
|podLabels|Extra labels for Jasperreports pods|string|{}|
|podAnnotations|Annotations for Jasperreports pods|string|{}|
|podAffinityPreset|Pod affinity preset. Ignored if affinity is set. Allowed values: soft or hard|string|""|
|podAntiAffinityPreset|Pod anti-affinity preset. Ignored if affinity is set. Allowed values: soft or hard|string|soft|
|nodeAffinityPreset.type|Node affinity preset type. Ignored if affinity is set. Allowed values: soft or hard|string|""|
|nodeAffinityPreset.key|Node label key to match. Ignored if affinity is set.|string|""|
|affinity|Affinity for pod assignment|string|{}|
|nodeSelector|Node labels for pod assignment|string|{}|
|priorityClassName|JasperReports pods' priorityClassName|string|""|
|schedulerName|Name of the k8s scheduler (other than default)|string|""|
|lifecycleHooks|LifecycleHooks to set additional configuration at startup.|string|{}|
|persistence.enabled|Enable persistence using PVC|string|true|
|persistence.storageClass|PVC Storage Class for Jasperreports volume|string|""|
|persistence.accessModes|Persistent Volume Access Mode|string|["ReadWriteOnce"]|
|persistence.size|PVC Storage Request for Jasperreports volume|integer|8Gi|
|persistence.existingClaim|An Existing PVC name for Jasperreports volume|string|""|
|persistence.annotations|Persistent Volume Claim annotations|string|{}|

### Exposure parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|service.type|Kubernetes Service type|string|Kubernetes Service type|
|service.ports.http|Service HTTP port|integer|80|
|service.nodePorts.http|Kubernetes http node port|string|""|
|service.clusterIP|Jarperreports service Cluster IP|string|""|
|service.loadBalancerIP|Kubernetes LoadBalancerIP to request|string|""|
|service.externalTrafficPolicy|Enable client source IP preservation|string|Cluster|
|service.annotations|Annotations for Jasperreports service|string|{}|
|service.sessionAffinityConfig|Additional settings for the sessionAffinity|string|{}|
|ingress.enabled|Enable ingress controller resource|string|false|
|ingress.pathType|Ingress path type|string|ImplementationSpecific|
|ingress.apiVersion|Force Ingress API version (automatically detected if not set)|string|""|
|ingress.hostname|Default host for the ingress resource|string|jasperreports.local|
|ingress.path|Ingress path|string|/|
|ingress.annotations|Additional annotations for the Ingress resource. To enable certificate autogeneration, place here your cert-manager annotations|string|{}|
|ingress.tls|Enable TLS configuration for the hostname defined at ingress.hostname parameter|string|false|
|ingress.ingressClassName|IngressClass that will be be used to implement the Ingress (Kubernetes 1.18+)|string|""|

### Database parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|mariadb.enabled|Whether to use the MariaDB chart|string|true|
|mariadb.architecture|MariaDB architecture (standalone or replication)|string|standalone|
|mariadb.auth.rootPassword|Password for the MariaDB root user|string|""|
|mariadb.auth.database|Database name to create|string|bitnami_jasperreports|
|mariadb.auth.username|Database user to create|string|bn_jasperreports|
|mariadb.auth.password|Password for the database|string|""|
|mariadb.primary.persistence.enabled|Enable database persistence using PVC|string|true|
|mariadb.primary.persistence.storageClass|PVC Storage Class|string|""|
|mariadb.primary.persistence.accessModes|Access mode of persistent volume|string|["ReadWriteOnce"]|
|mariadb.primary.persistence.size|Database Persistent Volume Size|integer|8Gi|
|mariadb.primary.persistence.hostPath|Host mount path for MariaDB volume|string|""|
|mariadb.primary.persistence.existingClaim|Enable persistence using an existing PVC|string|""|
|externalDatabase.existingSecret|Name of the database existing Secret Object|string|""|
|externalDatabase.host|Host of the existing database|string|""|
|externalDatabase.port|Port of the existing database|integer|3306|
|externalDatabase.user|Existing username in the external db|string|bn_jasperreports|
|externalDatabase.password|Password for the above username|string|""|
|externalDatabase.database|Name of the existing database|string|bitnami_jasperreports|

### NetworkPolicy parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|networkPolicy.enabled|Enable network policies|string|false|
|networkPolicy.ingress.enabled|Enable network policy for Ingress Proxies|string|false|
|networkPolicy.ingress.namespaceSelector|Ingress Proxy namespace selector labels. These labels will be used to identify the Ingress Proxy's namespace|string|{}|
|networkPolicy.ingress.podSelector|Ingress Proxy pods selector labels. These labels will be used to identify the Ingress Proxy pods|string|{}|
|networkPolicy.ingressRules.backendOnlyAccessibleByFrontend|Enable ingress rule that makes the backend (mariadb) only accessible by Jasperreports' pods|string|false|
|networkPolicy.ingressRules.customBackendSelector|Backend selector labels. These labels will be used to identify the backend pods.|string|{}|
|networkPolicy.ingressRules.accessOnlyFrom.enabled|Enable ingress rule that makes Jasperreports only accessible from a particular origin|string|false|
|networkPolicy.ingressRules.accessOnlyFrom.namespaceSelector|Namespace selector label that is allowed to access Jasperreports. This label will be used to identified the allowed namespace(s)|string|{}|
|networkPolicy.ingressRules.accessOnlyFrom.podSelector|Pods selector label that is allowed to access Jasperreports. This label will be used to identified the allowed pod(s).|string|{}|
|networkPolicy.ingressRules.customRules|Custom network policy ingress rule|string|{}|
|networkPolicy.egressRules.denyConnectionsToExternal|Enable egress rule that denies outgoing traffic outside the cluster, except for DNS (port 53)|string|false|
|networkPolicy.egressRules.customRules|Custom network policy rule|string|{}|
