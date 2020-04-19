# ckad Preparation

## YAML definition

YAML

Kind	Version
POD	v1
Service v1
ReplicaSet apps/v1
Deployment apps/v1

## PODs
   create a pod with run command: <code> kubectl run --generator=run-pod/v1 nginx --image=nginx</code>

## scale replicaset
 k scale rs rs1 --replicas=5
