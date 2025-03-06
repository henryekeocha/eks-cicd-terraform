# From Scratch to Production: Deploying EKS Clusters and Applications with CI/CD using Jenkins and Terraform

![alt text](image.png)

**GitHub Repository:** [https://github.com/henryekeocha/eks-cicd-terraform](https://github.com/henryekeocha/eks-cicd-terraform)

## **Introduction**  
This project provides a comprehensive guide to deploying **Amazon EKS clusters** and applications using a **CI/CD pipeline with Jenkins and Terraform**. It automates the infrastructure provisioning, application deployment, and continuous integration process, making it easy to scale and manage Kubernetes workloads on AWS.

### **Key Technologies Used:**  
- **Amazon Elastic Kubernetes Service (EKS)** – Managed Kubernetes on AWS  
- **Jenkins** – CI/CD automation server  
- **Terraform** – Infrastructure as Code (IaC) for AWS resources  
- **Docker** – Containerization for application packaging  
- **Kubernetes** – Orchestrating containerized applications  
- **AWS CLI & Kubectl** – Managing AWS and Kubernetes  

---

## **Features**  
✅ **Automated Infrastructure Deployment** – Terraform provisions AWS EKS clusters and related resources.  
✅ **CI/CD Pipeline with Jenkins** – Automates building, testing, and deploying applications to EKS.  
✅ **Secure & Scalable Deployment** – Uses best practices for security, networking, and autoscaling.  
✅ **Modular Codebase** – Well-structured Terraform configurations and Jenkins pipelines.  
✅ **End-to-End Workflow** – Covers setup from **scratch to production** in a **repeatable and scalable** way.  

---

## **Project Structure**  
```
eks-cicd-terraform/
│── jenkins_server/       # Jenkins setup and configurations
│── manifest/             # Kubernetes deployment and service manifests
│── tf-aws-eks/           # Terraform files for provisioning AWS EKS
│── Jenkinsfile           # Defines Jenkins pipeline
│── README.md             # Project documentation
│── image.png             # Banner or diagram for the project
```

### **Folder Breakdown:**  
- **`jenkins_server/`** – Scripts and configurations for setting up Jenkins.  
- **`manifest/`** – Kubernetes YAML files for application deployment.  
- **`tf-aws-eks/`** – Terraform configurations to create AWS EKS resources.  
- **`Jenkinsfile`** – Pipeline definition for automated CI/CD.  

---

## **Prerequisites**  
Ensure you have the following tools installed before proceeding:  

✅ **AWS CLI** - [Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)  
✅ **Terraform** - [Install Terraform](https://developer.hashicorp.com/terraform/downloads)  
✅ **Jenkins** - [Install Jenkins](https://www.jenkins.io/doc/book/installing/)  
✅ **Docker** - [Install Docker](https://docs.docker.com/get-docker/)  
✅ **Kubectl** - [Install Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)  
✅ **Helm (Optional)** - [Install Helm](https://helm.sh/docs/intro/install/)  

---

## **Installation & Setup**  

### **1️⃣ Clone the Repository**  
```sh
git clone https://github.com/henryekeocha/eks-cicd-terraform.git
cd eks-cicd-terraform
```

### **2️⃣ Configure AWS CLI**  
Ensure you have configured AWS credentials with the required permissions.  
```sh
aws configure
```

### **3️⃣ Deploy the EKS Cluster with Terraform**  
```sh
cd tf-aws-eks
terraform init
terraform apply -auto-approve
```

### **4️⃣ Verify the EKS Cluster**  
```sh
aws eks update-kubeconfig --name my-cluster --region us-east-1
kubectl get nodes
```

### **5️⃣ Set Up Jenkins Server**  
- Install **Jenkins** and required plugins (Pipeline, Kubernetes, Terraform).  
- Configure credentials for AWS and DockerHub.  

### **6️⃣ Deploy Application Using Jenkins Pipeline**  
- Modify the `Jenkinsfile` as needed.  
- Push changes to trigger CI/CD.  

---

## **CI/CD Workflow**  
### **🔄 Automated Deployment Process:**  
1. **Code Push** – Developer pushes changes to GitHub.  
2. **Jenkins Pipeline Execution** –  
   - Clones the repository  
   - Builds and tests the application  
   - Builds a Docker image and pushes it to a registry  
   - Deploys the application to EKS  
3. **Application is Live on Kubernetes** 🎉  

---

## **Terraform Infrastructure**  
Terraform is used to provision AWS infrastructure:  
- **VPC, Subnets, and Security Groups**  
- **EKS Cluster and Node Groups**  
- **IAM Roles and Policies for Kubernetes and Jenkins**  

To destroy resources:  
```sh
terraform destroy -auto-approve
```

---

## **Usage Guide**  

### **Accessing the Application**  
Once deployed, retrieve the service URL:  
```sh
kubectl get svc -n my-namespace
```

### **Scaling the Deployment**  
Increase replicas:  
```sh
kubectl scale deployment my-app --replicas=3
```

---

## **Troubleshooting**  

🔴 **Terraform Apply Fails?**  
- Ensure AWS credentials are correctly configured.  
- Check if Terraform is up-to-date.  

🔴 **Jenkins Pipeline Failing?**  
- Verify AWS and DockerHub credentials in Jenkins.  
- Check logs for missing dependencies.  

🔴 **Application Not Deploying?**  
- Verify `kubectl` is connected to the correct cluster.  
- Check Kubernetes logs:  
```sh
kubectl logs -f deployment/my-app
```

---

## **Contributing**  
I welcome contributions! To contribute:  
1. Fork the repo and create a new branch.  
2. Commit changes and push to your fork.  
3. Open a **Pull Request** with detailed explanations.  

---

🚀 **Now you're ready to deploy production-grade Kubernetes applications with Jenkins and Terraform!**  
