# Lab 4 – Executive Meeting Coordinator

## Estimated Duration: 45 minutes

## Overview

In this hands-on lab, you will use Copilot Cowork to automate the full lifecycle of an executive meeting — from preparation through to post-meeting follow-up — grounded entirely in real Microsoft 365 data. You will generate a one-page meeting prep brief as a Word document by having Cowork pull attendee history, agenda details, related emails and files, and open action items in parallel from Outlook, OneDrive/SharePoint, and Teams. You will refine that document with a human-approved Risks section, move the updated file into a governed OneDrive folder using a Microsoft Graph approval gate, and verify version control along the way. You will then assemble a cross-app "Meeting Pack" with a hyperlinked index document, and finally test Cowork's responsible AI grounding behavior by asking it to generate post-meeting deliverables from a transcript that does not exist — confirming that it refuses to fabricate content and instead offers constructive alternatives.


## Objectives

In this lab, you will perform the following:


- Task 1: AI-Generated Meeting Preparation
- Task 2: Collect Documents, Emails, and Action Items
- Task 3: Post-Meeting Follow-Up Automation

## Task 1: AI-Generated Meeting Preparation

In this task you will build a cross-app meeting prep brief as a Word document saved to
OneDrive Lab Files. Data gathered from Calendar, Email,
OneDrive/SharePoint, and Teams in parallel.

1.  Go to the Cowork tab (not Chat).

    ![](media/m4e1s1.png)

2.  In the prompt bar, type the prompt and press Enter:

    ```
    "Prepare me for my Steering Committee Review meeting. Build a one-page prep brief containing: attendee list with my last interaction with each, the stated agenda and purpose, related email threads and files, open action items from the Risk Review Meeting Follow-up, and 3 questions I should ask. Save it as a Word document in my 'Project Orion Files' folder named 'Prep – Steering Committee Review – [meeting date]'."
    ```
    
    ![](media/m4e1s2.png)

1. Workspace opens — Step 1 of 2 complete, calendar
accessed.

    ![](media/m4e1s3.png)

1. Workspace expands to 5 steps — parallel lookups begin.

    ![](media/m4e1s4.png)

1. Data gathering complete — transitioning to document
build

    ![](media/m4e1s5.png)

1. Folder created — Word plugin activates

    ![](media/m4e1s6.png)

1. “Approved 1 action” confirms the Lab Files folder was
created. The Word plugin activates immediately in the Skills & Plugins
panel — required to generate the .docx file.

1. Word document build starts — agent narrates its plan.

    ![](media/m4e1s7.png)

1. Four parallel sub-tasks enumerated — Output panel
shows document

    ![](media/m4e1s8.png)

1. First parallel batch complete — deeper email search
begins

    ![](media/m4e1s9.png)

1. Deepest data layer — email bodies, Teams chats, and
transcripts.

    ![](media/m4e1s10.png)

1. Upload failed — document accessible via link card

    ![](media/m4e1s11.png)

6.  Click the document link card to open the prep brief in Word Online
    and verify all sections.

    ![](media/m4e1s12.png)

7. Side-by-side — Cowork shows 3 questions

    ![](media/m4e1s13.png)

    The three strategic questions are grounded in the
    meeting’s stated purpose.

7.  Send the refinement prompt:

    **Refinement prompt** 
    ```
    "Add a Risks section to this prep brief listing anything in my recent emails or files that could affect the Steering Committee decision - including the Tailspin Toys critical support escalation and the Fabrikam Industries feature enhancement request, if they are still open."
    ```

    ![](media/m4e1s14.png)

1. Refinement submitted — Cowork re-analyses email
threads

    ![](media/m4e1s15.png)

1. Word Online — view document in context before Risks
section added.

    ![](media/m4e1s16.png)

8. Send the prompt: 
    ```
    Move updated word file to lab files folder
    ```

    ![](media/m4e1s17.png)

1. "Move updated word file" sent — Cowork searching
    OneDrive

    ![](media/m4e1s18.png)

1. Send the prompt:
     ```
     Move the updated version with the Risks section to the Lab Files folder.
     ```

    ![](media/m4e1s19.png)

9.  A “Use Microsoft Graph?” card for the file move has appeared. Click
    “Approve”.

    ![](media/m4e1s20.png)

