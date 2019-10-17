pipeline {
    agent any

    stages {
        stage('Create Kubernetes Cluster') {
            eksctl create cluster \
                --name cloudcapstone \
                --version 1 \
                --nodegroup-name standard-workers \
                --node-type t2.micro \
                --nodes 2 \
                --nodes-min 1 \
                --nodes-max 2 \
                --node-ami auto
        }
        stage('Create Configuration File') {
            aws eks \
              --region \
              --us-west-2 \
              --update-kubeconfig \
              --name cloudcapstone
        }
      }
    }
