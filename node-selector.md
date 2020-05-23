first we need to label a node
```
kubectl label nodes <nodename> key=value
kubectl label nodes node01 size=small
```

now that we have label the node we can assig node-selector

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  labels:
    env: test
spec:
  containers:
  - name: nginx
    image: nginx
    imagePullPolicy: IfNotPresent
  nodeSelector:
    size: small
```


*** NodeSelector are limited because we cannot provide complex expressions like 
"Size NOT small" or
"Size Medium or Large"

For this we can use NodeAffinity

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: disktype
            operator: In
            values:
            - ssd            
  containers:
  - name: nginx
    image: nginx
    imagePullPolicy: IfNotPresent
```
The new node affinity syntax supports the following operators: In, NotIn, Exists, DoesNotExist, Gt, Lt
