## Notes about AWS DynamoDB:

By default it is regionally distributed (replicated over 3 separated AZs (for availability reasons) ) 
We can make globally distributed by making tables global (distributed over more than one region)

## Factors to consider while thinking to create a VPC or not :
* Security: If you require a high level of security for your application and want to control network access, you may want to use a VPC.
* Data Sensitivity: If your application handles sensitive data, you may want to use a VPC to ensure that the data is not accessible over the internet.
* Compliance: If your application is subject to regulatory compliance (e.g. HIPAA, PCI-DSS), you may need to use a VPC to meet the security requirements.
* Networking: If you need to connect to other resources within your organization's network (from private to cloud), or want to use private IP addresses for your instances, you may want to use a VPC.
* Cost: If you're using certain services that don't require to be inside a VPC and it will save you money, you may choose to not use a VPC.

In our case :  
AWS DynamoDB is a fully managed services , and our use case is simple (e.g. we don't need access from internet or between cloud and on-premises)

&rarr; we don’t need to create a vpc . 

**Note :**  
To make a resource (outside a vpc ) able to access another resource (inside a vpc ) ,we will need to put VPC Endpoints
