# kpmgintv
Git Repository for KPMG purpose 

------------------------------------------
The purpose of this code repository is to address KPMG challenges asked as part of interview process.
-----------------------------------
**Challenge #1**: 

A 3-tier environment is a common setup. Use a tool of your choosing/familiarity create these
resources on a cloud environment (Azure/AWS/GCP). 

**Answer/Output-1:** Infrastructure-as-Code using 3-tier architecture environment using Azure VMs and MS SQL Database using Terraform

Cloud provider : Microsoft Azure
Resource provider : Azure Resource Manager (ARM)
Orchestration/IAC : Terraform

**Brief summary:**

From the below example code, we have used the ‘azurerm’ Resource provider to provision resources
in Azure. The configuration creates a resource group, an Azure App Service Plan and App Service for
the web tier, an Azure Virtual Network and Virtual Machine Scale Set for the application tier, and
an Azure SQL Server and SQL Database for the database tier.

The App Service and Virtual Machine Scale Set (VMSS) are configured with appropriate settings for
Linux-based deployments. The Virtual Machine Scale Set is provisioned with two instances.

The SQL Server is provisioned with an administrator username and password, and SSL enforcement is
enabled for secure connections. The SQL Database is created under the SQL Server with Basic
edition, a specific collation, and a maximum size of 5GB.

Network traffic (north-south) traffic can also be restricted using NSG rules between 3 tiers (which is
not considered in the code)


-----------------------------------
**Challenge #2**: 

We need to write code that will query the meta data of an instance within AWS or Azure or GCP
and provide a json formatted output. 

**Answer/Output-1:** Code snippet in Python that uses the Azure SDK for Python to extract
metadata of an Azure Virtual Machine Scale Set (VMSS) and outputs the metadata in
JSON format:

Cloud provider : Microsoft Azure
Resource provider : Python & Azure SDK
Prog.Language : Python
Pre-reqs : azure-identity and azure-mgmt-compute packages to be installed
(pip install azure-identity azure-mgmt-compute)

**Brief summary:**

The below code uses the Azure SDK to authenticate using the default Azure credentials and query &
retrieve the Azure Virtual Machine Scale set (VMSS) metadata. It extracts relevant metadata properties
from the VMSS object and stores them in a dictionary.
Finally, it converts the metadata dictionary to JSON format using the json.dumps() function and prints
the JSON output.

We can further customize the code to extract additional metadata properties (or) perform specific
operations with the VMSS metadata as needed for reference.

-----------------------------------
**Challenge #3**: 

We have a nested object. We would like a function where you pass in the object and a key and
get back the value.
The choice of language and implementation is up to you.
Example Inputs
object = {“a”:{“b”:{“c”:”d”}}}
key = a/b/c
object = {“x”:{“y”:{“z”:”a”}}}
key = x/y/z
value = a

**Answer/Output-1:** Example code snippet of a nested object function in Python that takes an
object and a key as input parameter variable.

Prog. Language : Python

**Brief summary:**

The below code uses the Python programming language to generate a nested object function which
have the inputs of objects and key.

The code uses get_value_from_nested_object function which takes an object and a key as input.
It splits the key using the / delimiter to get individual keys. Then, it iterates through the keys, accessing
each level of the nested object until it reaches the desired value. If a key doesn't exist or a value is not
subscriptable, it returns None.

In the below example usage, we have two objects (object_1 and object_2) and their corresponding
keys (key_1 and key_2). The function extracts the values based on the keys, and the results are printed
as output.
-----------------------------------
