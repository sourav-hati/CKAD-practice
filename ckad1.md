CKAD Practice Questions (30)
Core Concepts
1.	Create a pod named `nginx-pod` running the image `nginx:1.19` and ensure it restarts only on failure.
2.	Check logs of a pod named `backend-pod` running in namespace `dev`. Show only the last 20 lines.
3.	Expose an existing deployment `myapp` on port `8080` as a ClusterIP service named `myapp-svc`.
Configuration
4.	Create a ConfigMap named `app-config` with two keys: `APP_ENV=production`, `APP_DEBUG=false`.
5.	Mount the above ConfigMap into a pod so that `APP_ENV` and `APP_DEBUG` appear as environment variables.
6.	Create a Secret named `db-secret` with keys: `username=admin`, `password=MyP@ssw0rd`.
7.	Update a deployment `api-deploy` to use the secret `db-secret` as environment variables.
Multi-Container Pods
8.	Create a pod named `sidecar-pod` with two containers:
   - `app` using `nginx`
   - `sidecar` using `busybox` running `tail -f /var/log/nginx/access.log`.
9.	Share a volume between both containers in the above pod for logs.
Observability
10.	Run a command to check CPU and memory usage of pods in `default` namespace.
11.	Get detailed description of pod `orders-pod` and filter only the events section.
12.	Troubleshoot a pod stuck in `CrashLoopBackOff`. What commands will you use?
Pod Design
13.	Create a deployment named `frontend` with 3 replicas using image `nginx:1.20`.
14.	Perform a rolling update on the deployment `frontend` to use `nginx:1.21`.
15.	Rollback the deployment `frontend` to the previous version.
16.	Create a job named `batch-job` using image `busybox` that runs `echo Hello CKAD` once.
17.	Create a cronjob named `daily-job` that runs at 1 AM daily to print `Backup started`.
Services & Networking
18.	Expose the `frontend` deployment as a NodePort service listening on port `30080`.
19.	Create an Ingress resource that routes traffic:
   - `/app1` → `app1-svc:8080`
   - `/app2` → `app2-svc:9090`.
20.	Verify DNS resolution of service `backend-svc` inside a pod using `nslookup`.
State Persistence
21.	Create a PersistentVolume of 1Gi storage using `hostPath: /mnt/data`.
22.	Create a PersistentVolumeClaim named `app-pvc` requesting 500Mi storage.
23.	Mount the PVC into a pod named `db-pod` at `/data/db`.
Security & RBAC
24.	Create a service account named `deploy-sa`.
25.	Create a pod `sa-pod` running nginx using the service account `deploy-sa`.
26.	Create a Role `pod-reader` in namespace `dev` allowing `get`, `list`, `watch` on pods.
27.	Bind the above Role to user `developer` with a RoleBinding.
Application Lifecycle
28.	Perform a `kubectl rollout pause` on deployment `frontend`, then resume it.
29.	Drain a node named `worker-1` safely before maintenance.
30.	Run a command to scale deployment `frontend` to 5 replicas.
