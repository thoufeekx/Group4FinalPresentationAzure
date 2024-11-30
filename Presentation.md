




# Part 2: Legacy System Modernization (ERP and Mainframe)






## Part 3 Security and Data Protection


# Part 4: Cost Estimation and optimization
### **Cost Estimation for GlobalTech Solutions on Azure**  

The table below provides the detailed **cost estimation** for migrating GlobalTech Solutions' infrastructure to Azure, breaking down the monthly and yearly costs for each service.
For a more accurate cost estimation, I will break it down based on the services and resources mentioned in the scenario. I'll use Azure's pricing calculator to estimate the costs for the following components:

### Assumptions:
- **150 Virtual Machines (VMs):** Mix of Windows Server and Linux VMs.
- **Monolithic ERP System:** Estimated size for migration (likely rehosted or refactored).
- **SQL Database Cluster:** Migration to Azure SQL Managed Instance.
- **E-commerce Applications:** Estimated usage of Azure App Services, Load Balancer, and CDN.
- **Mainframe System:** Likely rehosted or modernized with Azure services like Azure Virtual Machines or Azure Kubernetes Service (AKS).
- **Backup & Disaster Recovery:** Azure Backup and Azure Site Recovery.

### **1. Virtual Machines (VMs)**
- **VM Type**: Assume a mix of **D-series** for Windows and **B-series** for Linux VMs (e.g., Standard D2s v3 for general-purpose).
- **Size**: Assuming 2 vCPUs and 8GB RAM for most VMs.
- **Operating System**: Windows (with additional license cost) and Linux (without license cost).
- **Usage**: On-demand pricing for simplicity.

**Cost Estimation for 150 VMs**:
- **Windows VM (D2s v3)**: Approx. **$0.096/hr** (for pay-as-you-go)
- **Linux VM (B1s)**: Approx. **$0.017/hr**

**Total Estimate (Monthly)**:  
- For Windows VMs:  
  \( 75 \, \text{VMs} \times 0.096 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 5,268 \, \text{USD/month} \)
- For Linux VMs:  
  \( 75 \, \text{VMs} \times 0.017 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 931.5 \, \text{USD/month} \)

**Total for 150 VMs:**  
- \( 5,268 + 931.5 = 6,199.5 \, \text{USD/month} \)

### **2. SQL Database (Azure SQL Managed Instance)**
- **Usage**: Assume a standard **General Purpose** SKU for SQL Managed Instance.
- **Size**: 8 vCores, 32 GB memory.
- **Backup Storage**: Included in pricing but additional charges for storage beyond the free limit.

**Cost Estimation**:
- **Azure SQL Managed Instance** (Standard): Approx. **$1.064/hr**.
- Monthly estimate:  
  \( 1.064 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 776.72 \, \text{USD/month} \)

### **3. Azure Storage and Data Transfer**
- **Storage for VMs**: Estimated at 100 GB per VM for operating system disk and data storage.
- **Data Transfer**: Assuming minimal cross-region transfer and in/out data.

**Storage Costs**:
- **Standard SSD (Managed Disks)**: Approx. **$0.08/GB/month**.
- Total storage cost for 150 VMs:  
  \( 150 \times 100 \, \text{GB} \times 0.08 \, \text{USD/GB} = 1,200 \, \text{USD/month} \)

**Data Transfer Costs**:  
- Assuming 1 TB of outbound data transfer per month, priced at **$0.087/GB** for the first 10 TB.
  - \( 1,000 \, \text{GB} \times 0.087 \, \text{USD/GB} = 87 \, \text{USD/month} \).

### **4. Load Balancer & Networking**
- **Azure Load Balancer**: Assuming basic load balancing for public-facing applications.
  - Approx. **$0.025/hr** for the basic load balancer.

**Cost Estimation**:
- \( 0.025 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 18.25 \, \text{USD/month} \)

### **5. Backup and Disaster Recovery (Azure Site Recovery)**
- **Azure Site Recovery** for VM replication and disaster recovery.
- Estimated cost: **$0.02/VM/hr** for replication.

**Cost Estimation**:
- \( 150 \, \text{VMs} \times 0.02 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 2,190 \, \text{USD/month} \)

