

# **Terraform EKS infra using Module**

## **Terraform Module**

Terraform Module is just a folder containing a group of resource configurations that can be re-usable later by just passing the values. So, always write a module with the common configurations that are needed for many places and call the module with the custom values as per the use case.
 
•	Terraform module is a set of configuration files in a single directory.

•	Even a simple configuration consisting of a single directory with one or more .tf files is a module. 

•	When you run Terraform commands directly from such a directory, it is considered it as root module. 

•	Terraform commands will only directly use the configuration files in one directory, which is usually the current working directory. 

•	However, your configuration can use module blocks to call modules in other directories. 

•	When terraform encounters a module block, it loads and processes that module's configuration files.

•	Input variables let you customize aspects of Terraform modules without altering the module's own source code. This functionality allows you to share modules across different Terraform configurations, making your module customizable and reusable.

**Local and remote modules:**

Modules can either be loaded from the local filesystem, or a remote source. Terraform supports a variety of remote sources, including the Terraform Registry, most version control systems, HTTP URLs, and Terraform Cloud or Terraform Enterprise private module registries.

Reuse Configuration with Modules:  Create and use Terraform modules to organize your configuration. 



## **AWS Elastic Kubernetes Service**


**EKS Deployment**


•	EKS is the extra wrapper/extra layer that is created on top of the kubernetes technology that give you a managed kubernetes kind of facilities.

•	EKS will help you in accessing your kubernetes.

•	EKS will help you in deploying your application into kubernetes in an easy way.


**EKS Node group**


•	A node group is one or more Amazon EC2 instances that are deployed in an Amazon EC2 Auto Scaling group. 

•	All instances in a node group must have the following characteristics: 

•	Be the same instance type. 

•	Be running the same Amazon Machine Image (AMI) Use the same Amazon EKS node IAM role.


## **Terraform eks-using-custom**

**1. eks.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/1e82f621-ce13-4a16-ad30-f4b6ff7b3e66)




**2. nodeport.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/455fabf3-12c7-4439-93d2-b8f606329b65)


**3. output.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/29d0315b-9519-4888-8fd1-464d036dec66)


**4. provider.tf**


**5. role.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/d67322c1-a5b7-45b6-a4d5-20ebcf6d1c0c)


**6. sg.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/fcff8826-ceb4-4cbb-84f5-66a69431573c)



**7. vpc.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/1f73fa2d-8881-479c-877a-cb86e8032e1c)


   

# **Terraform eks-using-terraform-modules**


**1. eks-cluster.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/b67184d0-8543-4484-a662-37a737bc8076)


**2. kubernets.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/9d9c0a46-349f-4ddc-855a-42c5f4592c06)


**3. outputs.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/b6738bdc-337c-4d98-9e87-1c2e0973f0db)


**4. security-group.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/f1d1c93f-da82-4904-9857-17642f931197)


**5. versions.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/1c06a16c-7777-4a36-9938-9cacbff24fd3)


**6. vpc.tf**

![image](https://github.com/Namg04/terraform-module/assets/61374484/3af15841-1a63-42be-bebb-02198295779b)


# **Execute terraform**  

**Checking iam role**

![image](https://github.com/Namg04/terraform-module/assets/61374484/10a1ec1f-71a1-408c-aee3-b4cbdca11c91)


**Initialise terraform**

![image](https://github.com/Namg04/terraform-module/assets/61374484/08bef834-acda-487a-95e9-49ded983bd73)

**Validate**

![image](https://github.com/Namg04/terraform-module/assets/61374484/4910bd4d-b60e-46a0-b223-aed3873c2df3)

**Apply**

![image](https://github.com/Namg04/terraform-module/assets/61374484/47f59f05-247a-4dbb-854d-2327a9eee31a)


**Plan**

![image](https://github.com/Namg04/terraform-module/assets/61374484/312ba43f-d664-4dc2-b8da-5b9be56c72cb)



# **Validate created EKS Infra**


**2 ec2 instances created Prod and dev**

![image](https://github.com/Namg04/terraform-module/assets/61374484/68cc63df-8e57-4c46-b7df-f7c0615d6ebc)


**VPC**

![image](https://github.com/Namg04/terraform-module/assets/61374484/5e8065a3-6c03-490d-92aa-692539d7ca02)

**EKS**

![image](https://github.com/Namg04/terraform-module/assets/61374484/d90706d1-40ab-4159-8fed-620fed1677b5)


![image](https://github.com/Namg04/terraform-module/assets/61374484/6ea0a83c-2140-487b-8668-7f1ba8baa67a)

At the time of deploy EKS cluster which is managed kubernetes cluster platform, aws will create client side certificate to deploy api server. 
*Generate client side certificate to access kubernetes cluster*

![image](https://github.com/Namg04/terraform-module/assets/61374484/a7bc5cfb-65a3-4373-bd0c-a2cabd15348b)

NOTE: Remember kubernetes cluster is deployed using which aws access key or IAM role. 
Only the same credentials has to be used to generate the client side certificate.


# **Destroy EKS**

![image](https://github.com/Namg04/terraform-module/assets/61374484/2d0c05c0-8b8f-45bd-860d-56edf5109649)

