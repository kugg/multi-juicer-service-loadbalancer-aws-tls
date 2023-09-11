# multi-juicer-service-loadbalancer-aws-tls
A terraform configuration for running multijuicer with a TLS front.

1. This configuration is based on the OWASP Multijuicer AWS EKS instructions [found here](https://github.com/iteratec/multi-juicer/blob/main/guides/aws/aws.md).
2. To make the EKS environment work for multi-juicer you must configure IAM policies for the environment. The instructions for policies can be [found here](https://eksctl.io/usage/minimum-iam-policies/).
3. A TLS certificate has to be available in the AWS ACM. To create a certificate follow the instructions [over at ACM](https://aws.amazon.com/certificate-manager/).
4. To set up TLS for multi-juicer in AWS replace the loadbalancer.yaml from multi-juicer with loadbalancer_https.yaml from this repository. Replace the ARN in the `service.beta.kubernetes.io/aws-load-balancer-ssl-cert` annotation with your ARN from ACM.
