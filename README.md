# ckad Preparation

## YAML definition

YAML


Kind	| Version
--- | ---
POD	| v1
Service | v1
ReplicaSet | apps/v1
Deployment | apps/v1

## PODs
   create a pod with run command: 
      <code> kubectl run --generator=run-pod/v1 nginx --image=nginx</code>
   Create Manifest with --dry-run
   <code>kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml</code>
   

## scale replicaset
 <code>kubectl scale rs rs1 --replicas=5</code>
