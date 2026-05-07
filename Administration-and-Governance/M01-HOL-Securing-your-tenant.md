# Lab 1: Securing your Tenant

### Estimated Duration: 60 Minutes

## Overview

In this hands-on lab, you will act as an **Environment Administrator** for **Fabrikam**, supporting the adoption of the Power Platform while ensuring **compliance with the organization's data and security policies**. 

Your responsibilities include enabling employees to build Power Apps and Power Automate flows to boost productivity, while also maintaining control over data governance. You will begin by **assessing existing Power Platform usage** across the organization and then implement baseline security policies to align with **Fabrikam’s compliance requirements**.

## Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Exploring existing Power Platform usage
- Exercise 2 – Plan an environment strategy
- Exercise 3 – Plan a DLP strategy
- Exercise 4 – Evaluate the impact of adding DLP
- Exercise 5 – Configure a security role

<!--
### Lab Test Environment

This lab is designed to be completed in an environment setup for multiple students to complete the Admin in a day series of hands-on labs. We will be providing an environment for you to 
utilize for this course.

You will be assigned one or more users to use to complete the tasks. Because this is a shared environment, some tasks that require a tenant Global Administrator or a Service Administrator will already be completed. Your account will only be an environment administrator.
-->

## Exercise 1: Exploring existing Power Platform usage

In this exercise, you will be exploring the tenant to see what Power Platform assets have already been created. Specifically, you will be looking at the following:

- Environments that have been created
- Data Loss Prevention (DLP) policies.

### Task 1: Review existing environments

In this task you will, navigate to the Power Platform admin center to explore, filter, and analyze environments, security roles, and apps created in the default environment.

1. Open a new tab and navigate to **Power Platform admin center** by following the URL:

    ```
    https://aka.ms/ppac
    ```

    >**Note:** Close the Pop up screen. If you recieve any feedback pop-up, close it.

1. On the **Power Platform admin center** page, from the left navigation menu, select **Manage**.

    ![](images/M01/manage.png)

1. Click on the **Environments** and review the list of environments. These are the environments that are available for you to manage.

   ![](images/M01/envlist.png)

1. Notice the **Type** column, you can see Fabrikam is already using several types of environments.

1. You can filter and order environments. Select on the **Type (1)** column, select filter by **Production (2)**, and select **Apply (3)**.

   ![](images/M01/2.png)

1. You should now see only the **Production** type environments.

   ![](images/M01/prodenv.png)

1. Select on the **Type (1)** column again and filter by **Default (2)** and **Production (3)**, and select **Apply (4)**.

   ![](images/M01/dp.png)

1. You should now see **Production** and **Default** environments.

1. Select on the **Environments (1)** column, select **Sort order** by **Ascending (2)**, and select **Apply (3)**.

   ![](images/M01/4.png)

1. The list of environments will show **Production** and **Default** environments ordered by environment name in ascending order.

   ![](images/M01/PDA.png)

1. Now remove the filters by clicking on the **Environment (1)**, clicking on **Clear all filters (2)**, and then **Apply (3)**. You should see all environments.

    ![](images/img-01-03.png)

1. Next, notice all the environments with **Thrive Hr** in the name. These are a set of environments Contoso uses to manage the lifecycle of its Thrive apps, a suite of employee 
    engagement apps. They are built in Thrive Hr - Dev and then are promoted to Test -> UAT-> Production after testing by your admin team.

    ![](images/M01/envlist.png)    

1. Select on the **Type (1)** and filter by **Default (2)** and then **Apply (3)**.

    ![](images/img-01-04.png)  

1. This is the environment in which all users are makers and can build their apps and flows. Think of this environment as supporting personal productivity use of the platform. This is also the default location used by any customizations built with Power Apps in Office apps. The default environment can’t be deleted, but you can rename it to make its purpose clear.

1. Select the default environment by selecting the name in the list to drill down into the detail page.

    ![](images/M01/denv.png)

1. In the **Access** section, you’ll notice that there are multiple options to choose from, which can be used to determine who has access to which items.

    ![](images/img-01-05.png)

1. Select **See all** under **Security Roles**.

    ![](images/M01/seeallsec.png)

1. From here, you can review all of the **Security roles** for your company and manage their access to the company’s data. By default, users have access to all security roles. The business unit currently listed is the same as the tenant and these are assigned to all users by default. Managed roles can be modified to create.

    ![](images/M01/roles.png)    