### **6. E-Commerce Application and Web Hosting**
- **Azure App Service** for hosting e-commerce applications.
- Estimated cost for **Basic Tier** with autoscaling: **$0.075/hr** per app.

**Cost Estimation**:
- Assuming 3 applications, each running for 730 hours/month:  
  \( 3 \times 0.075 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 163.88 \, \text{USD/month} \)

### **7. Compliance and Security (e.g., Azure Security Center)**
- Security Center cost: **$0.03/VM/hr** for protection.
  - \( 150 \, \text{VMs} \times 0.03 \, \text{USD/hr} \times 730 \, \text{hrs/month} = 3,285 \, \text{USD/month} \).

### **Total Estimated Monthly Cost for Migration**:
| Service                            | Cost Estimate (USD/month)    |
|------------------------------------|-----------------------------|
| **Virtual Machines (150 VMs)**     | 6,199.5                    |
| **Azure SQL Managed Instance**     | 776.72                     |
| **Storage (Managed Disks)**        | 1,200                       |
| **Data Transfer (Outbound)**       | 87                          |
| **Load Balancer**                  | 18.25                       |
| **Site Recovery (Disaster Recovery)** | 2,190                    |
| **E-Commerce App Service**         | 163.88                      |
| **Security Center (Compliance)**   | 3,285                       |
| **Total**                           | **13,920.35 USD/month**    |

### **Cost Optimization Strategies**:
1. **Reserved Instances**:  
   - For long-term savings, purchase **Reserved Instances** (1-year or 3-year term) for VMs. This can reduce VM costs by up to 72%.
   
2. **Auto-scaling**:  
   - Enable **auto-scaling** for e-commerce applications to scale based on traffic demand, reducing costs during low usage periods.

3. **Storage Tiering**:  
   - Use **Azure Blob Storage** for archival data and **Standard SSD** for active storage, optimizing costs for infrequently accessed data.

4. **Spot VMs**:  
   - Consider using **Spot VMs** for non-critical workloads or batch processing to reduce VM costs.

5. **Monitoring and Cost Management**:  
   - Implement **Azure Cost Management** and **Azure Advisor** to regularly monitor resource usage and receive recommendations for optimizing costs.

---

To calculate the **yearly cost** for the components we discussed, we can multiply the **monthly cost** by **12**. Here’s the breakdown for the total estimated yearly cost:

### **1. Virtual Machines (150 VMs)**
- Monthly cost: **$6,199.5**
- Yearly cost:  
  \( 6,199.5 \, \text{USD/month} \times 12 = 74,394 \, \text{USD/year} \)

### **2. Azure SQL Managed Instance**
- Monthly cost: **$776.72**
- Yearly cost:  
  \( 776.72 \, \text{USD/month} \times 12 = 9,320.64 \, \text{USD/year} \)

### **3. Storage (Managed Disks)**
- Monthly cost: **$1,200**
- Yearly cost:  
  \( 1,200 \, \text{USD/month} \times 12 = 14,400 \, \text{USD/year} \)

### **4. Data Transfer (Outbound)**
- Monthly cost: **$87**
- Yearly cost:  
  \( 87 \, \text{USD/month} \times 12 = 1,044 \, \text{USD/year} \)

### **5. Load Balancer**
- Monthly cost: **$18.25**
- Yearly cost:  
  \( 18.25 \, \text{USD/month} \times 12 = 219 \, \text{USD/year} \)

### **6. Site Recovery (Disaster Recovery)**
- Monthly cost: **$2,190**
- Yearly cost:  
  \( 2,190 \, \text{USD/month} \times 12 = 26,280 \, \text{USD/year} \)

### **7. E-Commerce Application Hosting (App Service)**
- Monthly cost: **$163.88**
- Yearly cost:  
  \( 163.88 \, \text{USD/month} \times 12 = 1,966.56 \, \text{USD/year} \)

### **8. Security Center (Compliance)**
- Monthly cost: **$3,285**
- Yearly cost:  
  \( 3,285 \, \text{USD/month} \times 12 = 39,420 \, \text{USD/year} \)

---

### **Total Estimated Yearly Cost**:

