### It is possible to setup cloud specific features on AWS LB.

* Create a certificate from AWS-Certificate-Manager

* It can be done with an annotation in a service(configure a cert and enable it)
* Annotations below are the ones that enables access logs on LB;
    "
    service.beta.kubernetes.io/aws-load-balancer-access-log-emit-interval
    service.beta.kubernetes.io/aws-load-balancer-access-log-enabled
    service.beta.kubernetes.io/aws-load-balancer-access-log-s3-bucket-name
    service.beta.kubernetes.io/aws-load-balancer-access-log-s3-bucket-prefix
    "
    To add resource tags;
    "
    service.beta.kubernetes.io/aws-load-balancer-additional-resource-tags
    "
    Backend protocol to use;
    "
    service.beta.kubernetes.io/aws-load-balancer-backend-protocol
    "
    Certificates;
    "
    service.beta.kubernetes.io/aws-load-balancer-ssl-cert   ARN
    "
    Connection Draining and Timeout;
    "
    service.beta.kubernetes.io/aws-load-balancer-connection-draining-enabled
    service.beta.kubernetes.io/aws-load-balancer-connection-draining-timeout
    service.beta.kubernetes.io/aws-load-balancer-connection-idle-timeout
    service.beta.kubernetes.io/aws-load-balancer-cross-zone-load-balancing-enabled
    "
    For extra security;
    "
    service.beta.kubernetes.io/aws-load-balancer-extra-security-groups
    "
    Configure LB;
    "service.beta.kubernetes.io/aws-load-balancer-internal = true
    service.beta.kubernetes.io/aws-load-balancer-proxy-protocol
    service.beta.kubernetes.io/aws-load-balancer-ssl-ports
    "

