# Lab 1: Getting Started with Copilot Cowork

### Estimated Duration: 75 Minutes

## Overview
In this hands-on lab, you will get oriented to Copilot Cowork, the agentic workspace inside Microsoft 365 Copilot. Unlike traditional Copilot Chat, where you ask a single question and receive a single answer, Cowork can plan and carry out multi-step tasks on your behalf - reading your emails, checking your calendar, working with files, and delivering a finished result, all in one go. You will sign in to Microsoft 365, tour the Cowork home screen, generate sample emails and calendar events in Outlook, upload sample files to OneDrive, create a team in Microsoft Teams, and run your first tasks using starter tiles, typed prompts, and voice commands. You will also learn how to add context to a task, review task history and scheduled tasks, and explore the Customize area where Cowork's capabilities can be extended with plugins and skills.

>**Note:** Tasks 1 through 4 are prerequisite setup steps, not the core "Getting Started" walkthrough itself. Copilot Cowork works by acting on real data in your mailbox, calendar, files, and Teams, so before exploring what it can do, your environment needs sample emails, calendar events, OneDrive files, and a Teams channel in place. These four tasks create that data for use throughout this lab and every lab that follows. The actual "Getting Started" experience begins at Task 5 - complete Tasks 1 through 4 first, or later tasks will have nothing to work with.

## Objectives
In this lab, you will perform the following:

- Task 1: Sign In and Explore the Cowork Home Screen
- Task 2: Generate Sample Emails in Outlook
- Task 3: Generate Sample Calendar Events in Outlook
- Task 4: Upload Sample Files to OneDrive and Create a Team in Microsoft Teams
- Task 5: Run Your First Tasks with Cowork
- Task 6: Use the + Menu to Add Context to a Task
- Task 7: Explore Task History, Scheduled Tasks, and Task Ideas
- Task 8: Explore the Customize Area

## Task 1: Sign In and Explore the Cowork Home Screen

In this task, you will sign in to Microsoft 365, review how Copilot Cowork differs from Copilot Chat, and explore the layout of the Cowork home screen.

1. Review how Copilot Cowork compares to Copilot Chat.

    |     **Copilot Chat**     |               **Copilot Cowork**           |
    |:-------------------------|--------------------------------------------|
    | One question, one answer | Multi-step tasks from a single instruction |
    |   You guide each step    | Cowork plans and executes the steps itself |
    | Great for quick lookups  |  Great for complex, repeatable workflows   |
    |     No task history      |     All tasks are saved and searchable     |

2. Open the Edge browser and navigate to the Microsoft 365 portal with the below link and click on **Sign in**:

   ```
   www.office.com
   ```

   ![Sign in to Microsoft 365](media/1.png)

3. On the sign-in page, enter the provided email address and click **Next (2)**.
   - **Email/Username**: <inject key="AzureAdUserEmail"></inject> **(1)**

       ![Enter email address](media/2.png)

4. Enter the provided Temporary Access Pass and click **Sign in (2)**.
   - **Temporary Access Pass**: <inject key="AzureAdUserPassword"></inject> **(1)**

       ![Enter temporary access pass](media/3.png)

5. When prompted, select **No** on the Stay signed in? dialog.

   ![Stay signed in prompt](media/4.png)

6. At the top of the left panel, click on the **Cowork** tab.

    ![](media/5.png)

7. Click the **Auto** dropdown at the top and review the models available.

    ![](media/6.png)

    >**Note**: Leave the model set to Auto for this entire lab. Auto automatically selects the best available model for each task, so you do not need to choose one manually.

8. Click the **"..." (1)** icon at the top-right corner, select **Keyboard shortcuts (2)**, and review the list.

    ![](media/7.png)

    ![](media/8.png)

## Task 2: Generate Sample Emails in Outlook

In this task, you will use Cowork to generate and send 5 sample training emails to your own Outlook inbox for use in later labs.