| Service                            | Monthly Cost (USD) | Yearly Cost (USD)  |
|------------------------------------|-------------------|--------------------|
| **Virtual Machines (150 VMs)**     | 6,199.5           | 74,394             |
| **Azure SQL Managed Instance**     | 776.72            | 9,320.64           |
| **Storage (Managed Disks)**        | 1,200             | 14,400             |
| **Data Transfer (Outbound)**       | 87                | 1,044              |
| **Load Balancer**                  | 18.25             | 219                |
| **Site Recovery (Disaster Recovery)** | 2,190           | 26,280             |
| **E-Commerce App Service**         | 163.88            | 1,966.56           |
| **Security Center (Compliance)**   | 3,285             | 39,420             |
| **Total**                          | **13,920.35**     | **167,543.20**     |

### **Total Estimated Yearly Cost**:  
**$167,543.20 USD/year**

This yearly estimate assumes that the resources are used continuously throughout the year. For cost optimization, consider purchasing **Reserved Instances** or using **Spot VMs** for savings in the long run.



Here’s a more polished version of the cost optimization strategies:

---

### **Azure Cost Optimization Strategy for GlobalTech Solutions**

As part of GlobalTech Solutions' cloud migration to Azure, implementing cost optimization strategies is essential to ensure efficient use of resources while adhering to the company's budgetary constraints. The following strategies will help optimize costs across infrastructure, storage, and application services, while maintaining performance, scalability, and compliance.

---

#### **1. Azure Reserved Instances (RIs) for Virtual Machines**
**Overview:**  
Reserved Instances (RIs) provide significant discounts (up to 72%) for committing to specific Azure virtual machine configurations over one- or three-year periods.

**Cost Optimization Opportunity:**  
For the 150 virtual machines (VMs) in GlobalTech’s environment, we recommend evaluating the possibility of purchasing RIs for steady-state workloads. RIs offer substantial savings over the pay-as-you-go model, especially for VMs used for mission-critical applications that require consistent usage. This strategy is particularly beneficial for workloads such as the company's ERP system and in-house SQL databases.

**Action Plan:**  
- Analyze the usage patterns of each VM to determine which VMs will benefit from long-term reservations.
- Secure RIs for critical production VMs that run consistently, such as the e-commerce platform, ERP system, and database cluster.

---

#### **2. Azure Spot Virtual Machines**
**Overview:**  
Azure Spot VMs offer unused Azure capacity at a fraction of the cost (up to 90% off regular prices). However, Spot VMs can be evicted if Azure needs the capacity for other purposes.

**Cost Optimization Opportunity:**  
For non-production environments or workloads that can tolerate interruptions, Spot VMs can significantly reduce costs. These are ideal for development, testing, or batch processing jobs that do not require high availability.

**Action Plan:**  
- Identify non-critical workloads, such as development and test environments, that can leverage Spot VMs.
- Monitor the reliability and performance of Spot VMs to ensure they meet the company’s operational needs.

---

#### **3. Auto-Scaling for Azure Virtual Machines**
**Overview:**  
Azure’s auto-scaling feature automatically adjusts the number of running VMs based on workload demand, ensuring that only the required resources are used at any given time.

**Cost Optimization Opportunity:**  
For dynamic workloads, such as the e-commerce application, auto-scaling ensures resources are only provisioned when needed. During off-peak hours, VMs can be scaled down to minimize costs.

**Action Plan:**  
- Implement auto-scaling for critical workloads, especially e-commerce and ERP systems.
- Set scaling rules to ensure the number of VMs aligns with actual demand, reducing idle resources.

---

#### **4. Azure Hybrid Benefit**
**Overview:**  
Azure Hybrid Benefit allows customers to apply existing on-premises licenses for Windows Server and SQL Server to reduce the cost of running these workloads in Azure.

**Cost Optimization Opportunity:**  
GlobalTech Solutions can leverage the Azure Hybrid Benefit if they have existing Windows Server or SQL Server licenses with Software Assurance. This can result in up to 40% savings on virtual machine costs and up to 55% savings for SQL Server.

**Action Plan:**  
- Review existing software licenses and determine eligibility for the Azure Hybrid Benefit.
- Apply the benefit to eligible workloads, such as the company’s SQL database cluster and Windows-based VMs.

---

#### **5. Storage Tier Optimization**
**Overview:**  
Azure provides different storage tiers—Hot, Cool, and Archive—designed to meet various data access needs, allowing for cost-effective storage based on usage patterns.