1. Use the search box in the top right to enter **Environment Maker (1)**, then select the only result for **Environment Maker** security role and notice the **Business unit (2)**.

    ![](images/img-01-06.png)

1. Go back to the Environment Details page by clicking on the **default environment** name.

    ![](images/img-01-07.png)

1. In the **Resources** section, select **Power Apps**.

    ![](images/M01/pa.png)

1. These are apps built by users in your default environment. Notice that many of them are just test names because this is where a lot of users will experiment and build their first app. As you scroll down the list, you might notice some names are more deliberate, e.g., Product Showcase. Later in the course, we will talk about how to identify these upcoming apps so you can help guide them to ensure they mature and have adequate governance.

    ![](images/img-01-08.png)

### Task 2: Review existing Data policies

In this task, you will examine existing DLP policies, including global and exception policies, and review how connectors and environments are configured.

1. From the left navigation menu, select **Security (1)**, then click on **Data and privacy (2)** and select **Data policy (3)**.

    ![](images/M01/L1T2S1-0505.png)

1. Review the list of existing policies.

    ![](images/M01/L1T2S2-0505.png)

    - As an environment admin, you will only see policies that impact environments of which you are a member. In this lab environment, you are a member of the default environment and the Thrive environments, so you will see policies that impact those environments.

    - As an environment admin or regular environment user, you will also be able to see any tenant-wide DLP policies applied to your environment. However, you would not be able to edit 
      those tenant-side DLP policies.

    - As a Global Admin, Admin, Power Platform Service Admin, or D365 Service Admin in your tenant, you will see all policies that exist in your tenant, even those that you did not 
      create.

1. Notice that the **Contoso Global DLP** policy is intended to span all environments (except selected ones) and represents the Global DLP policy. In this lab environment, the **Contoso Global DLP** policy has 4 environments selected instead of "All except 4".

1. You will also notice a DLP for **Thrive Exceptions DLP**. That team had worked with the IT department to agree on exceptions they needed for their environments and their environment would be excluded from the Contoso Global DLP. This exception DLP policy would have their environments included and apply only to them.

   ![](images/po-05.png)

1. Select the **Contoso Global DLP (1)** and select **Edit Policy (2)**.

   ![](images/M01/poledit.png)

1. Select **Prebuilt connectors (1)** and review the **Business (2)** connectors.

    ![](images/pb.png)

1. Select **Scope (1)** and **Environments (2)** to see how it they are configured.

   ![](images/es.png)

1. Once finished, select **Cancel** button in the bottom right to head back to the Data Policies screen.

   ![](images/cancel.png)

1. Select the **Thrive Exception DLP (1)** and select **Edit Policy (2)**.

    ![](images/tep.png)

1. Select on the **Prebuilt connectors (1)** and select the **Business (2)** tab. Based on the use case for the Thrive application the connectors in the Business group have been established. You can also see how Scope and Environments are configured to only select the Thrive environments.

    ![](images/bui.png)

1. To exit this screen, select the **Cancel** button on the bottom right of the screen again.

    ![](images/can.png)

## Exercise 2: Plan an environment strategy

In this exercise, you will be planning an environment strategy for Fabrikam. You will review the scenario for Fabrikam that explains their current situation. After reviewing, you will evaluate and propose an environmental plan.

### Task 1: Read about the current situation at Fabrikam

In this task, read the following and take notes that would help you propose an environment plan for Fabrikam.

You have recently joined the newly formed Power Platform Center of Excellence team at Fabrikam and are responsible for establishing a governance strategy. Currently, there is no 
governance process established, and employees can create apps, flows, and even environments without any control. Fabrikam has been in existence for 40 years and has 4,500 employees 
at multiple office locations in the US, UK, and EU. Fabrikam employees are all licensed for Office 365 E3, and a growing number of them have either Power Automate or Power Apps per user 
licenses. Over the last 6 months, Fabrikam’s management realized that this was greatly improving productivity, but they recognised that without some planned governance, it could easily get 
out of control. About 50 of the users are more advanced power users of the platform, always looking at ways to push its limits. Fabrikam’s sales team of 100 users also uses a heavily 
customized Dynamics 365 Sales app deployment.

