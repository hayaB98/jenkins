apiVersion: v1
kind: Pod
spec:
  containers: 
    - name: maven
      image: maven:3.5.4-jdk-8-slim
      command: ["tail", "-f", "/dev/null"] 
      imagePullPolicy: Always 
      resources:  
        requests:
          memory: "8Gi"
          cpu: "500m"
        limits:
          memory: "8Gi"
    - name: docker
      image: docker:18.06.1
      command: ["tail", "-f", "/dev/null"]
      imagePullPolicy: Always
      volumeMounts:
        - name: docker
          mountPath: /var/run/docker.sock
  volumes:
    - name: docker
      hostPath:
        path: /var/run/docker.sock