1. Copy succeeds — file verified in Lab Files folder

    ![](media/m4e1s21.png)

1. Final confirmation — housekeeping note about two
    copies

    ![](media/m4e1s22.png)

1. Document thumbnail hover card — v2 file confirmed in
    Output panel

    ![](media/m4e1s23.png)

10. Open OneDrive → My files. Verify the Lab Files folder exists with 1
    item.

     ![](media/m4e1s24.png)

1. Send Prompt : 
    ```
    Can you confirm which document is the correct final version?
    ```

    ![](media/m4e1s25.png)

1. Word Online — RISKS / BLOCKERS section visible in
    final document

    ![](media/m4e1s26.png)

## Task 2: Collect Documents, Emails, and Action Items

In this task you will gather all content related to the Project Sync meeting and
organise it into a “Meeting Pack” folder in OneDrive with a hyperlinked
index document.

1. Send the prompt: 
    ```
    "For the Steering Committee Review meeting for Project Orion, gather
        everything related: files in OneDrive/SharePoint, email threads,
        Teams messages, and any open tasks. Organise them into a single
        'Meeting Pack' folder in OneDrive and give me an index document
        linking to each item with a one-line description."
     ```

    ![](media/m4e2s1.png)

1. New workspace with 4 steps — parallel search
    launched

    ![](media/m4e2s2.png)

1. Project Sync identified — false positives detected,
deeper search initiated**

    ![](media/m4e2s3.png)

14. A “Create folder?” card has appeared. Click “Create” to approve the
        Meeting Pack folder.

    ![](media/m4e2s4.png)

1. Meeting Pack folder created — prep brief being copied
in

    ![](media/m4e2s5.png)

1. Index document creation starts

    ![](media/m4e2s6.png)

1. All 4 steps complete — 5-item index confirmed with
    caveats

    ![](media/m4e2s7.png)

15. Click the Meeting Pack index document link to open it in Word
    Online. Verify the first 3 rows and test the hyperlinks.

    ![](media/m4e2s8.png)

1. Word Online — Complete index with all 5 items

    ![](media/m4e2s9.png)

## Task 3: Post-Meeting Follow-Up Automation

In this task you will generate a meeting summary, action items, follow-up email, and
tasks from a transcript. Demonstrates AI grounding — refusing to
fabricate content without source material.

1. Send the prompt: 
    ```
    "From the Steering Committee Review
    meeting's transcript/notes: (1) write a crisp summary with decisions
    made, (2) extract action items with owner and due date, (3) draft a
    follow-up email to all attendees, and (4) create tasks for the items
    assigned to me. Show me everything for review before creating or
    sending anything."
    ```

    ![](media/m4e3s1.png)

    ![](media/m4e3s2.png)

1. Complete refusal with three constructive forward
paths

    ![](media/m4e3s3.png)

    After an exhaustive search, Cowork confirms no source
    material exists: “I can’t produce them without fabricating what was
    said, which I won’t do.” Three constructive alternatives are offered:
    paste notes into chat, run after the meeting with transcription on, or
    point to a different meeting with an existing transcript.

1. Correction pre-registered — honest state disclosure

    In the **Describe another option** box, enter the following prompt and click **Submit**:

    ```
    Correction: the website task belongs to Priya, not me.
    ```

    ![](media/m4e3s4.png)

    ![](media/m4e3s5.png)

## Review

In this lab, you completed the following:

- Built an AI-generated meeting prep brief as a Word document, combining calendar, email, file, and Teams data gathered in parallel by Cowork
- Refined the prep brief with a human-approved Risks section grounded in real email threads, without creating a duplicate document
- Moved the updated file into a governed OneDrive Lab Files folder using a Microsoft Graph approval gate, and verified version control between the original and updated copies
- Assembled a cross-app "Meeting Pack" folder containing files, emails, Teams messages, and open tasks related to a meeting
- Generated a hyperlinked index document linking to 5 collected items with source labels and one-line descriptions
- Tested Cowork's responsible AI grounding behavior and confirmed it refuses to fabricate meeting summaries, action items, or follow-up emails without a real transcript or notes
- Verified that Cowork correctly pre-registers a correction for future use instead of creating phantom corrected outputs


## You have successfully completed the Lab!

Now, click on **Next >>** from the lower right corner to move on to the next page.

![](media/nxtim.png)
