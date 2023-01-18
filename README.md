Expose multiple svc in different namespaces, which are using same elb using ingress group.
I'm using AWS cloud and EKS cluster.

1. Create two namespaces
2. Deploy deployment and svc in each of the namespaces
3. Create ingress resource in each of the namespace, which create elb and specify the same group name in both the ingress
4. NOTE: Change namespaces, certificate-arn, host, path, svc name accordingly
5. Update DNS records of ELB to your host

To run the same manifest,
Create EKS cluster,
Run namespace file. #kubectl apply -f ns.yaml
Run both the hello-beta and hello-prod file
#kubectl apply -f beta.yaml
#kuectl apply -f prod.yaml

In ingress file, comment  annotations of 'certificate arn' if you don't have any ssl certificate.
Change you hostname
Upadte your host entry in your route53 or any other dns provider
