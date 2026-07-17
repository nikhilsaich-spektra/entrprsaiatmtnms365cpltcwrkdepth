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

In this task, you will use Cowork to generate and send 20 sample training emails to your own Outlook inbox for use in later labs.

1. In the Cowork pane, enter the below prompt **(1)** and click the **send (2)** button:

     ```
     I need you to seed my Outlook inbox with 20 sample training emails for a Copilot Cowork demo environment (Contoso Electronics / Project Orion ERP modernization scenario). Send each one individually to my own email address so it lands as a received message in my Inbox. You have my approval to send all 20 without pausing for individual confirmation — just send them one after another and give me a final summary list when done.

     For every email: write a proper business email (greeting, 2–4 short paragraphs or bullet points as noted, professional sign-off with the sender name and title/company given below). Prefix each Subject line with the source tag shown in brackets. Do not literally attach files — if an email references an attachment, just mention it in the body text as an attachment would be described in real reply threads.

     Send these 20, in this order:

     ## Customer & Sales

     1. **[Northwind Retail]** Subject: *"Final Contract Review – Payment Milestone Clarification."* From: Priya Desai, Procurement Lead, Northwind Retail. She's reviewing the ERP contract and needs clarification on the payment milestone schedule before she can sign. Polite, slightly urgent — she wants this resolved this week.

     2. **[Fabrikam Industries]** Subject: *"Feature Request – Barcode Scanning & Warehouse Integration."* From: Marcus Webb, IT Director, Fabrikam Industries. Requests that barcode scanning and warehouse-management integration be added to the ERP build, explains it's needed for their distribution centers.

     3. **[Adventure Works]** Subject: *"Go-Live Schedule Confirmed – Training Schedule Needed."* From: Elena Torres, Operations Manager, Adventure Works. Confirms she's fine with the proposed go-live date, but asks when end-user training sessions will be scheduled.

     4. **[Tailspin Toys]** Subject: *"URGENT: Production Issue Affecting Order Processing."* From: David Chen, IT Support Lead, Tailspin Toys. Urgent tone — a production issue is blocking order processing right now, needs immediate attention, asks for a callback ASAP.

     5. **[Fourth Coffee]** Subject: *"Invitation – Quarterly Business Review."* From: the Fourth Coffee Account Team. Invites the recipient to a QBR next week, mentions an agenda and a presentation deck are attached, asks to confirm attendance.

     ## Internal Project

     6. **[Project Orion – PMO]** Subject: *"Weekly Status Update – Project Orion."* From: Rajesh Kumar, Project Manager. Structured with four short sections: Completed This Week, Delays, Upcoming Milestones, Risks. Include 2–3 concrete action items with owners.

     7. **[Architecture Team]** Subject: *"Architecture Review Outcomes."* From: Sandra Liu, Technical Architect. Documents 3 design decisions made in a recent architecture review (e.g., integration pattern, data model choice, API approach) and the reasoning for each.

     8. **[QA Team]** Subject: *"Testing Completion Report – Sprint Review."* From: Amit Verma, QA Lead. Reports number of tests passed/failed, lists 2–3 open bugs with severity, and gives a clear release recommendation (go / no-go / go-with-conditions).

     9. **[Security Team]** Subject: *"Security Assessment Findings – Action Required."* From the Infosec team. Reports a number of high-risk vulnerabilities and medium findings found during assessment, and lists required remediation steps with an owner and deadline.

     10. **[Infrastructure Team]** Subject: *"Deployment Readiness Checklist – Status Confirmed."* From the Infrastructure team. Confirms status (ready/pending) across servers, backup, disaster recovery, and monitoring ahead of go-live.

     ## Executive Communications

     11. **[Office of the CIO]** Subject: *"CIO Monthly Update – AI Adoption & Priorities."* Company-wide tone, covers progress on AI adoption initiatives and strategic priorities for the quarter.

     12. **[Office of the CEO]** Subject: *"Town Hall Announcement – Organizational Updates."* Announces an upcoming town hall, references organizational changes and quarterly goals to be discussed, invites all staff to attend.

     13. **[Finance Department]** Subject: *"Budget Approved – Project Orion Additional Funding."* From the Finance Director. Confirms additional budget has been approved for Project Orion, states it requires an acknowledgement reply from the recipient.

     14. **[HR / Learning & Development]** Subject: *"Action Required – Register for Copilot Training."* Announces mandatory Copilot training sessions, gives a registration deadline, states attendance is mandatory for all employees.

     ## Vendor Communications

     15. **[Licensing Account Team]** Subject: *"Reminder – Microsoft 365 License Renewal."* Renewal reminder for Microsoft 365 licenses, references a pricing summary, gives a renewal deadline.

     16. **[Dell Hardware Logistics]** Subject: *"Shipment Delay Notice – Hardware Order."* Notifies that a hardware shipment is delayed by one week, gives a revised delivery date, notes the impact on the deployment timeline.

     17. **[Network Services Provider]** Subject: *"Scheduled Maintenance Notice – This Weekend."* Notifies of a weekend maintenance window with a potential service interruption, no action needed from the recipient.

     ## Meeting-Related

     18. **[PMO]** Subject: *"Invitation – Steering Committee Meeting."* Includes a short agenda (3–4 bullet points), a list of expected attendees (roles, not real people), a placeholder Teams link, and a note that a deck is attached.

     19. **[PMO – Risk Management]** Subject: *"Risk Review Meeting – Follow-Up Notes."* Summarizes 3 decisions made in a recent risk review, each with an owner name and a due date.

     20. **[Executive Sponsor]** Subject: *"Go-Live Readiness Review – Executive Meeting Invite."* Summarizes overall project health, references the deployment readiness checklist, and lists 2–3 approval items needed from executives before go-live.

     Once all 20 are sent, give me a confirmation list showing each subject line and the time it was sent.
     ```

     ![](media/8(1).png)