One of the first things you did was look in the admin center to see how many environments there were. Currently, in the tenant, there are 45 environments with a variety of names that users 
choose. The majority of the applications looked like they were in the default environment or a couple of other custom environments that had been created. There was one environment that 
was the production Dynamics 365 application environment used by the sales team.

The most organized department is market research; they built an application that is used daily for conducting their market surveys. Currently, there is just a single custom environment 
named Market Research that supports the application. There are a couple of people in the department who are app makers, making all the changes. They tend to do them in the late 
afternoons and evenings and publish them when nobody's around to avoid impacting other users. There is currently no testing done before the app is published, other than by the person 
making the changes. They are open to the testing idea but are not sure how to do it with a single environment.

You found out that the new environments have stopped being created simply because they have run out of storage from creating too many environments. When you asked about this, you were 
handed a stack of requests that claimed they needed new environments. The following are the priority requests; we will ask you to help identify how to handle these when you fill out the 
environment strategy template.

- Request 1: A user would like to build a set of Power Automate flows that help organize their Outlook inbox and tag emails.

- Request 2: The VP of Service wants to build some custom apps to support their teams; like how the market research team has done.
    
- Request 3: Marketing wants to build an app that makes it easy to publish tweets on Twitter using the Twitter connector. They also plan to create Power Automate flows that notify 
    them of mentions along with the sentiment of the message.

- Request 4: HR would like to try the Crisis Comms app that Microsoft published and would like an environment for it to run in.
    
- Request 5: A user would like to build an app that uses a custom connector for a 3rd party service and also uses the Dropbox connector.

Yesterday, you got some good news: another 30GB of storage capacity for environments had been procured. You also got permission to put in place the necessary steps to ensure it does not 
get wasted.

### Task 2: Build an Environment Plan

In this task, you use the information from Task 1’s scenario to help you propose an environment plan for Fabrikam. To help you build the plan we have prepared a worksheet with questions for you to answer.

1. In the **LabVM**, open the File explorer, navigate to `C:\LabFiles\PPAdminAttendee%20(1)\PPAdminAttendee\M01 - HOL - Securing your tenant\Resources` **(1)** then open **M01 – HOL Environment Plan Worksheet.docx (2)** from the Resources folder.

    ![](images/M01/pp15.png)

1. Complete it by answering each of the questions. You should spend no more than 10 minutes on this before proceeding to the next task.

### Task 3: Review the example environment plan and compare it to yours

In this task, we have provided you with a completed environment plan. Review the answers and compare them to the ones you built in the prior task.

1. Open the Example Environment Plan document **M01 – HOL Environment Plan Example.docx** and compare the answers to the one you completed in the previous task.

    ![](images/M01/pp16.png)

## Exercise 3: Plan a DLP strategy

In this exercise, you will be planning a DLP strategy for Fabrikam using the same scenario background information from the last exercise.

### Task 1: Build a DLP Plan

In this task, you use the information from the last exercise’s scenario to help you propose a DLP plan for Fabrikam. To help you build the plan we have prepared a worksheet with questions 
for you to answer.

1. IN the **LabVM**, open **M01 – HOL DLP Plan Worksheet.docx** from the Resources folder and complete it by answering each of the questions. You should spend no more than 10 minutes on this before proceeding to the next task.

### Task 2: Review the example DLP plan and compare it to yours

In this task, we have provided you with a completed environment plan. Review the answers and compare them to the ones you built in the prior task.

1. Open the Example Environment Plan document **M01 – HOL DLP Plan Example.docx** and compare the answers to the one you completed in the previous task.

2. Talk to your trainer about any significant differences that do not make sense to you.

## Exercise 4: Evaluate the impact of adding DLP

In this exercise, you will be creating a DLP policy and evaluating its impact on the user experience.

### Task 1: Create a trial environment

In this task, you will set up a new trial environment with Dataverse and assign a security group.

1. Navigate back to the **Power Platform admin center**.

1. From the left navigation menu, select **Manage (1)**, select **Environment (2)** and then click on **+ New (3)**.

   ![](images/newenv.png)

1. On the **New environment** page, enter the following details:

    - Type: **Trial (1)** 
    - Region: **United States - Default (2)**
    - Name: **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (3)**
    - Expand **Change default settings** 
    - Add a Dataverse data store: **Yes (4)** 
    - Select **Next (5)**

        ![](images/img-01-11.png)

        ![](images/img-01-12.png)

