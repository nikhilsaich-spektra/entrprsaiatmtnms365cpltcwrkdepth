# Lab 6: Building Custom Cowork Skill (Read Only)

### Estimated Duration: 90 minutes

## Overview

In this hands-on lab, you will use Copilot Cowork's conversational AI Skill Builder to create two reusable custom skills. Rather than filling out forms or writing code, you will describe each skill in plain language and answer a series of follow-up questions while Cowork generates the skill automatically. You will plan a skill specification on paper, build a Leadership Update skill and test it against a sample input, build a second Project Status Brief skill with a full specification, download and review the generated skill definition file, invoke the skill using its trigger phrase, and publish its output directly to a Microsoft Teams channel with human approval at the write step. Finally, you will inspect a skill's details and review its management options, including Download, Edit Instructions, and Delete.

>**Note:** This is a read-only lab intended to introduce the key concepts and capabilities of building custom skills in Microsoft 365 Copilot Cowork. No hands-on activities are performed in this exercise, in order to manage credit consumption for the workshop. Participants will gain the foundational knowledge needed to understand how custom skills are created, tested, and used.

## Objectives

In this lab, you will perform the following:

- Task 1: Design Your Skill on Paper First
- Task 2: Build the Leadership Update Skill
- Task 3: Select the Skill Purpose
- Task 4: Test the Leadership Update Skill
- Task 5: Build the Project Status Brief Skill
- Task 6: Review the Completed Skill and Output Files
- Task 7: Run the Project Status Brief and Post to a Teams Channel
- Task 8: Post the Project Status Brief to a Teams Channel
- Task 9: Inspect, Edit, Download, and Delete Skills

## Task 1: Design Your Skill on Paper First

In this task, you will plan the Leadership Update skill on paper before building it - capturing what it should do, what it needs to read, and what its output should look like in a Skill Specification.

1. Open the **Start** menu, search for **Notepad** and select the application from the search results.

    ![](./media/m6t2s1.png)

1. In Notepad, enter the following planning questions:

    ```text
    What should this skill do?

    What does it need to read?

    Does it write or change anything?

    What should the output look like?

    Is there a variable that might change?
    ```

1. Verify all five planning questions have been added to the Notepad document.

    ![](./media/m6t2s2.png)

1. Review each question and enter your responses below the corresponding question.

1. Save the notes for reference during the remaining exercises.

   >**Note:** Use the sample answers below as a reference if you are unable to complete the notepad entries independently.

   ```
   What should this skill do?

   Generate concise leadership update messages from project, operational, or business input provided by the user. The skill should create executive-ready updates focused on key accomplishments, risks, decisions, next steps, and overall status.

   What does it need to read?

   User-provided project updates, status notes, milestones, risks, business updates, meeting summaries, or task completion details.

   Does it write or change anything?

   No. The skill only generates communication content and does not modify files, messages, or data sources.

   What should the output look like?

   A professional leadership update with:
   - Executive Summary
   - Key Accomplishments
   - Risks and Issues  
   - Next Steps
   - Overall Status

   Is there a variable that might change?

   Yes.
   - Project name
   - Reporting period
   - Audience
   - Business unit
   - Status details
   - Risks and action items

   ```
   
1. In the existing **Notepad** document, scroll below the planning questions and responses entered in the previous task.

1. Add a new section for the skill specification.

1. Enter the following Skill Specification fields:

    ```text
    Skill Name:

    Trigger Phrase:

    Parameters:

    Apps It May Read:

    Apps It May Write:

    Output Format:
    ```

1. Complete each field based on the requirements of the Leadership Update skill.

