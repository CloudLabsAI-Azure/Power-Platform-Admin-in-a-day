# Lab 3: Action through Automation

### Estimated Duration: 120 Minutes

## Overview

In this lab, you are an **administrator** supporting Fabrikam's efforts to **streamline and control Power Platform usage**. Fabrikam has restricted environment creation to global or service admins and wants an automated process for users to request new environments and Dataverse databases without discouraging platform adoption. You will build a **Microsoft Form** for users to submit requests, and then use **Power Automate with administrative connectors and approval workflows** to automate the review and provisioning process. The solution will handle approvals, environment creation, and user notifications. 

You’ll also explore the app **auditing process** from the CoE Starter Kit by stepping through it as both a maker and an admin, and install a prebuilt flow to identify new app makers, add them to an Office 365 group, and send them a welcome email.

## Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Create Environment Request Form
- Exercise 2 – Create Environment on Form Submit
- Exercise 3 – Welcome New Makers (Optional if you have time)

<!--
### Lab Test Environment

This hands-on lab is designed to be completed in an environment setup for multiple students to complete the Admin in a day series of hands-on labs.

You will be assigned one or more users to use to complete the hands-on tasks. Because this is a shared environment, some tasks that require a tenant Global Administrator or a Service 
Administrator will already be performed.

This lab does not require you to have completed any of the prior labs.
-->

## Exercise 1: Create Environment Request Form

In this exercise, you will be creating an environment request form using Microsoft Forms. This form could
collect additional information allowing it to be tailored to your individual organization's requirements.

### Task 1: Create Microsoft Form

In this task you will, create a form titled New Environment Approval Request with required fields for Environment Name, Business Justification, and Connectors to be used, then preview the saved form.

1. Open a new tab and navigate to **Microsoft Forms** with the following URL:

   ```
   https://forms.office.com/Pages/DesignPageV2.aspx?prevsubpage=design
   ```

2. On the **Welcome to Microsoft Forms!** page, select **Registration**.

   ![reg](images/M03/Regmsform.png)

3. Select the **Untitled Form** Header.

   ![untitiled](images/M03/untform.png)

4. Enter **New Environment Approval Request (1)** for title, enter **New environment request (2)** for description, and select **+ Quick start with (3)**.

   ![](images/M03/form2.png)

5. We will create the **Form**, as shown in the screenshot below, by following the steps outlined below.

   ![](images/M03/M3-EX1-T1-S5.png)

6. Select **Text**.

   ![](images/M03/text.png)

7. Enter the **Environment Name (1)**, mark the question as **Required (2)** by enabling it, and select **+ Add new question (3)**.

   ![](images/M03/addq.png)

8. Select **Text** again.

9. Enter **Business Justification (1)**, select **Long Answer (2)**, and mark it as **Required (3)**. Then, select **+ Add new question (4)**.

   ![](images/M03/q2.png)

10. Select **Text**.

11. Enter **What connectors will you use? (1)**, select **Long Answer (2)**, and mark it as **Required (3)**.

      ![](images/M03/q3.png)

12. The form will be saved automatically.

13. Select **Preview**.

    ![](images/M03/pr.png)

14. You can see the created form.

    ![](images/M03/cf.png)


## Exercise 2: Create Environment on Form Submit

In this exercise, you will be building the automated flow to process new form submissions.

> **Note**: For this exercise, we have hard-coded the language, currency and environment template. The Power Platform Administration connector has actions allowing you to dynamically retrieve these and make the process more flexible. You could allow the user to specify the values, or infer them from the user’s Office 365 profile information using the Office 365 connector.

### Task 1: Delete your sandbox environment

In this task you will, remove the earlier sandbox environment to free up the trial slot.

1. Navigate back to the **Power Platform admin center** page.

1. On the **Environment**, select the sandbox environment that you created in module one named **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** in the list of environments.

   ![](images/sandenv.png)

1. Select the **Delete** button.

   ![](images/sdel.png)

