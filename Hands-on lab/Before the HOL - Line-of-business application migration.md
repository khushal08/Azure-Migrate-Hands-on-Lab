<div class="MCWHeader1">
Line-of-business application migration
</div>

<div class="MCWHeader2">
Before the hands-on lab setup guide
</div>

<div class="MCWHeader3">
May 2019
</div>

**Contents**

<!-- TOC -->

- [Line-of-business application migration before the hands-on lab setup guide](#line-of-business-application-migration-before-the-hands-on-lab-setup-guide)
  - [Requirements](#requirements)
  - [Before the hands-on lab](#before-the-hands-on-lab)
    - [Task 1: Deploy the on-premises environment](#task-1-deploy-the-on-premises-environment)
    - [Task 2: Verify the on-premises environment](#task-2-verify-the-on-premises-environment)

<!-- /TOC -->

# Line-of-business application migration before the hands-on lab setup guide 

## Requirements

1.  You will need Owner or Contributor permissions for an Azure subscription to use in the lab.

2.  Your subscription must have sufficient unused quota to deploy the VMs used in this lab. To check your quota:
    -  Log in to the Azure portal, click **All services** then **Subscriptions**. Select your subscription, then click **Usage + quotas**.
    -  From the **Select a provider** drop-down, select **Microsoft.Compute**.
    -  From the **All service quotas** drop down, select **Standard DSv3 Family vCPUs**, **Standard FSv2 Family vCPUs** and **Total Regional vCPUs**.
    -  From the **All locations** drop down, select the location where you will deploy the lab.
    -  From the last drop-down, select **Show all**.
    -  Check that the selected quotas have sufficient unused capacity:
        - Standard DSv3 Family vCPUs: **at least 10 vCPUs**.
        - Standard FSv2 Family vCPUs: **at least 10 vCPUs**.
        - Total Regional vCPUs: **at least 20 vCPUs**.
  
## Before the hands-on lab

Duration: 60 minutes

### Task 1: Deploy the on-premises environment

1.  Deploy the template **SmartHotelHost.json** to a new resource group. This template deploys a virtual machine running nested Hyper-V, with 4 nested VMs. This comprises the 'on-premises' environment which you will assess and migrate during this lab.

    You can deploy the template by clicking on the 'Deploy to Azure' button below.

    [![Button to deploy the SmartHotelHost template to Azure](Images/BeforeTheHOL/deploy-to-azure.png "Deploy the SmartHotelHost template to Azure")](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2FMCW-Line-of-business-application-migration%2Fmaster%2FHands-on%2520lab%2FResources%2FSmartHotelHost.json)

    >**Note**: The template will take around 6-7 minutes to deploy. Once template deployment is complete, several additional scripts are executed to bootstrap the lab environment. **Allow at least 1 hour from the start of template deployment for the scripts to run.**

### Task 2: Verify the on-premises environment

1.  Navigate to the **SmartHotelHost** VM that was deployed by the template in the previous step.
   
2.  Make a note of the public IP address.

3.  Open a browser window, and navigate to **http://\<ip-address\>**. You should see the SmartHotel application, which is running as nested VMs within Hyper-V on the SmartHotelHost.

    ![Browser screenshot showing the SmartHotel application](Images/BeforeTheHOL/smarthotel.png)

You should follow all steps provided *before* performing the Hands-on lab.