1. Verify the Skill Specification contains all required information.

    ![](./media/m6t3s1.png)

    >**Note:** Use the sample Skill Specification template provided below as a reference if you are unable to complete the notepad entries independently.

   ```
   Skill Name:

    Leadership Update

   Trigger Phrase:

    Create a leadership update

   Generate an executive status update

    Prepare a leadership summary

   Parameters:

    - Project Name
    - Reporting Period
    - Key Accomplishments
    - Risks and Issues
    - Next Steps
    - Overall Status
    - Audience

   Apps It May Read:

    - Microsoft Teams
    - Microsoft Word
    - OneNote
    - Outlook Emails
    - SharePoint Documents

   Apps It May Write:

    None

   Output Format:

    Professional leadership communication including:
    - Title
    - Executive Summary
    - Key Achievements
    - Risks and Mitigations
    - Upcoming Activities
    - Status Indicator (Green/Amber/Red)

   Output should be concise, executive-friendly, and suitable for email, Teams, or leadership review.    
   ```

1. Review the Skill Specification and confirm the following details are documented:

    - Skill Name
    - Trigger Phrase
    - Parameters
    - Apps It May Read
    - Apps It May Write
    - Output Format

1. Save the Notepad document.

1. Keep the Skill Specification available for reference during the remaining tasks.

1. Do not paste the Skill Specification into Copilot Cowork unless instructed later in the lab.

## Task 2: Build the Leadership Update Skill

In this task, you will open the Skills area in Customize and start building the Leadership Update skill using Cowork's conversational Skill Builder, which asks a series of questions and generates the skill automatically.

1. On the **Copilot Cowork** home page, click the **"+" (1)** icon located beside the prompt bar.

1. Review the available options displayed in the menu and select **Customize (2)**.

    ![](./media/m6e2s1.png)

1. Review the available tabs on the Customize page and select the **Skills (1)** tab.

1. Review the Skills page and confirm the following sections are available:

    - **Your skills (2)**
    - **Built-in Skills (3)**
    - **Add button (4)**

      ![](./media/m6e2s2.png)

1. Click the **Add (1)** button located in the upper-right corner.

1. Review the available options in the dropdown menu.

1. Select **+ Create new (2)** to start creating a new personal skill.

   ![](./media/m6e2s5.png)

1. Verify the skill creation process starts successfully.

1. Confirm a new skill creation entry appears in the left navigation pane.

    ![](./media/m6e2s6.png)

1. Verify the skill builder is ready to collect information about the new skill.

1. Review the questions presented by the skill builder before proceeding to the next task.

1. Do not enter any responses until the skill definition prompts have finished loading.


## Task 3: Select the Skill Purpose

In this task, you will answer Cowork's follow-up questions about the skill's purpose and message type, then review the Leadership Update skill it generates.

1. Review the skill creation response generated by Copilot Cowork.

1. Verify the skill builder presents the available skill purpose options.

1. Review the following options:

    - Draft a recurring document
    - Format or transform content
    - Communication template
    - Data and analysis routine

      ![](./media/m6e2s3.png)

1. Select **Communication template**.

1. Click **Submit** to confirm the selected skill purpose.

1. Wait for Copilot Cowork to proceed to the next skill configuration step.

1. Verify the skill builder accepts the selected purpose and continues the skill creation workflow.

1. Review the message type options presented by Copilot Cowork.

1. Verify the available message types include:

    - Leadership / executive update
    - Team announcement
    - Customer / client reply
    - Project status email

1. Review the description for **Leadership / executive update**.

1. Select **Leadership / executive update**.

     ![](./media/m6e2s4(1).png)

    >**Note:** If the option is not available paste the below **prompt (1)** in the customize section and click **Submit (2)**.

    ```
    Leadership / exec update
    Concise status and asks for senior leaders — progress, risks, decisions needed. Skimmable, outcome-first.
    ```

    ![](./media/m6e2s4.png)

1. After submitting the message type selection, monitor the **Workspace** pane while Copilot Cowork begins creating the skill.

1. Verify the Workspace pane displays **3/3** completed steps.

    ![](./media/m6e2s11.png)

1. Review the output generated by Copilot Cowork.

1. Verify the following files are available in the **Output** section:

    - `team-status-update-SKILL.md`
    - `skill-quality-report.html`

      ![](./media/m6e2s12.png)