1. Confirm the deletion by typing the environment name **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (1)** and then select **Confirm (2)**. We have to delete it to create another Trial environment, which we can only have one at a time.

   ![](images/img-01-40.png)

   >**Note**: Environment deletion may take 10-15 minutes. Please wait until it is fully deleted, and keep refreshing the portal until the process is complete.

### Task 2: Create New Environment Approval Flow

In this task you will, build a flow triggered by form submissions that requests approval and conditionally creates a new environment.

1. Navigate to the tab where you have the **Power Automate** portal open. If you have closed it, navigate to the Power Automate portal with the following URL:

   ```
   https://make.powerautomate.com/
   ```

1. Make sure the environment is set to **Power Platform CoE**.

   >**Note**: This environment is where our CoE starter kit is installed and is intended to be our dedicated admin environment.

1. On the left navigation menu, select **My flows (1)**, select **+ New flow (2)** drop down and select **Automated cloud flow (3)**.

   ![](images/M03/pp62.png)

1. Type **New Environment Approval (1)** in the **Flow name** field. In the **Choose your flow’s trigger** section, search for **When a new response is submitted (2)** then select **When a new response is submitted (3)**, and select **Create (4)**.

   ![](images/M03/pp63.png)

1. Select the **When a new response is submitted** box.

   ![](images/M03/pp64.png)

1. For the **Form Id**, select the **New Environment Approval Request** form which you created.

   ![](images/M03/pp65.png)

1. Select **+ Add action**.

   ![](images/M03/pp66.png)

1. Search for **Microsoft Forms (1)** and select **Get response details (2)**.

   ![](images/M03/pp67.png)

1. Click on the **Get response details** and select **New Environment Approval Request (1)** for **Form Id** and click on the **dynamic content (2)** symbol to select **Response Id (3)**. 

    ![](images/M03/E2T2S9-0605.png)

    >**Note:** Please signin with ODL user credentials if prompted.

1. Select **+ Add action**.

    ![](images/M03/pp69.png)

1. Search for **Approvals (1)** and select **Start and Wait for an approval (2)**.

    ![](images/M03/pv33.png)

1. If prompted, click on **Create new**.

1. Select **Approve/Reject - First to Respond** for Approval type.

    ![](images/M03/pv34.png)

1. Enter the following details:

   - Title: **Environment Approval Requested (1)**
   - Assigned to: **<inject key="AzureAdUserEmail"></inject>** **(2)**
   - Details: **New Environment was requested by:** **(3)**
   - Select the **Dynamic content symbol (4)** and select the **Responders email (5)**

     ![](images/M03/E2T2S14.1-0605.png)

1. Similarly, add the following text and dynamic content in the **Details** field by hitting the enter key after the previous line:

   |Name| Dynamic content to add|
   |---|---|      
   | Environment Name | Environment Name |
   | Business Justification | Business Justification |
   | Connectors | What connectors will you use? |

      ![](images/M03/E2T2S15-0605.png)

1. Select **+ Add Action** under **Start and Wait for an Approval**.

    ![](images/M03/pv39.png)

1. Search for **Condition (1)** and the select **Condition (2)** Control.

    ![](images/M03/pp74.png)

1. Click on the **dynamic content symbol (1)** to select the value **Outcome (2)** from the Start and Wait for an Approval step.

    ![](images/M03/E2T2S18-0605.png)

1. Enter **is equals to (1)** for condition, enter **Approve (2)** for value.

    ![](images/M03/E2T2S19-0605.png)

1. Select **Add an action** in the **True**  branch.

    ![](images/M03/E2T2S20-0605.png)

1. Search for **Power Platform for Admins** and under **Power Platform for Admins** section select **See more (2)**. Select **Create Environment (3)**.

    ![](images/M03/E2T2S21-0605.png)

    ![](images/M03/E2T2S21.1-0605.png)    

1. If prompted to sign in, select **Sign in** and sign in with the ODL credentials.

    ![](images/M03/pp81.png)