1. In the Cowork pane, enter the below prompt **(1)** and click the **send (2)** button:

     ```
     I need you to seed my Outlook inbox with 5 sample training emails for a Copilot Cowork demo environment (Contoso Electronics / Project Orion ERP modernization scenario). Send each individually to my own email address so it lands as a received message in my Inbox. You have my approval to send all 5 without pausing for individual confirmation - send them one after another, then give me a final summary list (subject + time sent).

    For every email: proper business email (greeting, 2–3 short paragraphs or bullets, professional sign-off with sender name/title/company). Prefix the Subject line with the source tag in brackets. Do not literally attach files - mention any referenced attachment in the body text only.

    Send these 5, in order:

    1. [Northwind Retail] Subject: "Final Contract Review - Payment Milestone Clarification." From: Priya Desai, Procurement Lead, Northwind Retail. Reviewing the ERP contract, needs clarification on the payment milestone schedule before signing. Polite, slightly urgent - wants this resolved this week.

    2. [Fabrikam Industries] Subject: "Feature Request - Barcode Scanning & Warehouse Integration." From: Marcus Webb, IT Director, Fabrikam Industries. Requests barcode scanning and warehouse-management integration be added to the ERP build; needed for their distribution centers. Leave this request open/unresolved in tone.

    3. [Tailspin Toys] Subject: "URGENT: Production Issue Affecting Order Processing." From: David Chen, IT Support Lead, Tailspin Toys. Urgent tone - a production issue is blocking order processing right now, needs immediate attention, asks for a callback ASAP. Leave this issue open/unresolved in tone.

    4. [PMO] Subject: "Invitation – Steering Committee Meeting." Short agenda (3–4 bullet points covering Project Orion milestones, budget status, go/no-go checkpoints), a list of expected attendees (by role, not real people — e.g., Steering Committee members, Project Sponsor, PMO), a placeholder Teams link, and a note that a deck is attached.

    5. [PMO – Risk Management] Subject: "Risk Review Meeting – Follow-Up Notes." Summarizes 3 decisions made in a recent risk review, each with an owner name and a due date.

    Once all 5 are sent, give me a confirmation list showing each subject line and the time it was sent.
     ```

     ![](media/8(1).png)

2. After submitting the prompt, you can see that Cowork has started **processing** the request.

   ![](media/9.png)

3. Review the email generated by Cowork and click on **Send** to approve it.

   ![](media/10.png)

4. Review the second email generated by Cowork and click on **Send** to approve it.

   ![](media/11.png)

   >**Note**: Repeat the same steps and approve all the remaining 3 emails generated by Cowork.

5. Review the output generated with all 5 email details listed.

   ![](media/12.png)

6. To verify the emails were generated, click on the **Microsoft 365 app launcher (1)** and select **Outlook (2)**.

   ![](media/13.png)

7. If the **Your privacy matters** popup appears, click on **Continue**.

   ![](media/14.png)

8. Go to **Inbox (1)** and confirm that all the **sample emails (2)** are present.

    ![](media/15.png)

## Task 3: Generate Sample Calendar Events in Outlook

In this task, you will use Cowork to create 3 sample calendar events in Outlook to build out a realistic project calendar.

1. Go back to Microsoft 365 Copilot portal and in the Cowork pane, enter the below prompt **(1)** and click the **send (2)** button:

    ```
    I need you to create 3 sample calendar events on my Outlook calendar for a Copilot Cowork demo environment (Contoso Electronics / Project Orion ERP modernization scenario). Create all 3 without pausing for individual confirmation, then give me a summary table at the end (event title, date, time) once done.

    ## Rules for every event

    - I am the only attendee/organizer — do NOT invite or add any other person's email address, even if a name or company is mentioned. Any names/companies mentioned should appear as plain text in the description only.
    - Add a Microsoft Teams meeting link to each event.
    - Schedule them on the next 3 consecutive business days starting tomorrow (skip weekends), one per business day, in the order below.
    - If any time conflicts with something already on my calendar, shift only that one event by 30 minutes and note it in your summary.

    ## The 3 events

    Business day 1 — 2:00–3:00 PM
    Title: Steering Committee Review
    Description: Agenda: review of Project Orion milestones, budget status, and go/no-go checkpoints. 
    Attendees (for reference only, do not invite): Steering Committee members, Project Sponsor, PMO.

    Business day 2 — 10:00–11:00 AM
    Title: Security Assessment Meeting
    Description: Agenda: review of vulnerability assessment findings (high-risk and medium findings) and required remediation plan. 
    Attendees (reference only): Security Team, Compliance Officer, IT Director.

    Business day 3 — 10:00–11:30 AM
    Title: Go-Live Readiness Review
    Description: Agenda: walkthrough of the deployment readiness checklist (servers, backup, disaster recovery, monitoring), outstanding approval items, and the go-live decision. 
    Attendees (reference only): Executive Sponsor, Infrastructure Lead, PMO, QA Lead.

    Once all 3 are created, confirm each one's final date/time (noting any that were shifted due to conflicts) in a clean summary table.
    ```

    ![](media/16.png)

