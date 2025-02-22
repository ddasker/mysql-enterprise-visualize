# Create your Virtual Cloud Network and Related Components


## Introduction

**Create your VCN and subnets**

The first step when deploying a Compute in Oracle Cloud Infrastructure (OCI) is to setup a Virtual Cloud Network. The VCN will be used to connect your linux instance to the internet. You will configure all the components needed to create your virtual network.

_Estimated Time:_ 10 minutes

### Objectives

In this lab, you will be guided through the following tasks:


- Create Virtual Cloud Network 
- Configure security list to allow MySQL incoming connections


### Prerequisites

* An Oracle Free Tier or Paid Cloud Account
* A web browser
* Login to OCI to land on OCI Dashboard (This image shows a trial account)

![INTRO](./images/oci-dashboard.png " ") 

## Task 1: Create Virtual Cloud Network 

1. Click Navigation Menu   
    Select Networking  
    Select Virtual Cloud Networks
    ![VCN](./images/03vcn01.png " ")

2. Click **Start VCN Wizard**
    ![VCN](./images/03vcn02.png " ")

3. Select 'Create VCN with Internet Connectivity'

    Click 'Start VCN Wizard' 
    ![VCN](./images/03vcn03.png " ")

4. Create a VCN with Internet Connectivity 

    On Basic Information, complete the following fields:

 VCN Name: 
     ```
    <copy>myvcn</copy>
    ```
 Compartment: Select  **(root)**

 Your screen should look similar to the following
    ![VCN](./images/03vcn04.png " ")

5. Click 'Next' at the bottom of the screen 

6. Review Oracle Virtual Cloud Network (VCN), Subnets, and Gateways
         
    Click 'Create' to create the VCN
    ![VCN](./images/03vcn04-1.png " ")

7. The Virtual Cloud Network creation is completing 
    ![VCN](./images/03vcn05.png " ")
    
8. Click 'View Virtual Cloud Network' to display the created VCN
    ![VCN](./images/03vcn06.png " ")

## Task 2: Configure security list to allow MySQL incoming connections

1. On myvcn page under 'Subnets in (root) Compartment', click  '**Public Subnet-myvcn**' 
     ![VCN](./images/03vcn07.png " ")

2.	On Public Subnet-myvcn page under 'Security Lists',  click  '**Security List for Public Subnet-myvcn**'
    ![VCN](./images/03vcn08.png " ")

3.	On Security List for Public Subnet-myvcn page under 'Ingress Rules', click '**Add Ingress Rules**' 
    ![VCN](./images/03vcn09.png " ")

4.	On Add Ingress Rules page under Ingress Rule 1
 
 Add an Ingress Rule with Source CIDR 
    ```
    <copy>0.0.0.0/0</copy>
    ```
 Destination Port Range 
     ```
    <copy>3306,33060</copy>
     ```
Description 
     ```
    <copy>MySQL Port Access</copy>
     ```
 Click 'Add Ingress Rule'
    ![VCN](./images/03vcn10.png " ")

5.	On Security List for Public Subnet-myvcn page, the new Ingress Rules will be shown under the Ingress Rules List
    ![VCN](./images/03vcn11.png " ")


**You may now proceed to the next lab**


## Acknowledgements
* **Author** - Dale Dasker, MySQL Solution Engineering
* **Last Updated By/Date** - <Dale Dasker, April 2023