1. Select the following Parameters:

   - Location: **United States (1)** 
   - Display Name: Select **Dynamic content (2)** and select **Environment Name (3)** from the Get response details.

      ![](images/M03/E2T2S23-0605.png)

      >**Note:** Location determines the region for the environment, in a real process you might allow this to be auto-determined by the user location or something the requester provides.

   - Environment Sku: **Trial (4)**
   - Click on Save **(5)** but do not navigate away from the page after saving.

     ![](images/M03/E2T2S23.1-0605.png)

### Task 3: Create a Database and Notify the User

In this task you will, extend the flow to provision a CDS database and send approval/rejection notification emails.

1. Select **+ Add an action** under **Create Environment**.

   ![](images/M03/pv42.png)

1. Search for **Power Platform for Admins** and under **Power Platform for Admins** section select **See more (2)**. Select **Create CDS Database (3)**.

    ![](images/M03/E2T2S21-0605.png)

    ![](images/M03/E2T3S2.1-0605.png)

1. Select on the **Environment (1)** dropdown and select **Enter Custom Value (2)**.

   ![](images/M03/E2T3S3-0605.png)

1. Enter **/ (1)** and select **Insert dynamic content (2)** to get the dynamic values.  

   ![](images/M03/ppm11.png)

1. Select **Name** from the Dynamic content pane.

   ![](images/M03/E2T3S5-0605.png)

1. Select **Show all (2)**.

   ![](images/M03/pv44.png)

1. Enter the following: 

   - Base Language: **1033 (1)**
   - Currency Code: **USD (2)** 
   - Template Item: **D365_CDSSampleApp (3)**

      ![](images/M03/pv45.png)

1. Select **Add an action** under **Create CDS Databse**.

   ![](images/M03/pv46.png)

1. Search for **Send Email (1)** and select **Send an email (V2) (2)**.

   ![](images/M03/pp91.png)

1. If prompted, click on **Sign in**. Sign in with the lab credentials.

   ![](images/M03/pp92.png)

1. Click on Settings dropdown **(1)** and then select **Use dynamic content (2)**.

   ![](images/M03/pv47.png)

1. Enter the following details:

   - To: Select **Responders Email** from the Dynamic Content pane **(1)**.
   - Subject: **Your environment was created (2)**
   - Body: **Environment:** and select **Display Name** from the Dynamic Content pane under the **Create Environment** step and add **was created** in the last **(3)**.

     ![](images/M03/E2T3S12-0605.png)

1. Go to the **False** branch and select **Add an Action** to create a new connection under the **False** branch.

   ![](images/M03/pv48.png)

1. Search for Send email and select **Send an email (V2)**.

   ![](images/M03/pp96.png)

1. Click on Settings dropdown **(1)** and then select **Use dynamic content (2)**.

   ![](images/M03/pv49.png)

1. Enter the following details:

   - To: Select **Responders Email** from the Dynamic Content pane **(1)**.
   - Subject: **Your environment request was rejected (2)**
   - Body: **Your request for new environment was rejected (3)**. 

      ![](images/M03/E2T3S16-0605.png)

1. Select **Save**.

    ![](images/M03/M3-EX2-T3-S21.png)

1. Select **Flow checker** and make sure there are no errors.

    ![](images/M03/pp101.png)

    ![](images/M03/pp102.png)

1. Close the **Flow checker** pane with the X to the right of the pane header.

1. Select the **Back** button.

    ![](images/M03/E2T3S20-0605.png)

### Task 4: Test the Flow

In this task you will, submit the form, approve the request via email, and verify that the new environment is created successfully in the admin center.

1. Navigate to **Microsoft Forms** and open the form you created.

   ![](images/img-01-41.png)

1. Select **Collect responses**.

   ![](images/img-01-42.png)

1. Select **Copy link** button.   

   ![](images/img-01-43.png)

1. Paste the link in the browser and navigate to the create form.

   ![](images/img-01-44.png)

1. The form should load, provide the following details and then click on **Submit (4)**.

   - Environment name: Provide **Central Apps Test (1)**
   - Business Justification: **We will use this Environment for training new employees (2)**
   - What connector will you use: **Microsoft Dataverse (3)**. 

     ![](images/M03/E2T4S5-0605.png)    
   
      >**Note**: For this course, we will be using this environment we created here later in another lab to deploy the Device Ordering solution using Azure Dev Ops, for that lab it will serve as the Test environment which is why we are suggesting naming it Central Apps Test. In real word use, most likely it would be a team/project development environment that would be requested using a form like this.