1. Review the completion summary generated by Copilot Cowork.

1. In the **Output** section, locate **skill-quality-report.html**.

1. Close the Workspace pane by selecting the **Close (X)** button.

    ![](./media/m6e2s13.png)

1. Verify the skill has been created successfully before proceeding to the next exercise.

## Task 4: Test the Leadership Update Skill

In this task, you will test the Leadership Update skill with a sample input and confirm it activates correctly and is registered under Your Skills.

1. In the left navigation pane, select **New task**.

1. Verify the Copilot Cowork home page opens successfully.

    ![](./media/m6e2t4s1.png)

1. Review the available sections on the home page.

1. Verify the following components are visible:

    - Cowork prompt box
    - Recent tasks
    - Suggested tasks
    - Copilot Cowork home page content

1. Select the task input box to begin a new task.

1. In the Copilot Cowork prompt box, enter the skill validation prompt 

    ```
    Use team-status-update

    Summarize the following information into an executive-ready leadership update:

    Over the past week, several key initiatives have made progress. Most planned activities are on schedule, although a few tasks are taking longer than expected due to resource constraints. Team collaboration has improved, and stakeholder engagement remains positive. Some risks have been identified that may impact upcoming deadlines if not addressed. Additional support may be needed to maintain momentum.
    ```

1. Review the prompt before submitting it.

    ![](./media/m6e2t4s2.png)

1. Click **Send** or press **Enter** to submit the prompt.

1. Wait for Copilot Cowork to process the request and invoke the newly created skill.

1. Wait for Copilot Cowork to process the request and generate the leadership update.

1. Review the generated output.

1. Verify the response is organized into the following sections:

    - Headline
    - Progress
    - Risks and Blockers
    - Asks / Next Steps

        ![](./media/m6e2t4s3.png)

1. Review the content generated within each section.

1. Verify the custom skill is listed under **Skills & Plugins**, confirming that the skill was successfully invoked.

1. Confirm the output follows the expected leadership update format before proceeding to the next task.

1. In the left navigation pane, select **Customize**.

1. Verify the newly created skill is listed in the Skills library.

    ![](./media/m6e2t4s4.png)

1. Confirm the skill displays under **Your Skills** and is available for future use.

## Task 5: Build the Project Status Brief Skill

In this task, you will build a second skill, the Project Status Brief, using the same conversational Skill Builder pattern as Task 2 - this time from a full written specification.

1. In the left navigation pane, select **Customize**.

1. Select the **Skills** tab.

1. Select **Add** in the upper-right corner of the Skills page.

1. Review the available options in the dropdown menu.

    ![](./media/m6e2t5s1.png)

1. Verify the following options are available:

    - **Create new**
    - **Upload skill**

1. Confirm the existing custom skill is listed under **Your Skills**.

1. Select **+ Create new** to begin creating the next skill.

1. Verify the skill creation workflow starts successfully before proceeding to the next task.

1. Review the Workspace pane and confirm **Skill Management** is available under **Skills & Plugins**.

    ![](./media/m6e2t5s2.png)

1. Wait for the skill purpose options to appear.

1. Review the available skill purpose options presented by Copilot Cowork.

1. In the **Describe another option** field, enter the **Project Status Brief skill specification (1)** and click **Submit (2)** to continue.

    ```
    Name: Project Status Brief

    Description:
    Generates a concise project status brief for leadership and stakeholders. The skill summarizes project progress, completed work, current risks, blockers, upcoming milestones, and next steps in a professional format suitable for executive review.

    Purpose:
    Create consistent project update summaries from user-provided project information.

    Output Format:
    - Project Overview
    - Key Accomplishments
    - Current Status
    - Risks and Blockers
    - Upcoming Milestones
    - Next Steps

    Input:
    Project updates, meeting notes, milestone status, risks, issues, and action items.

    Tone:
    Professional and concise.

    Apps It May Read:
    Teams, Outlook, Word, OneNote, SharePoint

    Apps It May Write:
    None

    Trigger Phrase:
    Create a project status brief
    Generate a project update
    Summarize project progress
    ```

    ![](./media/m6e2t5s3.png)