1. Leave the default values for **Language (1)** and **Currency (2)**. Under **Security group** section, click **+ Select (3)**.

    ![](images/img-01-14.png)

1. Then set your security group to **None (1)** and then select **Done (2)**.

   ![](images/M01/E4T1S5-new-0505.png)

1. On the **Add Dataverse** page, select **Save**.

   ![](images/M01/E4T1S6-0505.png)

1. Wait for the environment to be created. Please do **refresh** the page. The state will change to **Ready** when the environment is ready.

    ![](images/M01/e4t16.png)

### Task 2: Create a flow to get the weather

In this task you will, build a simple scheduled flow that retrieves weather data and sends it via email.

1. Navigate to the **Power Apps** portal, click on the **Environment (1)** and select the **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** **(2)** environment that you have created.

   ![](images/M01/E4T2S1-0505.png)

2. On the **Power Apps** portal, select **Flows (1)** from the left, select **+ New flow (2)** drop down and select **Scheduled cloud flow (3)**.

   ![](images/po-13.png)

3. Enter **Weather Flow (1)** for **Flow Name**, select **Repeat every 1 Day (2)**, and select **Create (3)**.

    ![](images/M01/E4T2S3-0505.png)

4. On the **Weather Flow** page, select **+ New step**.

    ![](images/M01/E4T2S4-0505.png)

5. Search for **MSN (1)** and select **Get current weather** **(2)**.

   ![](images/img-01-16.png)

6. Provide your **Location (1)**, select your preferred **Units (2)**, and select **+ New step (3)**.

   ![](images/M01/E4T2S6-0505.png)

7. Search for **send an email (1)** and select **Send an email (V2) (2)**.

   ![](images/img-01-18.png)

8. On the Send an Email (V2) step, provide the following details:

    - **To:** **<inject key="AzureAdUserEmail"></inject> (1)**
    - **Subject:** **Current Weather (2)**
    - **Body:** Enter **Current weather for: (3)**
    - Then select the **Location (4)** value from the Insert parameters pane below. This will add the dynamic value for location to the body of the email.

        ![](images/M01/E4T2S9-0505.png)

10. Hit the **[ENTER]** key, and type **Temperature: and Conditions: (1)** in seperate lines and then select **Temperature (2)** and **Conditions (3)** value from the insert parameters pane below. 

    ![](images/M01/E4T2S9.1-0505.png)

13. Select **Save**.

    ![](images/img-01-21.png)

14. Go to **My Flows** by selecting the **back arrow button** of Weather Flow located on the top left of the page.

    ![](images/M01/E4T2S11-0505.png)

15. Select the checkbox of the flow **(1)** and select **Run (2)**.

    ![](images/M01/E4T2S12-0505.png)

17. Select **Run flow**.

    ![](images/M01/E4T2S13-0505.png)

18. Select **Done** and wait for the flow run to complete. 

19. Open a new tab in the same browser. Copy and paste the following link in the browser https://outlook.office365.com/ to navigate to **Outlook**, and sign in with the ODL credentials.  Now you should get an email with the weather information.

    ![](images/M01/E4T2S14-0505.png)

### Task 3: Create a DLP Policy

In this task, you will create an environment-specific DLP and see how it impacts your workflow.

1. Navigate to the Power Apps portal, from the top right corner, click on the **gear icon (1)** and select **Admin Center (2)** to navigate to the **Power Platform admin center**.

   ![](images/M01/E4T3S1-0505.png)

1. On the **Power Platform admin center** select **Security (1)** from the left pane, select **Data and privacy (2)** and click **Data Policy (3)**.

   ![](images/M01/e4t29.png)

1. Click on **+ New Policy**

    ![](images/M01/e4t10.png)

1. Enter **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (1)** for Name and select **Next (2)**.

   ![](images/img-01-22.png)

1. On the **Prebuilt connections** search for **Microsoft Dataverse (1)** then select **Microsoft Dataverse (2)**, and click on **Move to Business (3)**. Choose carefully, you may have to expand the Name column to differentiate 
   between connectors in your search results.

   ![](images/M01/E4T3S5-0505.png)

1. Search for **SharePoint (1)**, select **SharePoint (2)** and click on **Move to Business (3)**.

   ![](images/M01/E4T3S6-0505.png)

