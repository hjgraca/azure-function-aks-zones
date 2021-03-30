### Azure Functions demo
Deployed to AKS and triggered by Azure Service Bus

#### How to build and run
```func new```

```func init --docker-only```

```func start```

#### Build and push docker

```docker build < image name:tag >:< tag > .```

```docker push < image name:tag >:< tag >```

#### Kubernetes

Using [topologySpreadConstraints](https://kubernetes.io/docs/concepts/workloads/pods/pod-topology-spread-constraints/)

```yaml
topologySpreadConstraints:
        - maxSkew: 1
          topologyKey: topology.kubernetes.io/zone 
          whenUnsatisfiable: ScheduleAnyway
          labelSelector:
            matchLabels:
              app: sb-trigger
```



Replace placeholders and run:

```kubectl apply -f deploy.yaml```