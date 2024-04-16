# Az104-Implement-Virtual-Networking

## Job skills
•	Task 1: Create a virtual network with subnets using the portal.
•	Task 2: Create a virtual network and subnets using a template.
•	Task 3: Create and configure communication between an Application Security Group and a Network Security Group.
•	Task 4: Configure public and private Azure DNS zones.

## Task 1: Create a virtual network with subnets using the portal
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/08e6ff3c-06db-469e-8715-d68a539c00ef)

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/e373d3e8-89ed-40f1-84db-ae4c958107fe)

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/01f681ed-b073-4374-a56a-fd6e0562c3af)

### The virtual network and subnets were successfully deployed:

 ![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/e15a2163-a0ce-4d9d-830d-9f7d9034b9f6)

### Exporting the template to create another virtual network:
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/a8586f2e-7291-4f7a-bbb5-d335f3ab53c7)

## Task 2: Create a virtual network and subnets using a template
### •	Changed all occurrences of CoreServicesVnet with ManufacturingVnet.
### •	Changed all occurrences of 10.20.0.0 with 10.30.0.0.

 ![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/0b04e98e-6092-4701-9fb6-669b7b680ab7)

### •	Changed all occurrences of SharedServicesSubnet to SensorSubnet1.
### •	Changed all occurrences of 10.20.10.0/24 to 10.30.20.0/24.
### •	Changed all occurrences of DatabaseSubnet to SensorSubnet2.
### •	Changed all occurrences of 10.20.20.0/24 to 10.30.21.0/24.
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/8ff1cc51-34ea-41d3-8480-9ea0f18e0755)

### •	Replaced the only occurrence of CoreServicesVnet with ManufacturingVnet in the parameters file.
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/6a96200e-f893-439c-a465-864b6ed6471a)

### Deploying the ManufacturingVnet via the template and parameter files that were downloaded and edited.
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/c0782296-87b9-4219-b9d7-dc29c3adada7) 

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/fe5c15e1-b2d1-4283-bdae-3d6b75a0aa14)

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/ed327595-9edd-47d3-a178-55d1f6909089)

## Task 3: Create and configure communication between an Application Security Group and a Network Security Group
### Creation of the Application Security Group:
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/b8db6271-6c55-4920-9747-f6b20ce2fa79)

### Creation of the Network Security Group:

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/4d11e11f-5212-4066-9150-000706ef12d0)
 
### Associating the SharedServicesSubnet from the CoreServicesVnet with the Network Security Group
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/49649451-11b8-43f4-b4f9-3dc27ef4df00)

### Creating a custom Network Security Group rule to allow inbound traffic from the Application Security Group (asg-web) to any destination if the destination port is 80 (HTTP) or 443 (HTTPS). 

 ![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/87ffb72c-8be3-402b-84c4-296b744de5e7)

### Creating a custom Network Security Group Rule to deny the outbound traffic from any source out to the internet. This rule is required to have a higher priority than 65001 which cannot be deleted and allows outbound traffic to the internet.
 
 ![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/38634d04-77ba-42b1-ac7b-2e7412513108)

## Task 4: Configure public and private Azure DNS zones
### Creation of the DNS Zone (Contoso.com was reserved) ns1-34.azure-dns.com.

 ![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/10864464-922f-4f17-bfe2-cd992e489f29)

### Creating the record set so that www.drewcrouch.com resolves to 10.1.1.4. In the real world, this IP address would be the address of the web server.

 ![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/cc2c9643-115f-4ae5-b7bd-9252a3f6f524)

### Verifying the address resolves to 10.1.1.4:
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/f4d19bc5-6a33-4fd8-ae27-0926800173d5)

### Creating a private DNS Zone:
 
![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/b45f4b33-5dbe-4f9a-a1c3-79103be4adf8)

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/dc1f1f38-58a0-4934-af12-7a05a6cbb3e1)

### Assigned the sensorvm DNS name to 10.1.1.4:

![image](https://github.com/DrewCrouch1/Az104-Implement-Virtual-Networking/assets/158229796/a323b187-43ee-419c-8565-c7a182c7ed16)