2. After submitting the prompt, you can see that Cowork has started **processing** the request.

   ![](media/9.png)

3. Review the email generated by Cowork and click on **Send** to approve it.

   ![](media/10.png)

4. Review the second email generated by Cowork and click on **Send** to approve it.

   ![](media/11.png)

   >**Note**: Repeat the same steps and approve all the remaining 18 emails generated by Cowork.

5. Review the output generated with all 20 email details listed.

   ![](media/12.png)

6. To verify the emails were generated, click on the **Microsoft 365 app launcher (1)** and select **Outlook (2)**.

   ![](media/13.png)

7. If the **Your privacy matters** popup appears, click on **Continue**.

   ![](media/14.png)

8. Go to **Inbox (1)** and confirm that all the **sample emails (2)** are present.

    ![](media/15.png)

## Task 3: Generate Sample Calendar Events in Outlook

In this task, you will use Cowork to create 10 sample calendar events in Outlook to build out a realistic project calendar.

1. Go back to Microsoft 365 Copilot portal and in the Cowork pane, enter the below prompt **(1)** and click the **send (2)** button:

    ```
    I need you to create 10 sample calendar events on my Outlook calendar for a Copilot Cowork demo environment (Contoso Electronics / Project Orion ERP modernization scenario). Create all 10 without pausing for individual confirmation, then give me a summary table at the end (event title, date, time) once done.

    ## Rules for every event

    - I am the only attendee/organizer — do NOT invite or add any other person's email address to any of these events, even if a name or company is mentioned. Any attendee names or companies mentioned below should appear as plain text inside the event description only.
    - Add a Microsoft Teams meeting link to each event (standard "Teams meeting" toggle).
    - Schedule them on 10 consecutive business days starting tomorrow (skip weekends), one event per business day, in the exact order listed below, at the specific time given.
    - If any of these times conflict with something already on my calendar, shift only that one event by 30 minutes and note it in your summary — don't skip it.
    - Two of these events should have NO description/agenda at all (marked below) — leave them as bare title + time. Every other event should get the short agenda text given.

    ## The 10 events

    **Business day 1 — 9:30–9:45 AM**
    Title: Weekly Project Stand-up
    Description: (leave blank — no agenda)

    **Business day 2 — 2:00–3:00 PM**
    Title: Steering Committee Review
    Description: Agenda: review of Project Orion milestones, budget status, and go/no-go checkpoints. Attendees (for reference only, do not invite): Steering Committee members, Project Sponsor, PMO.

    **Business day 3 — 11:00 AM–12:00 PM**
    Title: Architecture Review
    Description: Agenda: review of integration pattern, data model, and API design decisions from the recent architecture review. Attendees (reference only): Technical Architect, Lead Developers, Solution Architect.

    **Business day 4 — 10:00–11:00 AM**
    Title: Security Assessment Meeting
    Description: Agenda: review of vulnerability assessment findings (high-risk and medium findings) and required remediation plan. Attendees (reference only): Security Team, Compliance Officer, IT Director.

    **Business day 5 — 3:00–3:45 PM**
    Title: Customer Demo – Northwind
    Description: Agenda: live demo of ERP sales and procurement modules for Northwind Retail stakeholders. Attendees (reference only): Northwind Retail Procurement Team, Sales Engineer, Account Manager.

    **Business day 6 — 1:00–2:00 PM**
    Title: Executive Budget Review
    Description: Agenda: review of Project Orion budget utilization and approval of additional funding request. Attendees (reference only): CFO, Finance Director, Project Sponsor.

    **Business day 7 — 4:00–4:30 PM**
    Title: Vendor Status Call
    Description: (leave blank — no agenda)

    **Business day 8 — 10:00–11:30 AM**
    Title: Go-Live Readiness Review
    Description: Agenda: walkthrough of the deployment readiness checklist (servers, backup, disaster recovery, monitoring), outstanding approval items, and the go-live decision. Attendees (reference only): Executive Sponsor, Infrastructure Lead, PMO, QA Lead.

    **Business day 9 — 2:00–3:00 PM**
    Title: Quarterly Business Review
    Description: Agenda: review of quarterly sales performance, regional analysis, and recommendations for next quarter. Attendees (reference only): Sales Leadership, Regional Managers, Executive Sponsor.

    **Business day 10 — 1:00–3:00 PM**
    Title: AI Adoption Workshop
    Description: Agenda: hands-on workshop covering the company's AI adoption strategy and Copilot training rollout. Attendees (reference only): All Staff, HR L&D Team, CIO Office.

    Once all 10 are created, confirm each one's final date/time (noting any that were shifted due to conflicts) in a clean summary table.
    ```

    ![](media/16.png)

2. After submitting the prompt, you can see that Cowork has started **processing** the request.

   ![](media/17.png)

3. Review the event generated by Cowork and click on **Send** to approve it.

   ![](media/18.png)

   >**Note**: Repeat the same steps and approve the remaining 9 events generated by Cowork.

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

8. Click the **microphone icon** on the right side of the task bar.

   ![](media/54.png)

9. Speak a simple instruction: ```Show me my meetings for tomorrow``` **(1)** and click **Send (2)**.

   ![](media/55.png)

10. Review the output generated and continue.

    ![](media/56.png)

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
