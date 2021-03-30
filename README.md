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
Replace placeholders and run:

```kubectl apply -f deploy.yaml```