1. Navigate back to the **Power Automate** portal, Go to **My flows** list and open the **New Environment Approval** flow you created.

1. You should see the flow running. Select the start date to open it.

   ![](images/M03/E2T4S7-0605.png)

1. The flow is waiting for approval.

   ![](images/M03/E2T4S8-0605.png)

1. Open a new tab and navigate to `https://outlook.com`, to open Outlook mail and Sign in with Lab credentials. 

1. You should have an approval request email, select to open it.

    ![](images/img-01-47.png)

1. Select **Approve** to approve the request and select **Submit**.

    ![](images/M03/pp110.png)

1. Navigate back to the flow browser tab. The flow should succeed.

    ![](images/img-01-48.png)

1. Navigate to the **Power Platform admin center**, and select **Environments (1)**. Click on **Refresh (2)** The new environment **Central Apps Test (3)** should be listed there.

    ![](images/img-01-49.png)

1. You should also get an email.
 
    ![](images/E2T4S14-0605.png)

1. You may test for request rejection if you like.

### Additional Information 

#### CoE Environment Management Sample Implementation

#### The CoE starter kit includes a sample implementation of an environment management process you can tailor to your own needs. The following diagram illustrates the high-level process.

![](images/M03/M3-EX3-overview.png)

##### Using the starter kit process can save you time, but as you saw in Exercises 1 and 2 the platform also supports you in building your custom processes.

## Exercise 3: Welcome New Makers (Optional if you have time)

In this exercise, you will be importing a pre-built flow that is designed to identify new app makers and welcome them by sending an email with some information for new makers. 
Additionally, the flow will add the user to an Office 365 group, so you have an easy way to communicate with all the makers in the company.

### Task 1: Create Office 365 Group

In this task you will, set up a Microsoft 365 group in Azure AD called Lab Admin Makers and copy its Object ID for use in the flow.

1. Navigate to the **Azure portal** in a new tab with the following URL:

   ```
   https://portal.azure.com/
   ```

1. If prompted to sign in, sign in with the lab credentials.

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Cancel** to skip the tour.

1. On the search bar, search for **Microsoft Entra ID (1)** and select **Microsoft Entra ID (2)**.

   ![](images/M03/E3T1S4-0605)

1. Under **Manage** select **Groups**.

   ![](images/M03/E3T1S5-0605.png)

1. Select **+ New group**.

   ![](images/M03/E3T1S6-0605.png)

1. Select the following:

   - Group Type: **Microsoft 365 (1)**
   - Group Name: **Lab Admin Makers (2)**
   - Click on **Create (3)**

      ![](images/M03/E3T1S7-0605.png)

1. Select **All groups (1)**, and select **Lab Admin Makers (2)**. 

   ![](images/M03/E3T1S8-0605.png)

1. Select **Properties (1)** and copy the **Object id (2)**.

   ![](images/M03/E3T1S9-0605.png)

1. Paste the **Object Id** to a notepad, you will need it in further task.

### Task 2: Import Flow

In this task you will, import the Send Welcome Email flow into the Power Platform CoE environment, configure necessary admin, Outlook, and Office 365 connections, and complete the setup.

1. Navigate to the **Power Platform admin center** and ensure that you are in the **Power Platform COE** environment.

   ![](images/coe1.png)

1. Click on **Settings**

   ![](images/coe2.png)

1. Expand the **Products (1)** and click on **features (2)**.

   ![](images/coe3.png)

1. Scroll down to **Create new canvas app and cloud flows in Dataverse solutions** and ensure that **both toggles are turned off (1)**. Then, select **Save (2)**.

   ![](images/M03/E3T2S4-0605.png)

1. Navigate to **Power Automate**. Make sure **Power Platform COE** environment is selected. 