2. After submitting the prompt, you can see that Cowork has started **processing** the request.

   ![](media/17.png)

3. Review the event generated by Cowork and click on **Send** to approve it.

   ![](media/18.png)

   >**Note**: Repeat the same steps and approve the remaining 2 events generated by Cowork.

4. Review the output generated with all 10 event details listed.

   ![](media/19.png)

5. Navigate back to Outlook and select the **Calendar icon (1)** from the left. Go to **Month (2)** at the top and review all **ten events (3)** listed.

   ![](media/20.png)

   ![](media/21.png)

## Task 4: Upload Sample Files to OneDrive and Create a Team in Microsoft Teams

In this task, you will upload sample folders and files to OneDrive, then create a team and channel in Microsoft Teams for use in later labs.

1. On the Microsoft 365 Copilot portal, open the **Microsoft 365 app launcher (1)** and select **OneDrive (2)**.

   ![](media/22.png)

2. If the **Work smarter with Copilot** popup appears, click on **Not now** and continue.

   ![](media/23.png)

3. On OneDrive, navigate to **My files**.

   ![](media/24.png)

4. Click on **Create or upload (1)** and select **Folder (2)** to create a new folder.

   ![](media/25.png)

5. Name the folder ```Lab Files``` **(1)** and click on **Create (2)**.

   ![](media/26.png)

6. Verify that the **Lab Files** folder is created and click on it to navigate inside.

   ![](media/27.png)

7. In **Lab Files**, click on **Create or upload (1)** and select **Folder upload (2)**.

   ![](media/28.png)

8. Navigate to the path ```C:\LabFiles\lab file``` **(1)**, select **ArchiveCandidates (2)**, and click **Upload (3)** to complete the upload.

   ![](media/29.png)

1. If you see a popup asking for permission to upload the files then click on **Upload**.

   ![](media/29(1).png)

   >**Note**: Repeat this process and upload all the remaining folders into Lab Files except the **Project Orion Files** folder.

9. Once done uploading, verify that all four folders are visible, then click on **Create or upload (1)** and select **Files upload (2)**.

   ![](media/30.png)

10. Navigate to the path ```C:\LabFiles\lab file``` **(1)**, select **all four files (2)**, and click **Open (3)** to complete the upload.

    ![](media/31.png)

11. Verify that all the folders and files are visible, then navigate back to **My files**.

    ![](media/32.png)

12. Click on **Create or upload (1)** and select **Folder upload (2)**.

    ![](media/33.png)

13. Navigate to the path ```C:\LabFiles\lab file``` **(1)**, select **Project Orion Files (2)**, and click **Upload (3)**.

    ![](media/34.png)

1. If you see a popup asking for permission to upload the files then click on **Upload**.

   ![](media/34(1).png)

14. Verify that the **Project Orion Files** folder appears in the list.

    ![](media/35.png)

15. Go back to the Microsoft 365 Copilot portal, open the **Microsoft 365 app launcher (1)**, and select **Teams (2)**.

    ![](media/36.png)

16. In the Teams browser, click on **See all your teams (1)** and select **Create team (2)**.

    ![](media/37.png)

    ![](media/38.png)

17. Add the team name as **Retail (1)**, the first channel name as **General (2)**, and click on **Create (3)**.

    ![](media/39.png)

18. Click on **Skip** on the **Add members to Retail** page.

    ![](media/40.png)

19. Verify that the team **Retail** and channel **General** have been created on the left.

    ![](media/41.png)

## Task 5: Run Your First Tasks with Cowork

In this task you will learn the three ways to give Cowork an instruction: starter tiles, typing, and voice.

1. Back on the Microsoft 365 Copilot portal, click on **Prep for a meeting (1)**.

   ![](media/42.png)

2. Review the **prompt (1)** and click on **Send (2)**.

   ![](media/43.png)

3. After submitting the prompt, you can see that Cowork has started **processing** the request.

   ![](media/44.png)

4. Review the recommendations provided by Cowork, select the **option (1)** of your choice, and click on **Next or Submit (2)**.

   ![](media/45.png)

   ![](media/46.png)

   ![](media/47.png)

   ![](media/48.png)

   ![](media/49.png)

   ![](media/50.png)

   >**Note**: As Cowork uses AI to generate responses, the number and type of follow-up prompts may vary from the examples shown above.

5. Review the output generated by Cowork that includes the **Prep Word document**.

   ![](media/51.png)

6. Enter the following prompt **(1)** and click the **send (2)** button:

    ```
    Summarize my last 5 unread emails and list any action items I need to respond to.
    ```

   ![](media/52.png)

