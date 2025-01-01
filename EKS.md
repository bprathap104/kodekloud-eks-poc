# Amazon EKS (Elastic Kubernetes Service) Learning Guide

## 1. Fundamental Concepts

### Kubernetes Basics
- **Control Plane**: The brain of Kubernetes that manages the cluster
  - API Server: Entry point for all REST commands
  - etcd: Distributed key-value store for cluster data
  - Scheduler: Places containers based on resource requirements
  - Controller Manager: Maintains desired state
  - Cloud Controller Manager: Integrates with AWS services

### Container Concepts
- **Container Runtime**: Usually containerd or Docker
- **Container Images**: Packaged applications and dependencies
- **Container Registries**: Amazon ECR or other container repositories
- **Pod**: Smallest deployable unit in Kubernetes
- **Container Networking**: How containers communicate

## 2. EKS Architecture

### Control Plane Components
- **EKS Managed Control Plane**
  - AWS manages high availability
  - Automatic version updates
  - Multi-AZ deployment
  - Integrated with AWS services
  - Managed etcd cluster

### Worker Nodes
- **Node Types**
  - Managed Node Groups
  - Self-managed nodes
  - Fargate pods
- **Node Components**
  - kubelet
  - kube-proxy
  - Container runtime
  - AWS VPC CNI plugin

### Networking
- **VPC and Subnet Requirements**
  - Public and private subnets
  - NAT Gateway configuration
  - Security group setup
- **Pod Networking**
  - AWS VPC CNI
  - IP address management
  - Secondary IP ranges
- **Service Networking**
  - ClusterIP
  - NodePort
  - LoadBalancer
  - External DNS

## 3. Identity and Access Management

### Authentication
- **AWS IAM Integration**
  - IAM roles for service accounts (IRSA)
  - IAM users and roles
  - aws-auth ConfigMap
- **Kubernetes RBAC**
  - Roles and ClusterRoles
  - RoleBindings and ClusterRoleBindings
  - Service Accounts

### Authorization
- **Security Groups**
  - Pod Security Groups
  - Node Security Groups
  - Control Plane Security Groups
- **Network Policies**
  - Calico integration
  - Pod-to-pod communication rules
  - Namespace isolation

## 4. Storage Options

### Persistent Storage
- **Amazon EBS**
  - EBS CSI Driver
  - Storage Classes
  - Dynamic provisioning
- **Amazon EFS**
  - EFS CSI Driver
  - Shared file systems
- **Amazon FSx for Lustre**
  - High-performance storage

### Ephemeral Storage
- **emptyDir volumes**
- **hostPath volumes**
- **ConfigMaps and Secrets**

## 5. Monitoring and Logging

### Observability
- **Amazon CloudWatch**
  - Container Insights
  - Log groups
  - Metrics collection
- **AWS X-Ray**
  - Distributed tracing
  - Service mesh integration

### Logging Solutions
- **Fluent Bit**
- **CloudWatch Logs**
- **Amazon OpenSearch**
- **Custom logging solutions**

## 6. Scaling and High Availability

### Cluster Scaling
- **Cluster Autoscaler**
  - Node scaling policies
  - Resource-based scaling
- **Horizontal Pod Autoscaling**
  - CPU/Memory based
  - Custom metrics
- **Vertical Pod Autoscaling**

### Load Balancing
- **AWS Load Balancer Controller**
  - ALB ingress controller
  - NLB integration
- **Service Load Balancing**
  - Internal load balancers
  - External load balancers

## 7. Development and Deployment

### CI/CD Integration
- **AWS CodePipeline**
- **AWS CodeBuild**
- **GitOps workflows**
- **Helm charts**

### Application Deployment
- **Deployment Strategies**
  - Rolling updates
  - Blue-green deployments
  - Canary releases
- **Configuration Management**
  - ConfigMaps
  - Secrets
  - External configuration stores

## 8. Cost Optimization

### Resource Management
- **Spot Instances**
  - Node groups with spot instances
  - Handling interruptions
- **Resource Quotas**
  - Namespace quotas
  - Resource limits
- **Cost Allocation**
  - Tagging strategies
  - Cost monitoring

## 9. Security Best Practices

### Cluster Security
- **Pod Security Standards**
  - Privileged vs restricted pods
  - Security contexts
- **Network Security**
  - VPC security
  - Network policies
- **Secret Management**
  - AWS Secrets Manager
  - External Secrets Operator

### Compliance and Governance
- **AWS Config Rules**
- **AWS Security Hub**
- **Amazon GuardDuty**

## 10. Troubleshooting and Maintenance

### Common Issues
- **Node Issues**
  - Node not ready
  - Capacity problems
- **Pod Issues**
  - CrashLoopBackOff
  - ImagePullBackOff
- **Networking Issues**
  - DNS problems
  - Service connectivity

### Maintenance Tasks
- **Cluster Updates**
  - Version upgrades
  - Add-on updates
- **Backup and Restore**
  - Velero integration
  - Disaster recovery plans

## 11. Advanced Topics

### Service Mesh
- **AWS App Mesh**
  - Service discovery
  - Traffic management
  - Observability

### Serverless Integration
- **AWS Fargate**
  - Serverless compute
  - Pod execution
- **AWS Lambda**
  - Event-driven architectures
  - Serverless integration

### Multi-cluster Management
- **Cluster Federation**
- **Multi-cluster service mesh**
- **Cross-cluster communication**