1. Select **My Flows (1)** and click **Import (2)** and select **Import Package (Legacy) (3)**.

   ![](images/img-01-51.png)

   >**Note:** For this step, you may not be able to access the content while you are in Incognito mode. If this is the case, simply switch to your normal browser.

1. Select **Upload** and navigate to `C:\LabFiles\PPAdminAttendee%20(1)\PPAdminAttendee\M03 - HOL - Alert and Act` **(1)**, select the **Send Welcome Email (2)** zip file and select **Open (3)**.

   ![](images/M03/ppt36.png)

1. This file will be available in the lab resource files you downloaded, named **SendWelcomeEmailToNewPowerAppsMakers_20190529192359.zip**.

   ![](images/M03/M3-EX4-T2-S5.png)

1. Once the file is uploaded, on the **Import package**, select Configure for the flow.

   ![](images/M03/M3-EX4-T2-S6.png)

1. On the **Import setup** select **Create as new (1)** and select **Save (2)**.

   ![](images/M03/E3T2S10-0605.png)

1. Select **Configure** for **Power platform for Admins Connection**.

    ![](images/M03/pv57.png)

1. Select the available connection **(1)** and select **Save (2)**.

   ![](images/M03/E3T2S12-0605.png)

1. Select Action for **Office 365 Outlook Connection**.

   ![](images/M03/pv59.png)

1. Select the available connection **(1)** and select **Save (2)**.

   ![](images/M03/E3T2S14-0605.png)

1. Select **Configure** for **PowerApps for Admins Connection**.

   ![](images/M03/pv61.png)

1. Select the available connection and select **Save**. 

1. If the connection is not listed, then follow the below steps:

    - Click on **+ Create new**.

    - Select **+ New connection**.

      ![](images/img-01-52.png)

    - Search for **Power apps (1)**  and select **PowerApps for Admins (2)**.

      ![](images/img-01-53.png)

    - On the **Connect to Power Apps for Admins** page, select **Create**.

      ![](images/img-01-54.png)

    - On the **Pick an account** page, select the **<inject key="AzureAdUserEmail"></inject>**.

    - On the **Confirmation required** page, select the check-box of the **I have verified this request and trust the source (1)** and select **Allow access (2)**.

      ![](images/img-01-55.png)

   - You should now have the connections listed in the image below.

      ![](images/img-01-56.png)

   - Go back to the **Import package** page.

      >**Note:** If you are unable to see the **Flow import** page, follow the steps from 09–15 and directly jump to step 20.

   - Select **Refresh list**, select the connection you just added, and select **Save**.

      ![](images/img-01-57.png)

1. Select **Configure** for **Office 365 Group Connection**.

    ![](images/M03/ppt38.png)

1. Select the available connection and select **Save**.   

1. If the connection is not listed, then follow the below steps:    

    - Select **+ Create new**.

      ![](images/img-01-58.png)

    - Select **+ New connection**.

      ![](images/img-01-52.png)

    - Search for **Office 365 Groups (1)** and select **Office 365 Groups (2)** from the new connection list.

      ![](images/img-01-59.png)

    - On the **Connect to Office 365 Groups** page, select **Create**.

      ![](images/img-01-60.png)

    - On the **Pick an account** page, select the **<inject key="AzureAdUserEmail"></inject>**.

    - On the **Confirmation required** page, select the check-box of the **I have verified this request and trust the source (1)** and select **Allow access (2)**.

      ![](images/img-01-61.png)

   - You should now have the connections listed in the image below.

      ![](images/img-01-62.png)

   - Go back to the **Import package** page. Select **Refresh list**, select the connection you just added, and select **Save**.

      ![](images/img-01-57.png)

1. Select **Configure** for **Office 365 Users Connection**.

   ![](images/img-01-63.png)

1. Select the available connection and select **Save**.   