1. Verify the skill specification is accepted successfully.

1. Review the first build step displayed in the Workspace pane.

    ![](./media/m6e2t5s4.png)

1. Verify the skill creation process continues successfully.

    ![](./media/m6e2t5s5.png)

1. Wait for the skill generation step to complete.

1. Wait for all build activities to complete.

1. Verify the Workspace pane displays **3/3** completed steps.

    ![](./media/m6e2t5s6.png)

1. Review the generated output files.

1. In the **Output** section select **skill-quality-report.html**.

1. Review the generated quality report.

    ![](./media/m6e2t5s7.png)

1. Verify the following files are available in the **Output** section:

    - `project-status-brief_SKILL.md`
    - `skill-quality-report.html`

1. Confirm the skill creation process completed successfully before proceeding to the next task.

## Task 6: Review the Completed Skill and Output Files

In this task, you will review the completed skill and its generated output files, verify the skill definition includes all required elements (name, description, trigger phrases, usage instructions, guardrails, and data sources), and download the skill definition file for later use.

1. Review the final completion summary generated by Copilot Cowork.

1. Review the generated skill details and trigger phrases.

     ![](./media/m6e2t6s1.png)

1. Verify the summary includes:

    - Skill name
    - Trigger phrases
    - Quality score
    - Skill category
    - Output files

1. Review the trigger phrases provided for using the skill.

1. Record the trigger phrases for future testing and validation activities.

1. In the **Output** section, select **project-status-brief-SKILL.md**.

1. Review the generated skill definition file.

    ![](./media/m6e2t6s2.png)

    ![](./media/m6e2t6s3.png)

1. Verify the skill definition includes:

    - Skill name
    - Description
    - Trigger phrases
    - Usage instructions
    - Guardrails
    - Data sources

1. Review the configured trigger phrases and usage guidance.

1. Close the skill definition file after reviewing the contents.

1. Verify the skill creation exercise is complete before proceeding to the next exercise.

1. In the **project-status-brief-SKILL.md** preview window, click the **ellipsis (...)** menu in the upper-right corner.

1. From the menu, select **Download**.

    ![](./media/m6e2t6s4.png)

1. Verify the file is downloaded successfully to the local device.

1. Open the Downloads folder and confirm the **project-status-brief-SKILL.md** file is available.

1. Retain the downloaded file for later use in the skill upload exercise.

## Task 7: Run the Project Status Brief and Post to a Teams Channel

In this task, you will upload the downloaded skill file, invoke the Project Status Brief skill using its trigger phrase and review the generated briefing.

1. Navigate to **Customize** > **Skills**.

1. Review the **Your Skills** section.

    ![](./media/m6e2t7s1.png)

1. In the **Open** file dialog, navigate to **This PC** > **Downloads**.

1. Select the **project-status-brief-SKILL.md (1)** file from the Downloads folder and click **Open (2)** to upload the selected skill file.

    ![](./media/m6e2t7s2.png)

1. Confirm the imported skill is available for use and is listed alongside existing custom skills.

    ![](./media/m6e2t7s3.png)

1. In the left navigation pane, select **New task (1)**.

1. In the task input box, enter the following **trigger phrase (2)** and click **Send (3)** to submit the request.

    ```text
    give me the project status brief
    ```

    ![](./media/m6e2t7s4.png)

1. Review the left navigation pane and verify a new Project Status Brief task is created.

     ![](./media/m6e2t7s5.png)

1. Verify the submitted prompt appears in the conversation window.

1. Wait for Copilot Cowork to process the request and invoke the Project Status Brief skill.

1. Review the **Workspace** pane and verify the skill is activated successfully.

    ![](./media/m6e2t7s6.png)

1. Review the **Workspace** pane and confirm **project-status-brief** is displayed under **Skills & Plugins**.

    ![](./media/m6e2t7s7.png)