1. Search for **Outlook (1)**, select **Office 365 Outlook (2)** and click on **Move to Business (3)**.

   ![](images/M01/E4T3S7-0505.png)

1. Select the **Business (1)** tab. You should now have **three connectors (2)** moved to Business. Then click on **Next (3)**.

   ![](images/M01/E4T3S8-0505.png)

1. Skip the Custom connector by selecting the **Next** button, we won’t be using any in this example.

1. Select **Add multiple environments (1)** from the options, then select **Next (2)**.

    ![](images/multenv.png)

1. Choose the environment you created **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (1)** and select **+ Add to Policy (2)**. Once done, select **Next**.

    ![](images/M01/E4T3S11-0505.png)

1. Review the policy, to make sure you have **(3) Business**  **(1)** connectors added, and only  **1 environment(s)** **(2)** selected and select **Create policy (3)**.

    ![](images/M01/E4T3S12-0505.png)

1. Navigate to the **Power Apps** portal, from the left navigation menu, click on **Power Platform (1)** and then select **Power Automate (2)**.

    ![](images/M01/E4T3S13-0505.png)

1. Make sure you are in **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** environment.  

    ![](images/M01/E4T3S14-0505.png)

1. On the **Power Automate** page, from the left navigation menu, select **My flows (1)**. The flow should now be suspended because of the **DLP** you created. **Select to open the flow.** This can take up to 5 minutes. Wait a few minutes and then select refresh.

    ![](images/M01/E4T3S15-0505.png)

