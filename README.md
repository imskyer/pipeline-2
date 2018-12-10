# pipeline
Repository that contains al Knative pipeline artifacts

## Create Build Service Account Credentials
Replace user name and password with appropriate values and run the command below

```
kubectl apply -f build-service-acct-creds.yaml
```

## Create Build Service account
Next we will need to create the build service account. Run command below to create it

```
kubectl apply -f build-service-acct.yaml
```

## Build query service
At this point we should be able to build the query service. Since the build for query leverages a shareable knative CI build template be sure to create it before running the build.

```
kubectl apply -f build-query.yaml
```

### Checking build
Run command below to check the status of build

```
kubectl get builds -o yaml
```

## Build Indexer service
Run the command below to build the indexer service.

```
kubectl apply -f build-indexer.yaml
```

