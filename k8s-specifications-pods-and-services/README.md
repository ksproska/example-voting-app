# Simplest kubernetes deployment
![](./../architecture.excalidraw.png)

The most basic components of the kubernetes architecture are pods, 
each component of the architecture (vote, result, redis, db and worker) is run
from the docker image inside the separate pod.

## Services for databases
UI applications (vote and result) as well as worker apps require connection to databases
(redis and db), therefore those services need to be accessed by service.

The service types are default (`ClusterIP`), meaning:
> Exposes the Service on a cluster-internal IP. 
> Choosing this value makes the Service only reachable from within the cluster. 
> This is the default that is used if you don't explicitly specify a type for a Service. 
> You can expose the Service to the public internet using an Ingress or a Gateway.

This enables internal communication without exposing services externally.

## Services for UI applications
UI applications (vote and result) need to be available for end user as external services,
therefore services need to be created with external access.

The service type is set therefore to `NodePort`, meaning:
> Exposes the Service on each Node's IP at a static port (the NodePort). 
> To make the node port available, Kubernetes sets up a cluster IP address, 
> the same as if you had requested a Service of type: ClusterIP.

After running `minikube service <service-name> --url` the ip with port number under which service is available will be displayed.
If under `ports` the `nodePort` is not specified the random value from the specific range will be assigned:

> If you set the type field to NodePort, 
> the Kubernetes control plane allocates a port from a range 
> specified by --service-node-port-range flag (default: 30000-32767). 
> Each node proxies that port (the same port number on every Node) into your Service. 
> Your Service reports the allocated port in its .spec.ports[*].nodePort field.

## Sources
[Kubernetes documentation - service types](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)
