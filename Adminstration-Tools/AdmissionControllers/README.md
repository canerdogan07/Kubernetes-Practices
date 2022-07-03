### Adminssion controllers are used to intercept requests that are sent to kubernetes API server.

* The interception happens after the user is authenticated(token or certificate) and authorized(RBAC)

* Also happens before the object saved in the backend

* Can be enabled by administrator and added at cluster creation by kube-apiserver: " kube-apiserver --enable-admission-plugins= defaults
  NamespaceLifecycle
  LimitRanger
  ServiceAccount
  DefaultStorageClass
  DefaultTolerationSeconds
  NodeRestriction
  MutatingAdmissionWebhook
  ValidatingAdmissionWebhook
  RecourceQuota
  PodSecurityPolicy(is explained in the folder)
  "