1. Verify the custom skill was successfully invoked to generate the briefing.

1. Scroll down to review the remaining sections of the report.

    ![](./media/m6e2t7s8.png)


## Task 8: Post the Project Status Brief to a Teams Channel

In this task, you will direct Cowork to post the generated Project Status Brief to a Microsoft Teams channel and confirm it was delivered.

1. In the task input box, enter the following instruction:

    ```text
    send the updates to Retail > General
    ```

1. Click **Send** or press **Enter** to submit the request.

1. Review the Teams activities and confirm Copilot Cowork identifies the Project Orion team.

1. When the **Post to channel** dialog appears, review the details and click on **Send**.

    ![](./media/m6e2t8s3(1).png)

1. Review how Cowork has started processing the request.

   ![](./media/m6e2t8s4(2).png)

1. Review the final confirmation message.

    ![](./media/m6e2t8s4(1).png)

1. Verify the confirmation indicates the Project Status Brief was posted to the target Teams channel.

1. Open Microsoft Teams.

1. Navigate to the target team and channel.

1. Verify the Project Status Brief message is available in the channel conversation.

    ![](./media/m6e2t8s5(1).png)

1. Confirm the posting activity completed successfully before proceeding to the next task.

1. Confirm the message appears in the channel conversation successfully.

1. Verify the end-to-end workflow completed successfully:

    - Project Status Brief generated
    - Teams post created
    - Message delivered to the selected channel

## Task 9: Inspect, Edit, Download, and Delete Skills

In this task, you will inspect a skill's full details and review its management options, including Download, Edit Instructions, and Delete.

1. In the left navigation pane, select **Customize**.

1. Select the **Skills** tab.

1. Review the **Your Skills** section.

1. Verify the **project-status-brief-1** skill is available in the Skills library.

1. Select the **project-status-brief-1** skill to open the skill details page.

    ![](./media/m6e2t9s1(1).png)

    ![](./media/m6e2t9s1.png)

1. Verify the skill details page loads successfully before proceeding to the next task.

1. In the **Your Skills** section, select **project-status-brief-1**.

1. Review the skill details page.

      ![](./media/m6e2t9s2.png)

1. Locate the actions available in the upper-right corner of the skill details page.

    ![](./media/m6e2t9s3.png)

1. Verify the following actions are available:

    - Download
    - Delete

1. Review the available skill management options.

1. Confirm the skill can be downloaded, edited, or removed if required.

    > **Note:** The **Delete** option permanently removes the skill. Use **Download** to save a copy of the SKILL.md file and use **Edit Instructions** to modify the skill behavior.

1. Verify the Project Status Brief skill configuration and management options before proceeding to the next task.

## Review

In this lab, you completed the following:


- Learned what a Custom Skill is and planned a skill specification on paper - capturing purpose, inputs, outputs, and trigger phrases - before using the builder
- Built the Leadership Update skill (team-status-update) using Copilot Cowork's fully conversational Skill Builder, selecting a skill purpose and a message type rather than filling out a manual form
- Tested the Leadership Update skill with a sample input and confirmed it generated a structured update with Headline, Progress, Risks and Blockers, and Asks/Next Steps sections
- Verified the custom skill was registered under Your Skills in the Skills library alongside the built-in PDF, Word, and Excel skills
- Built a second custom skill, the Project Status Brief, from a full written specification covering description, output format, tone, and permitted apps
- Reviewed the generated SKILL.md definition file and skill-quality-report.html, then downloaded the skill definition file for reuse
- Re-uploaded the downloaded skill definition and invoked the Project Status Brief skill using its trigger phrase
- Directed Copilot Cowork to post the generated Project Status Brief to a Microsoft Teams channel, reviewing and approving the post before it was sent
- Inspected a skill's details - Overview, When to Use, and When Not to Use - and reviewed its management options: Download, Edit Instructions, and Delete


## You have successfully completed the Lab!

Now, click on **Next >>** from the lower right corner to move on to the next page.

 ![](./media/nxtim.png)