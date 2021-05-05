# Rocket-chat-automatisation-script
apiVersion: apps/v1
kind: Deployment
metadata:
  creationTimestamp: null
  labels:
    app: node-js
  name: node-js
  namespace: app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: node-js
  strategy: {}
  template:
    metadata:
      creationTimestamp: null
      labels:
        app: node-js
    spec:
      containers:
      - image: diwaaakar2205/sample-nodejs-app
        name: node-js-hello
        resources:
          requests:
            cpu: "0.5"
            memory: "500Mi"
          limits:
            cpu: "0.5"
            memory: "500Mi"
status: {}
