## Using Skaffold for kustomize with Custom OpenAPI schema

Modified from https://github.com/kubernetes-sigs/kustomize/blob/master/examples/customOpenAPIschema.md. 

> Need to have kustomize v4.3.0 or greater installed

This `skaffold.yaml` file only defines a `kustomize` deploy stanza. The rendered manifest can be achieved by running:
```
skaffold render
```

Output:
```
❯ skaffold render                     
apiVersion: example.com/v1alpha1
kind: MyResource
metadata:
  name: service
spec:
  template:
    spec:
      containers:
      - command: example
        image: server
        name: server
        ports:
        - containerPort: 8080
          name: grpc
          protocol: TCP
```
