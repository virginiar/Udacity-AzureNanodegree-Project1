# Write-up Template

## 1. Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

### 1.1 Analyze costs, scalability, availability, and workflow
#### Virtual Machines
- **Costs**: The hourly price is based on the region, the operating systemn and the VM's size (procesing power, memory and storage capacity). There are several categories to help to choose the size of the VM. A General Purpose Linux instance B1LS with 1 Core, 0.5 GiB and 4 GiB would be enough to develop this project, with a cost of $0.0085/hour in France South region.
- **Scalability**: Azure Virtual Machines allow both horizontal and vertical scalability. Vertical scalability can be done with Virtual Machine Scale Sets (VMSS) or with a Load Balancer.
- **Availability**: The availability for a single instance using Standard HDD managed disk is 95%, but using Premium SSD managed disk is 99.9%. The availability could be increased at least 99.99% deploying two or more instances across two or more Availability Zones in the same Azure region.
- **Workflow**: An Azure Virtual Machine is an IaaS, so is labor intensive due to the underlying OS has to be configured and also all the packages have to be installed and configured. 

#### App Service
- **Costs**: The Azure App Service offers a Free tier with not cost, wit 1 GB of disk spaces and 10 apps. Also, Azure offers a Basic Linux environment for dev/test with a cost of $0.019/hour in France South region, with 10 GB of disk space and unlimited apps.
- **Scalability**: Azure App Service allow both horizontal and vertical scalability.
- **Availability**: Azure does not provide Service Level Agreements for apps deployed under the Free or Shared tiers. The availability for apps running in a customer suscription is 99.95%.
- **Workflow**: An Azure App Service is a PaaS, so the access to the host server is limited. There are also hardware limitations (max of 14GB of RAM and 4 vCPUs) and a limited set of programming languages to develop. But it can be deployed as part of a continuous deployment (CD) workflow, as example, with Github.

#### 1.2 Choose the appropriate solution (VM or App Service) for deploying the app

I have chosen an Azure App Service to deploy this project.

#### 1.3 Justify your choice

- This is an educational project so it is a lightweight application whithout high performance compute needs and it is below the hardware limitations of the Azure App Service.
- The web application is written in Python which is one of the supported languages of Azure App Service.
- The project can be deployed in the free tier, which reduces costs to those associated with storage.
- Azure App Service is a PaaS so the OS and most of the configurations is provided by Azure.
- The app will run in the Free tier, so not SLA is provided, but it is a educational project that does not need to guarantee access to real users.

## 2. Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

- The choice of the Azure App Service can be changed to Azure Virtual Machine if the app needs a more detailed control of the underlying operating systemneeds or add new tools written in an unsupported language. 
- Also if the app grows and the free tier service is not enough to support the app due to hardware limitations, the option can be a Azure Virtual Machine.