1. If the connection is not listed, then follow the below steps:

    - Select **+ Create new**.

      ![](images/img-01-58.png)

    - Select **+ New connection**.

      ![](images/img-01-52.png)

    - Search for **Office 365 Users (1)** and select **Office 365 Users (2)** from the connection list.

      ![](images/img-01-64.png)

    - On the **Connect to Office 365 Users** page, select **Create**.

      ![](images/img-01-65.png)

    - On the **Pick an account** page, select the **<inject key="AzureAdUserEmail"></inject>**.

    - On the **Confirmation required** page, select the check-box of the **I have verified this request and trust the source (1)** and select **Allow access (2)**.

      ![](images/img-01-66.png)

   - Navigate back to the **Import package** page, select **Refresh list**, select the connection you just added, and select **Save**.

      ![](images/img-01-57.png)

1. Select **Import** and wait for the import to complete.

    ![](images/img-01-68.png)

1. The flow should import successfully.

    ![](images/img-01-69.png)

### Task 3: Edit and Test Flow

In this task you will, edit the flow to use the created group’s ID, turn it on, and test it by creating a new app. Verify that the maker is added to the group and receives a welcome email.

1. Navigate to Power Apps maker portal with the following URL, and ensure to select the Central Apps Test environment.

   ```
   https://make.powerapps.com/
   ```

1. On the left navigation menu, select **Apps (1)**, then select **+ New app (2)** > **Start with a page design (3)**.

   ![](images/M03/E3T3S2-0605.png)

1. On the **Start with design** page, select **Create from blank** option.

   ![](images/img-01-70.png)

1. On the **Start with a blank canvas** page, select **Tablet size**.

   ![](images/img-01-72.png)

1. The app designer should open. Select **Save** at the top right of the page.

   ![](images/M03/pv63.png)

   >**Note:** Select **Skip** on the **Welcome to Power Apps Studio** page.   

1. Enter **Test app (1)** for App name and select **Create (2)**.

   ![](images/M03/pv64.png)

1. Go back to the **Power Apps** main page by selecting the **Back** button.

   ![](images/M3-EX4-T3-S6.png)

1. Select **Solutions (1)**. Click on  **Publish all customizations (2)**.

   ![](images/M03/pv65.png)

1. Wait for the publishing to complete.   

   ![](images/M03/pv66.png)

1. Navigate to **Power Automate**. Select the **Power Platform CoE** environment.

1. Select **My Flows (1)**. Search for **New Maker (2)** and then click on **Edit (3)** icon in the **Admin Alert | New Maker**.

    ![](images/M03/pv67.png)

1. Expand the **Recurrence** and make sure the flow is set to run once a day.

    ![](images/M03/M3-EX4-T3-S13.png)

1. Expand the **OfficialGroupID** box. Clear the current **Group ID**.

1. Copy the **Object Id** from your notepad and paste it in the **OfficialGroupID** box.

    ![](images/M03/pv68.png)

1. You may examine the steps of the flow. Select **Save**.

    ![](images/M03/pv69.png)

1. Select on the **back button**.

    ![](images/M03/pv70.png)

1. **Turn on** the flow if it is off.

    ![](images/M03/pv71.png)

1. Select **Run**.

    ![](images/M03/pv72.png)

1. Select **Run Flow**.

    ![](images/M03/pv73.png)

1. Select **Done**. **Refresh (1)** every few seconds until the flow status changes. Your flow run should succeed **(2)**.

    ![](images/M03/pv74.png)

1. Go back to the **Azure portal**. Select **Microsoft Enta ID**. Select **Groups** under **Manage**.

   ![](images/M03/pv52.png)

1. Select **All groups**. Search for **Lab Admin Makers** and then select it.

    ![](images/M03/ppt40.png)

1. Select **Members**. You should have at least one member.

    ![](images/M03/ppt42.png)
    
1. Navigate to [Outlook](https://outlook.office365.com/). You should get a welcome email. Open the email. If you don’t get an email, it is probably because you didn’t create an application in the past 24 hours, create a new Power App and run the flow again.
    
    ![](images/img-01-73.png)

## Summary

In this lab, you have accomplished the following:

- Exercise 1 - Created Environment Request Form
- Exercise 2 – Created Environment on Form Submit
- Exercise 3 – Welcome New Makers (Optional if you have time)

### You have successfully completed this module. Click **Next** from the lower right corner to move on to the next page.

![Launch Azure Portal](images/gp8.png)
