# Lab 7: Building a Personal Work Dashboard with Microsoft Copilot Cowork (Read Only)

### Estimated Duration: 30 minutes

## Overview
Modern knowledge workers spend a significant amount of time switching between Outlook, Teams, Calendar, and OneDrive to identify priorities and track ongoing work. Microsoft Copilot Cowork enables users to automate these repetitive activities by orchestrating Microsoft Graph data, generating personalized outputs, and scheduling recurring tasks that continuously refresh with the latest information.

In this lab, you will use Microsoft Copilot Cowork to build a personalized HTML work dashboard that consolidates important information from Microsoft 365 services into a single, interactive view. You will configure Cowork to gather data from Outlook, Teams, Calendar, OneDrive, and Microsoft Search, generate a visually rich dashboard with actionable insights, schedule automatic refreshes, and customize the dashboard to suit your preferences. By the end of the lab, you will have an automated work dashboard that provides a centralized view of your daily priorities while demonstrating how Copilot Cowork can streamline personal productivity workflows.

>**Note:** This is a read-only lab intended to introduce the key concepts and capabilities of building automated dashboards in Microsoft 365 Copilot Cowork. No hands-on activities are performed in this exercise, in order to manage credit consumption for the workshop. Participants will gain the foundational knowledge needed to understand how dashboards are built, customized, and scheduled to refresh.

## Objectives
After completing this lab, you will be able to:

- Access and navigate Microsoft Copilot Cowork.
- Build a personalized HTML work dashboard using Microsoft Graph data.
- Generate a dashboard that consolidates calendar events, emails, Teams chats, OneDrive activity, and actionable insights.
- Schedule recurring dashboard refreshes and configure automated email delivery.
- Verify scheduled task execution and monitor dashboard updates.
- Customize the dashboard layout and appearance, including theme preferences and content sections.
- Manage scheduled Cowork tasks by running, editing, pausing, or deleting automated workflows.

## Task 1 - Open Copilot Cowork

In this task, you will sign in to Microsoft 365 Copilot and navigate to the Cowork experience, ensuring your environment is ready to build and automate AI-powered productivity workflows.

1. Open your browser and navigate to **Microsoft 365 Copilot** using the URL

    ```
    https://m365.cloud.microsoft/
    ```

1. On the **Microsoft 365 Copilot** page, click **Sign in**.

    ![](./media/n1.png)

1. You'll see the **Sign into Microsoft 365 Copilot** tab. Here, enter your **credentials (1)** and select **Next (2)**:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

     ![Enter Your Username](media/n2.png)

1. Next, provide **Temporary Access pass**, and select **Sign In (2)**:

   - Enter **Temporary Access Pass:** <inject key="AzureAdUserPassword"></inject> **(1)**

        ![](./media/n3.png)

1. If **Action required** pop-up window appears, click on **Ask later**.

1. If prompted to **stay signed in**, you can click **No**.

    ![](./media/n4.png)

1.  Confirm you land on the Microsoft 365 home page.

    ![](./media/n5.png)

1. Click on the **Cowork** tab in the left navigation menu , to switch to Cowork

    ![](./media/n6.png)

## Task 2 - Building Dashboard using Cowork

In this task, you will use Microsoft Copilot Cowork to generate a personalized HTML work dashboard by gathering information from Outlook, Teams, Calendar, OneDrive, and Microsoft Search. The dashboard will provide a centralized view of your meetings, emails, projects, and other important work items.

1. In the task input box, enter the following prompt (1) and then click the **Submit (2)** icon.

    ![](./media/n7.png)

    ```
    Build me a personal work dashboard as a single HTML file at output/dashboard.html.

    Gather data in parallel from across my Microsoft Graph:

    1. Calendar — today's remaining events and the next 7 days, including response status and organizer
    2. Inbox — unread, flagged, and high-importance messages from the last few days
    3. Teams — unread chats with last-message previews
    4. OneDrive — recently modified folders in my personal drive
    5. Search M365 for any action-required emails (access renewals, expense reminders, training notices)

    Infer my top 3–5 active projects by clustering recurring meetings and email threads. Surface a "Next" action for each.

    Render a single-page HTML dashboard with this layout:

    - Header: greeting with today's date and last-refresh timestamp
    - KPI strip (4 tiles): overdue actions, unread emails, meetings tomorrow, active projects — color urgent ones red, healthy ones green
    - Urgent banner: items that need attention today
    - Tomorrow's Schedule card: every event with time, title, and organizer
    - Training & Learning card: upcoming training sessions

    Visual style: soft blue gradient background, rounded white cards with subtle shadow, 'Segoe UI' font, Microsoft accent #0078d4.

    PORTABILITY REQUIREMENT — zero external network requests, zero JavaScript. No CDN scripts, no charting libraries, no external fonts.

    Every item must be clickable — link calendar events, emails, and Teams chats to their real webLink/webUrl via Microsoft Graph.

    Save to output/dashboard.html. After writing, confirm the file exists.
    ```
1. Observe that **Copilot Cowork** is processing the request, gathering data across your **calendar**, **inbox**, **Teams**, and **OneDrive** in parallel, as shown under the **Steps** panel on the right.

    ![](./media/n8.png)

     >**Note**: Cowork can take upto 5-10 minutes to complete the task

1. Verify that all steps are completed under **Workspace**, and that the **dashboard.html** file is generated under **Output**, then click on the **dashboard** file to view the result.

    ![](./media/n9.png)

