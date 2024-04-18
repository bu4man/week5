|NAME|PROMPT|DESCRIPTION|EXAMPLE|
-----|------|-----------|-------|
|Pod|create pod for application "app" using image "gcr.io/k8s-k3s/demo:v1.0.0" and set labels "app" and "run" as demo, set http port 8080|Pod creation|app.yaml|
|Liveness probe|create liveness probe for the same pod|Add liveness probe|app-livenessProbe.yaml|
|Readiness probe|create readiness probe which checks /ready path on port 8000, period 2, 3 failures and 1 success as threshold|Add readiness probe|app-readinessProbe.yaml|
|Volume|add volume data to be mounted as /data with local path /var/lib/app|Add volume to pod|app-volumeMounts.yaml|
|Cronjob|add cronjob - every 5 minutes to execute echo Hello, world|Add cronjob|app-cronjob.yaml|
|Job|add a job to rsync using gsutil from glow-sportradar to /data/input|Create job to sync data in google cloud with pod|app-job.yaml|
|Multicontainer|create pod with 2 containers - nginx and debian, both having volume HTML. debian adds current time every second to index.html|Create pod with 2 containers|app-multicontainer.yaml|
|Pod with resource limit|create pod using image gcr.io/kuar-demo/kuard-amd64:1, liveness probe on /healthy, readiness probe on /ready, port 8080 for both. limits and requests set as CPU to 100m, ram to 128Mi. fail/success threshold as 3/1|Create pod with resource limits|app-resources.yaml|
|App secret|create pod with ENV  SECRET_USERNAME/SECRET_PASSWORD from secrets mysecret1 having username/password|Pass username/password from secrets as ENV|app-secret-env.yaml|
