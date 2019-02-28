# Hue Prod Docker

TODO: unify with current [Hue docker](/tools/docker).

```
cd tools/docker/hue-prod

git clone https://github.com/cloudera/hue.git
cd hue
git checkout -b origin/release-latest
cd ..
```

Build and push:

```
sudo docker build . -t gethue/hue:release-latest
sudo docker push gethue/hue:release-latest
```

Update the Hue pods:

```
kubectl delete pods `kubectl get pods | grep hue | grep -v postgres | cut -d" " -f1`
```