1. Verify that the **dashboard.html** file opens successfully, displaying a personalized dashboard with KPI cards for **Overdue Actions**, **Unread Emails**, **Meetings Tomorrow**, **Teams Unread**, **Active Projects**, and **OOF This Week**, along with a **Needs your attention today** section.

    ![](./media/n10.png)

1. Under **Output**, click the **more options (1)** icon next to **dashboard.html**, and review the available options: **Share**, **Download**, **Open in OneDrive**, **Open location**, and **Copy link**.

    ![](./media/n30.png)

## Task 3 - Schedule the Hourly Refresh

In this task, you will configure a recurring Cowork task to automatically refresh your work dashboard throughout the day. You will also verify that the scheduled task executes successfully and updates the dashboard with the latest information.

1. In the task input box, enter the following prompt (1) and then click the **Submit (2)** icon.

    ![](./media/n12.png)

    ```
    Set up a scheduled task that refreshes output/dashboard.html once daily at 8:00 AM Pacific time, and don't ask me to confirm it.
    Use the same data-gathering and rendering instructions from the dashboard we just built.

    Each run, also send me an email:

    To: my own email address
    Subject: "Your Daily Work Dashboard - [today's date in M/D format]"
    Body: brief greeting noting the dashboard is attached and clickable
    Attachment: output/dashboard.html

    Name the task "Daily work dashboard refresh"
    ```

1. On the **Create recurring task?** prompt, review the **Name**, **Repeat**, **Run in**, and **Description** details, ensure **Run once now** is checked, then click **Always allow Setup scheduled prompt**.

   ![](./media/n31.png)

1. Confirm that the message **"Done — your scheduled task is now active"** is displayed, verifying that the **Daily work dashboard refresh** task has been scheduled successfully.

   ![](./media/n32.png)

1. Under **Workspace**, verify that the **Daily work dashboard refresh** task is listed under **Scheduled task**, running **Daily at 8:00 AM**, and click on it to open the task.

   ![](./media/n33.png)

1. On the **Daily work dashboard refresh** blade, verify that the task status is **Active**.

   ![](./media/n16.png)

1. Click **Run now** to trigger the scheduled task immediately.

   ![](./media/n17.png)

1. Verify that the task ran successfully, confirming a **silent refresh, no email** since it ran outside the **9:55 AM Pacific** window, with the **dashboard.html** file updated with the latest **Last refreshed** timestamp.

   ![](./media/n34.png)

1. Under **Output**, click on the **dashboard.html** file to view the refreshed dashboard.

   ![](./media/n35.png)

1. Verify that the **dashboard.html** file displays the updated **Last refreshed (1)** timestamp, confirming the dashboard has been refreshed successfully.

   ![](./media/n21.png)

## Task 4 - Explore and Customize the Dashboard

In this task, you will review the generated dashboard, explore its interactive sections, customize its appearance and content, and save your preferred layout for future dashboard generations.

1. Go through the dashboard.html file and review all the sections available, including the KPI overview, Needs your attention today, Tomorrow's Schedule, and Training & Learning.

   ![](./media/n22.png)

   ![](./media/n23.png)

1. Navigate back to the **Cowork** chat, then in the message box, enter **"Lock this dashboard format in for all future ones" (1)** and click **Submit (2)**.

   ![](./media/n26.png)

1. Verify that the message **"Locked in"** is displayed, confirming that the dashboard format has been saved as the standing house style for future requests.

   ![](./media/n27.png)

1. In the message box, enter **"Remove the training and learning card" (1)** and click **Submit (2)**.

   ![](./media/n36.png)

1. Verify that the message confirms the **Training & Learning card** has been removed from both the live dashboard and the locked-in standard.

   ![](./media/n37.png)

1. Click **dashboard.html** in the Output section to open and review the changes.

   ![](./media/n38.png)

## Task 5 - Manage Scheduled tasks

In this task, you will review the scheduled dashboard automation, explore the available management options, and verify how recurring Cowork tasks can be monitored and maintained.

1. Click the **Cowork (1)** tab and then select **Scheduled (2)**.

   ![](./media/n28.png)

1. Confirm the schedule is now active, with **Manage schedules (1)** and click **... (2)** to review the **Edit**, **Run now**, **Pause**, and **Delete** options.

   ![](./media/n39.png)

# Lab Summary
In this lab, you used Microsoft Copilot Cowork to create a personalized HTML work dashboard that consolidated information from Outlook, Teams, Calendar, OneDrive, and Microsoft Search into a single interactive view. You verified that the generated dashboard displayed key productivity insights, including upcoming meetings, unread emails, active projects, Teams activity, recent files, and priority actions.

You then automated the dashboard by creating a recurring scheduled task that refreshes the dashboard throughout the workday and delivers a daily email containing the updated dashboard at the designated time. After validating the scheduled task and confirming the dashboard refreshed successfully, you explored the generated dashboard, customized its appearance and content, and saved your preferred layout for future dashboards. Finally, you reviewed and managed the scheduled automation task, gaining experience with maintaining recurring Copilot Cowork workflows.

You have successfully built, automated, customized, and managed a personal productivity dashboard using Microsoft Copilot Cowork, demonstrating how AI-powered workflows can simplify daily work management and provide timely, actionable insights across Microsoft 365.

## You have successfully completed the Lab!

Now, click on **Next >>** from the lower right corner to move on to the next page.

![Image](./media/nxtd1.png)