1. You should not be able to run the flow. There will be a notice at the top showing that the DLP is active and restricting access, and the **Status** should be suspended. Feel free to close the webpage/tab once you’ve confirmed it has been suspended.

    ![](images/M01/E4T3S16-0505.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="3379fa81-ffc4-49c5-82db-97274e81a612" />

## Exercise 5: Configure a security role

In this exercise, you will create a custom security role in Dataverse and then share a canvas app with that security role to see how it affects the user's access.

### Task 1: Import project management solution

In this task you will, import the Fabrikam Project Management solution, run the sample data flow, and test the canvas app with new project records.

1. Navigate to the **Power Apps** portal, and make sure you are in the **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> environment** you created earlier.

   ![](images/E5T1S1-0505.png)

2. On the left navigation menu, select **Solutions (1)** and click on **Import solution (2)**.

   ![](images/E5T1S2-0505.png)

3. On the **Import a solution** page, select **Browse**.

   ![](images/E5T1S3-0505.png)

4. Navigate to **C:\LabFiles\PPAdminAttendee%20(1)\PPAdminAttendee\M01 - HOL - Securing your tenant\Resources (1)** folder, select the **Fabrikam Project Management (2)** solution and select **Open (3)**.

   ![](images/M01/pp32.png)

5. One the file is **Uploaded (1)** select **Next (2)**.

   ![](images/E5T1S5-0505.png)

6. Select **Import** and wait for the import to complete. 

   ![](images/E5T1S6-0505.png)

7. You should get a **notification (1)** when the import succeeds. Select **Publish all customizations (2)** and wait for the publishing to complete.

   ![](images/E5T1S7-0505.png)

8. Select to open the **solution** you just imported.

   ![](images/E5T1S8-0505.png)

9. The solution should have six components.

    ![](images/E5T1S9-0505.png)

10. Select the **Import Sample Data – Projects (1)** flow. Please run this flow to insert sample project data for the app to use. Click on **Edit (2)**.

    ![](images/E5T1S10-0505.png)

12. At this point, you may be asked to sign in to the flow, click on **Sign in**.

    ![](images/E5T1S11-0505.png)

1. Select **Sign in** again for the **Microsoft Dataverse**

    ![](images/img-01-30.png)

    >**Note:** When prompted with the sign in window, please sign in with the ODL credentials.
        
1. Ignore the error message `Create and authorize OAuth connection failed`, and click on the back arrow button. 

    ![](images/M01/back.png)


1. Select the **Connection references (1)** tab from the left navigation menu. Click on the three dots next to the **Microsoft Dataverse (2)** connection reference and select **Edit (3)**.

    ![](images/E5T1S13new-0505.png)

1. On the Edit Microsoft Dataverse connection reference page, click on the **Connection (1)** dropdown and select **+ New connection (2)**.

    ![](images/E5T1S14new-0505.png)

1. You will be navigated to the Connections page, where you will search for **Dataverse (1)** and select **+ (2)** on Microsoft Dataverse.

    ![](images/E5T1S15new-0505.png)

1. On the Connect to Microsoft Dataverse page, select the Authentication Type as **OAuth (1)**, and then select **Create (2)**.

    ![](images/E5T1S16new-0505.png)

1. You will be prompted to sign in. Please sign in with the ODL credentials. On the Confirmation required window, check **(1)** the request and click on **Allow access (2)**. 

    ![](images/E5T1S17new-0505.png)

1. Navigate back to the Connection reference page in the Solution, select the **Microsoft Dataverse** connection reference, click on the three dots, and select **Edit (2)** again.

1. In the Connection dorpdown, now select the **<inject key="azureAdUserEmail"></inject> (3)** connection you just created and select **Save (4)**.

    ![](images/E5T1S18new-0505.png)

1. In the Solution, naviagte to **All (1)**, select the **Import Sample Data – Projects (2)** flow, and select **Edit (3)**.

    ![](images/E5T1S20new-0505.png)

1. Select **Continue**.

      ![](images/E5T1S21new-0505.png)

13. Select to expand the **Parse JSON** step.

    ![](images/E5T1S12-0505.png)

14. Examine the sample records the flow will create.

15. Select **Save** and wait for the flow to be saved.

    ![](images/E5T1S14-0505.png)

16. Go back to the details view of the flow by selecting the back button.

    ![](images/M01/back.png)

17. Open the **Import Sample Data – Projects** flow again.

18. **Turn on** the flow if Status is off.

19. Select **Run** to run the flow.

    ![](images/E5T1S28new-0505.png)

20. Select **Run flow**.

    ![](images/po-34.png)

21. If prompted, select **Done** and wait for the run to complete.

22. Select the **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** environment.

    ![](images/E5T1S31new-0505.png)

23. Go back to the solution page by selecting the **Back arrow** button.

    ![](images/E5T1S32new-0505.png)

24. Select **Apps (1)**, then click on the ellipses of **Project Admin (2)**, and click **Play (3)** to run the Canvas application.

    ![](images/E5T1S33new-0505.png)

25. The application should load, and you should see the sample project record the flow created. Select the **+ New** to create a new project.

    ![](images/E5T1S34new-0505.png)

26. Enter **Test Project (1)** for Title, select **Due date (2)** and select **Save and Close (3)**.

    ![](images/E5T1S35new-0505.png)

27. The application should create a new record and take you back to the list of projects.

     ![](images/E5T1S36new-0505.png)

28. Close the Project List application browser window or tab.

### Task 2: Create a security role

In this task, you will build a new Project Manager role, configure permissions on the Project table, and publish the changes.

1. Navigate to the **Power Apps** portal and make sure you have your sandbox environment selected and open the **Fabrikam Project Management** solution.

1. Select **+ New (1)** drop-down and select **Security (2)** > **Security role (3)**.

    ![](images/E5T2S2-0505.png)

1. Enter **Project Manager (1)** for **Role Name**, select your **Business unit (2)** from the drop down and select **Save (3)**.

   ![](images/E5T2S3-0505.png)

1. Search for **Project (1)**, locate the **Project** table and click on the name of the entity. This action will give this role User rights to the Project entity **(2)**.

    ![](images/E5T2S4-0505.png)

1. By clicking on the dropdown for the permissions under the read column, if you kept selecting the **Organization** on the label, it would increase the permissions.

   ![](images/E5T2S5-0505.png)

1. You will now give this role organization **Read** privilege. Select **Organization (1)** from the **None** drop-down  of the read column and click on **Save (2)**.

   ![](images/E5T2S6-0505.png)

1. Click on **<-Back** to navigate back to the Fabrikam Project Management page.

   ![](images/E5T2S7-0505.png)

1. Select **Publish all customizations** and wait for the publishing to be completed.

    ![](images/E5T2S8-0505.png)
 
## Summary

In this lab, you have accomplished the following:

- Exercise 1 - Explored existing Power Platform usage
- Exercise 2 – Planned an environment strategy
- Exercise 3 – Planned a DLP strategy
- Exercise 4 – Evaluated the impact of adding DLP
- Exercise 5 – Configured a security role

### You have successfully completed this module. Click **Next** from the lower right corner to move on to the next page.

![Launch Azure Portal](images/gp8.png)
