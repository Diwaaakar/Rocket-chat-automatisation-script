
# $ aws configure
# Terraform configuration
# $ mkdir learn-terraform-aws-instance
# $ cd learn-terraform-aws-instance
# $ touch main.tf


terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.27"
    }
  }

  required_version = ">= 0.14.9"
}

# For launching Ec2 instances 
Provider ¨aws¨ {
Profile = ¨dafault¨
region  = ¨us-west-2¨ 
}
resource ¨aws_instance¨ ¨example.fi¨{
ami  = ¨ami--830c94e3¨
instance_type = ¨t2-micro¨
}
tags = {
    Name = "ExampleAppServerInstance"
  }
}


# As the rocket chat was already deployed on aws so only need to do the automatisation


# Initialise the directory 
# $ terraform init

# Create infrastructure 
# $ terraform plan

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

# $ terraform apply

# for deleting 
# $ terraform destroy
