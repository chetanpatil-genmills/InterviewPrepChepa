Okay, here's the information about managing Ingress Controllers in Google Kubernetes Engine (GKE) in English:

In Google Kubernetes Engine (GKE), you can manage Ingress Controllers using several options, with the most common and recommended approach being through the Google Cloud Load Balancer (GCLB). Similar to the ALB Controller in AWS, the GCLB Ingress Controller provides load balancing and external access to your Kubernetes cluster.

Google Cloud Load Balancer (GCLB) Ingress Controller:

Automatic Provisioning:

When you deploy an Ingress resource, GKE automatically creates a Google Cloud Load Balancer (GCLB).

This load balancer routes traffic to the nodes in your cluster.

GKE configures the load balancer based on the rules defined in your Ingress resource.

Layer 7 Load Balancing:

GCLB provides Layer 7 load balancing, which means it can understand and route HTTP/HTTPS traffic.

You can route traffic to different backend services based on hostnames, paths, and other HTTP headers.

SSL/TLS Termination:

GCLB supports SSL/TLS termination, which means you can upload your SSL certificates to Google Cloud, and GCLB will encrypt and decrypt your traffic.

This offloads the burden of encryption and decryption from your backend services.

Multiple Backends:

You can define multiple backend services in a single Ingress resource.

GCLB will route traffic to these backend services based on the rules you define.

Health Checks:

GCLB automatically performs health checks on your backend services.

If a service is unhealthy, GCLB will stop routing traffic to that service.

Global Load Balancing:

If you have GKE clusters in multiple regions, you can use GCLB to set up global load balancing.

GCLB will automatically route your users to the cluster closest to them.

How to Manage the Ingress Controller:

Define Ingress Resource:

Define your Ingress resource in a YAML file.

In this file, you need to define your hostnames, paths, and backend services.

Deploy Ingress Resource:

Deploy your Ingress resource using the command kubectl apply -f my-ingress.yaml.

Check GCLB:

In the Google Cloud Console, you can check the status and configuration of your GCLB.

Alternative Ingress Controllers:

Besides GCLB, you can also use other Ingress Controllers, such as:

NGINX Ingress Controller: This is a popular open-source Ingress Controller based on the NGINX web server.

HAProxy Ingress Controller: This is based on the HAProxy load balancer.

These Ingress Controllers need to be installed and configured manually, but they offer more flexibility and customization options compared to GCLB.

Summary:

The easiest and recommended way to manage Ingress Controllers in GKE is to use the Google Cloud Load Balancer (GCLB). GCLB automatically provides load balancing and external access for your Kubernetes cluster. If you need more flexibility and customization, you can use other Ingress Controllers, such as NGINX Ingress Controller or HAProxy Ingress Controller.
