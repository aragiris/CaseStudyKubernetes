# CaseStudyKubernetes
Edureka Case study for Kubernetes YAML script

-----
## deploy-backend.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
    name: mongo
spec:
    replicas: 1
    selector:
      matchLabels:
        app: mongo
    template:
      metadata:
        labels:
          app: mongo
      spec:
        containers:
        - name: mongo
          image: mongo
          ports:
            - containerPort: 27017
           
## front-end.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: front-end
spec:
  replicas: 1
  selector:
      matchLabels:
        app: front-end
  template:
    metadata:
      labels:
        app: front-end
    spec:
      containers:
        - name: front-end
          image: devopsedu/employee
          ports:
            - containerPort: 8888