7. Review the output where Cowork has summarized the emails and listed the ones that need a response.

   ![](media/53.png)

## Task 6: Use the + Menu to Add Context to a Task

In this task, you will use the + menu in Cowork to attach work context and files to a task, and review how Cowork uses that context to generate a response.

1. Click on the **New task** from the left.

   ![](media/57.png)

2. Click the **"+" (1)** icon, review the options present, and select **Add work context (2)**.

   ![](media/58.png)

3. Navigate through each tab and review what it shows.

   ![](media/59.png)

4. Go to the **Files (1)** tab and select any of the **Excel file (2)**.

   ![](media/60.png)

5. In the task bar, enter ```What does this file contain?``` **(1)** and click **Send (2)**.

   ![](media/61.png)

6. Review the output generated by Cowork after reading the attached file.

   ![](media/62.png)

7. Click the **"+" (1)** icon, review the options present, and select **Upload images and files (2)**.

   ![](media/63.png)

8. Navigate to the path ```C:\LabFiles\lab file\Project Orion Files``` **(1)**, select **Information Security Policy (2)**, and click **Upload (3)**.

   ![](media/64.png)

9. In the task bar, enter ```What does this document contain?``` **(1)** and click **Send (2)**.

   ![](media/65.png)

10. Review the output generated by Cowork after reading the attached file.

    ![](media/66.png)

## Task 7: Explore Task History, Scheduled Tasks, and Task Ideas

In this task, you will search your task history, schedule a recurring task, and explore suggested task ideas.

1. Click on **My tasks (1)** from the left and type **email (2)** in the search bar. The list filters in real time to tasks containing that word.

   ![](media/67.png)

   ![](media/68.png)

2. Click the **"..." (1)** icon on any task row to review the options available to rename or delete the task.

   ![](media/69.png)

3. Select **Scheduled (1)** in the left panel and click on **Create (2)**.

   ![](media/70.png)

4. After clicking on Create, you can see that Cowork has started **processing** the request.

   ![](media/71.png)

5. Review the recommendations provided by Cowork, select the **option (1)** that best aligns with your interest, and click **Next (2)**.

   ![](media/72.png)

   ![](media/73.png)

6. Schedule the **time (1)** as per your need and click **Submit (2)**.

   ![](media/74.png)

7. Click on **Schedule** to approve the request for creating a scheduled task.

   ![](media/75.png)

8. Verify that Cowork has processed the request and generated the output.

   ![](media/76.png)

9. Click on **Scheduled (1)** and, under **Manage schedules**, verify that the **Weekday Morning Briefing (2)** task is scheduled.

   ![](media/77.png)

10. Click on **New task (1)** and select **Show more (2)** next to the "Try these next" section.

    ![](media/78.png)

11. Review all the topics presented one by one.

    ![](media/78(1).png)

12. Go to **Meetings (1)** and select **Meeting briefing (2)** to pre-fill it in the task bar.

    ![](media/79.png)

13. Read the prompt, then press Escape or clear the task bar without running it.

    ![](media/80.png)

## Task 8: Explore the Customize Area

In this task, you will explore the Customize area, where Cowork's capabilities can be extended through Plugins and Skills.

1. Click on **Customize** in the left panel.

   ![](media/81.png)

2. Click the **filter (1)** icon beside **Discover** and select **Collaboration (2)**.

   ![](media/82.png)

3. Review the plugins visible in the Discover gallery.

   ![](media/83.png)

   >**Note**: Each plugin tile shows a logo, name, and one-line description. Plugins connect Cowork to services outside Microsoft 365.

4. Click the **Skills (1)** tab at the top of the Customize page and review all the **built-in skills (2)** included with Cowork.

   ![](media/84.png)

5. Click the **Add** dropdown to create or upload a new skill.

   ![](media/85.png)

## Review
In this lab, you completed the following:

- Signed in to Microsoft 365 and explored the Copilot Cowork home screen
- Generated sample emails and calendar events in Outlook using Cowork
- Uploaded sample files to OneDrive and created a team and channel in Microsoft Teams
- Ran tasks using starter tiles, typed prompts, and voice commands
- Added context to a task using the + menu and uploaded files
- Explored task history, scheduled tasks, and suggested task ideas
- Explored the Customize area to review available plugins and skills

## You have successfully completed the Lab!

Now, click on **Next >>** from the lower right corner to move on to the next page.

![Image](./media/nxtd1.png)
