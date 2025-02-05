# Create MySQL HeatWave Database System

![mysql heatwave](./images/mysql-heatwave-logo.jpg "mysql heatwave")

## Introduction

In this lab, you will create and configure a MySQL DB System and  will add a HeatWave Cluster comprise of two or more HeatWave nodes.  

_Estimated Time:_ 20 minutes

[//]:    [](youtube:Uz_PXHzO9ac)

### Objectives

In this lab, you will be guided through the following tasks:

- Create Virtual Cloud Network
- Create MySQL HeatWave (DB System) Instance

### Prerequisites

- An Oracle Trial or Paid Cloud Account
- Some Experience with MySQL Shell

## Task 1: Create Virtual Cloud Network

1. You should be signed in to Oracle Cloud!

    Click **Navigation Menu**,

    ![OCI Console Home Page](./images/homepage.png " home page")

2. Click  **Networking**, then **Virtual Cloud Networks**  
    ![menu vcn](./images/home-menu-networking-vcn.png "home menu networking vcn ")

3. Click **Start VCN Wizard**
    ![vcn wizard](./images/vcn-wizard-menu.png "vcn wizard ")

4. Select 'Create VCN with Internet Connectivity'

    Click 'Start VCN Wizard'
    ![start vcn wizard](./images/vcn-wizard-start.png "start vcn wizard ")

5. Create a VCN with Internet Connectivity

    On Basic Information, complete the following fields:

    VCN Name:

    ```bash
    <copy>HEATWAVE-VCN</copy>
    ```

    Compartment: Select  **(root)**

    Your screen should look similar to the following
    ![select compartment](./images/vcn-wizard-compartment.png "select compartment")

6. Click 'Next' at the bottom of the screen

7. Review Oracle Virtual Cloud Network (VCN), Subnets, and Gateways

    Click 'Create' to create the VCN
    ![create vcn](./images/vcn-wizard-create.png "create vcn")

8. When the Virtual Cloud Network creation completes, click 'View Virtual Cloud Network' to display the created VCN
    ![vcn creation completing](./images/vcn-wizard-view.png "vcn creation completing")

9. On HEATWAVE-VCN page under 'Subnets in (root) Compartment', click  '**Private Subnet-HEATWAVE-VCN**'
     ![vcn subnet](./images/vcn-details-subnet.png "vcn detqails subnet")

10. On Private Subnet-HEATWAVE-VCN page under 'Security Lists',  click  '**Security List for Private Subnet-HEATWAVE-VCN**'
    ![VCN](./images/vcn-private-security-list.png "vcn private security list")

11. On Security List for Private Subnet-HEATWAVE-VCN page under 'Ingress Rules', click '**Add Ingress Rules**'
    ![vcn private subnet](./images/vcn-private-security-list-ingress.png "vcn private security list ingress")

12. On Add Ingress Rules page under Ingress Rule 1

    a. Add an Ingress Rule with Source CIDR

    ```bash
    <copy>0.0.0.0/0</copy>
    ```

    b. Destination Port Range

    ```bash
    <copy>3306,33060</copy>
     ```

    c. Description

    ```bash
    <copy>MySQL Port Access</copy>
    ```

    d. Click 'Add Ingress Rule'
    ![add ingres rule](./images/vcn-private-security-list-ingress-rules-mysql.png "vcn private security list ingress rukes mysql")

13. On Security List for Private Subnet-HEATWAVE-VCN page, the new Ingress Rules will be shown under the Ingress Rules List
    ![show ingres rule](./images/vcn-private-security-list-ingress-display.png "vcn private security list ingress display")

## Task 2: Create MySQL Database for HeatWave (DB System) instance

1. Click on Navigation Menu
         Databases
         MySQL
    ![home menu mysq](./images/home-menu-database-mysql.png "home menu mysql")

2. Click 'Create DB System'
    ![mysql create button](./images/mysql-menu.png " mysql create button")

3. Create MySQL DB System dialog by completing the fields in each section

    - Provide DB System information
    - Setup the DB system
    - Create Administrator credentials
    - Configure Networking
    - Configure placement
    - Configure hardware
    - Exclude Backups
    - Set up Advanced Options

4. For DB System Option Select **Development or Testing**

    ![heatwave db option](./images/mysql-create-option-develpment.png "heatwave db option")

5. Provide basic information for the DB System:

    a. Select Compartment **(root)**

    b. Enter Name

    ```bash
    <copy>HEATWAVE-DB</copy>
    ```

    c. Enter Description

    ```bash
    <copy>MySQL HeatWave Database Instance</copy>
    ```

    d. Select **HeatWave** to specify a HeatWave DB System
    ![heatwave db info setup](./images/mysql-create-info-setup.png "heatwave db info setup ")

6. Create Administrator Credentials

    **Enter Username** (write username to notepad for later use)

    **Enter Password** (write password to notepad for later use)

    **Confirm Password** (value should match password for later use)

    ![heatwave db admin](./images/mysql-create-admin.png "heatwave db admin ")

7. On Configure networking, keep the default values

    a. Virtual Cloud Network: **HEATWAVE-VCN**

    b. Subnet: **Private Subnet-HEATWAVE-VCN (Regional)**

    c. On Configure placement under 'Availability Domain'

    Select AD-1  ...  Do not check 'Choose a Fault Domain' for this DB System.

    ![heatwave db network ad](./images/mysql-create-network-ad.png "heatwave db network ad ")

8. On Configure hardware, keep default shape as **MySQL.HeatWave.VM.Standard.E3**

    Data Storage Size (GB) Set value to:  **1024**

    ```bash
    <copy>1024</copy>
    ```

    ![heatwave db  hardware](./images/mysql-create-db-hardware.png"heatwave db hardware ")

9. On Configure Backups, disable 'Enable Automatic Backup'

    ![heatwave db  backup](./images/mysql-create-backup.png " heatwave db  backup")

10. Click on Show Advanced Options

11. Go to the Networking tab, in the Hostname field enter (same as DB System Name):

    ```bash
        <copy>HEATWAVE-HW</copy> 
    ```  

    ![heatwave db advanced](./images/mysql-create-advanced.png "heatwave db advanced ")

12. Review **Create MySQL DB System**  Screen

    ![heatwave db create](./images/mysql-create.png "heatwave db create ")
  

    Click the '**Create**' button

13. The New MySQL DB System will be ready to use after a few minutes

    The state will be shown as 'Creating' during the creation
    ![show creeation state](./images/mysql-create-in-progress.png"show creeation state")

14. The state 'Active' indicates that the DB System is ready for use

    On HEATWAVE-HW Page, check the MySQL Endpoint (Private IP Address)

    ![heatwave endpoint](./images/mysql-detail-active.png"heatwave endpoint")

You may now **proceed to the next lab**.

## Acknowledgements

- **Author** - Perside Foster, MySQL Solution Engineering

- **Contributors** - Mandy Pang, MySQL Principal Product Manager,  Priscila Galvao, MySQL Solution Engineering, Nick Mader, MySQL Global Channel Enablement & Strategy Manager, Frédéric Descamps, MySQL Community Manager

- **Last Updated By/Date** - Perside Foster, MySQL Solution Engineering, February 2022