**Cost Optimization Opportunity:**  
By analyzing data access patterns, GlobalTech can move infrequently accessed data to lower-cost storage tiers such as Cool or Archive. This will reduce costs associated with data storage, especially for the legacy mainframe and ERP systems.

**Action Plan:**  
- Review current storage usage and identify which data is infrequently accessed.
- Migrate such data to Azure’s Cool or Archive storage tiers to reduce storage costs while ensuring compliance with data retention policies.

---

#### **6. Reserved Capacity for Azure SQL Managed Instance**
**Overview:**  
Azure offers Reserved Capacity for SQL Managed Instances, which provides significant discounts for committing to a certain level of database resources over a one- or three-year term.

**Cost Optimization Opportunity:**  
For the company’s SQL database cluster, purchasing Reserved Capacity for SQL Managed Instances can offer up to 65% savings on compute and storage costs.

**Action Plan:**  
- Evaluate SQL Managed Instance usage to determine the most appropriate reserved capacity.
- Lock in Reserved Capacity for long-term database operations to reduce costs.

---

#### **7. Azure Cost Management and Budgets**
**Overview:**  
Azure Cost Management and Budgets provide tools for tracking resource consumption and costs, helping organizations make informed decisions about resource optimization.

**Cost Optimization Opportunity:**  
By implementing Azure Cost Management, GlobalTech can set budgets and track expenditures in real-time. The service provides insights into resource usage and alerts users when costs exceed predefined thresholds.

**Action Plan:**  
- Set up budgets and cost alerts for each department or project within Azure.
- Regularly review cost reports to identify areas for optimization, ensuring that spending stays within budget.

---

#### **8. Optimizing Networking Costs**
**Overview:**  
Network data transfer, especially across regions, can incur significant costs. Optimizing networking strategies can result in substantial savings.

**Cost Optimization Opportunity:**  
To reduce network transfer costs, we recommend deploying resources within the same Azure region, where possible. Additionally, leveraging Azure’s Content Delivery Network (CDN) for static content can reduce outbound data transfer costs.

**Action Plan:**  
- Design the infrastructure to minimize cross-region traffic by deploying resources in the same region.
- Use Azure CDN to cache and deliver static content more efficiently, reducing bandwidth costs.

---

#### **9. Implementing Dev/Test Pricing**
**Overview:**  
Azure offers special pricing for development and testing environments, which can help reduce the cost of non-production workloads.

**Cost Optimization Opportunity:**  
By using the **Dev/Test** pricing tier for development and test environments, GlobalTech can reduce costs significantly for non-production workloads.

**Action Plan:**  
- Move all non-production workloads, such as testing and staging, to Azure’s **Dev/Test** pricing tier.
- Ensure that these environments are only running during working hours to further reduce costs.

---

#### **10. Azure Kubernetes Service (AKS) for Modernization**
**Overview:**  
Azure Kubernetes Service (AKS) is a fully managed container orchestration service that enables the deployment of containerized applications at scale, with efficient use of underlying infrastructure resources.

**Cost Optimization Opportunity:**  
By moving to containerized deployments in AKS, GlobalTech can improve resource utilization and reduce costs compared to traditional VM-based deployments.

**Action Plan:**  
- Assess the feasibility of refactoring the ERP system and other monolithic applications into containerized services for deployment on AKS.
- Leverage AKS's scaling and resource allocation capabilities to optimize operational costs.

---

### **Summary of Cost Optimization Strategies**

The cost optimization strategies outlined above will help GlobalTech Solutions maximize their return on investment in Azure while ensuring that performance, scalability, and security requirements are met. Key strategies include:

- **Reserved Instances** for long-term, steady-state workloads.
- **Azure Spot VMs** for non-critical, interruptible workloads.
- **Auto-scaling** for dynamic workloads to reduce resource waste.
- **Hybrid Benefit** to leverage existing licenses and reduce costs.
- **Storage tier optimization** to lower storage costs for infrequently accessed data.
- **SQL Managed Instance Reserved Capacity** for significant database cost savings.
- **Cost management tools** to track and optimize expenditures proactively.
- **Networking optimizations** to minimize data transfer costs.

By implementing these strategies, GlobalTech can expect significant savings in both short- and long-term cloud operations, while maintaining flexibility, scalability, and compliance with industry standards.

--- 

