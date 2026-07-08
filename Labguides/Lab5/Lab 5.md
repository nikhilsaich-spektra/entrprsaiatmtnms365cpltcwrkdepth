# Lab 5 – Intelligent File Organizer

| Item | Details |
|------|---------|
| **Duration** | ~65–75 minutes (including setup) |
| **Difficulty** | Intermediate |
| **Apps** | Copilot Cowork, OneDrive, SharePoint, Excel, Microsoft Teams |

By the end of this lab, you will be able to:

- Classify and rename enterprise files using AI-generated naming
  conventions

- Apply the YYYY-MM-DD_Topic_DocType rename convention across an entire
  OneDrive folder

- Execute a full governance audit covering duplicates, staleness,
  sharing risks, and ownership gaps

- Use human-in-the-loop approval gates before every bulk file operation

- Generate an Excel governance tracker and post a Teams summary from a
  single instruction

- Reorganise healthcare documents into clinical category subfolders with
  a department-aware naming scheme

- Apply responsible AI principles — understanding which governance
  actions require human approval

You are a Power User or IT Administrator at Contoso Operations,
overseeing a shared OneDrive environment containing 28 mixed files
across retail, healthcare, finance, and project folders. File naming is
inconsistent, governance is weak, and a compliance review is
approaching.

You will use Microsoft 365 Copilot Cowork — an agentic AI layer that
orchestrates OneDrive, SharePoint, Excel, and Teams — to classify,
rename, audit, report on, and reorganise these files. Every bulk action
requires your explicit approval before it executes.

# Lab Prerequisites

Complete the following setup steps before starting the lab (estimated:
15–20 minutes):

## Required Microsoft 365 Environment

- Microsoft 365 Copilot with Copilot Cowork enabled

- Microsoft Teams with permission to post to channels

- OneDrive for Business and SharePoint Online

- Microsoft Excel (Web or Desktop)

- Microsoft Graph-connected M365 tenant

## Required OneDrive Folder Structure

Create a Lab Files folder in OneDrive with these four subfolders:

- Lab Files / Healthcare — upload provided clinical document samples

- Lab Files / Retail — upload provided retail document samples

- Lab Files / Shared Files — configure 'Anyone with the link' sharing on
  at least 3 files

- Lab Files / Archive Candidates — optional pre-populated stale
  documents

## Required Teams Environment

- Team: Contoso Operations (or equivalent)

- Channel: General (Standard) — target for Exercise 3 Teams post

# Exercise 1 – Automated File Classification and Renaming

Duration: 8 minutes | Difficulty: Beginner–Intermediate

Use AI to classify all files in your OneDrive Lab Files folder, propose
a YYYY-MM-DD_Topic_DocType renaming scheme, preview the full mapping,
then approve and execute the batch rename into topic-organised
subfolders.

## Task 1: Open Copilot Cowork and Submit Classification Prompt

Enter the following classification prompt:

*Analyze the files in my OneDrive "Lab Files" folder. Classify each by
type and topic, then propose a renaming scheme of the form
YYYY-MM-DD\_\<Topic\>\_\<DocType\> based on each file's content and
metadata. Show me the full old-name → new-name mapping before renaming
anything.*

### Step 1 — Open Copilot Cowork and enter the prompt

1.  Open your browser and navigate to m365.cloud.microsoft. Sign in with
    your lab account.

2.  Click the Microsoft 365 Copilot app from the launcher. Click the
    'Cowork' tab at the top of the left sidebar — NOT the 'Chat' tab.

- You see 'What can I do for you?' in the centre. Click inside the large
  prompt bar.

- Type the full classification prompt shown above, then click the blue ↑
  send arrow on the right side of the box.

- The 'Needs your input' and 'Try these next' cards at the bottom are
  from previous sessions — do not click them.

![](./media/image1.png)

*Screenshot 1 — Classification prompt typed and ready to send in Copilot
Cowork*

### Step 2 — Cowork discovers the Lab Files folder and begins content analysis

No action needed — Cowork begins executing immediately. Watch the
Workspace panel on the right side of the screen open.

3.  Workspace shows Step 1 'Finding your Lab Files folder' with a
    spinning circle (in progress).

4.  In the main chat, read: 'I'll start by locating your Lab Files
    folder in OneDrive.' A 'Thought process \>' link appears — click it
    to expand Cowork's reasoning.

5.  Watch the Workspace counter advance from '0/3' to '1/3' once the
    folder is found.

6.  Cowork then lists all subfolders simultaneously — you will see
    'Executing tasks...' with multiple folder scans running in parallel.

![](./media/image2.png)

*Screenshot 2 — OneDrive discovery begins: Workspace shows Steps and
Calendar Management skill activating*

![](./media/image3.png)

*Screenshot 3 — Lab Files found: parallel subfolder listing begins
(Retail and Healthcare simultaneously)*

![](./media/image4.png)

*Screenshot 4 — Step 2 active: content extraction from all 28 files
starts*

![](./media/image5.png)

*Screenshot 5 — Adaptive extraction: empty spreadsheets detected, PDF
fallback strategy applied*

## Task 2: Review the Rename Mapping and Approve

After content analysis, Cowork produces the full old-name → new-name
mapping table and stops — it will not rename anything until you approve.

7.  Cowork has completed all 3 steps. Workspace shows '3/3' with all
    steps ✓. READ the output: 'Lab Files — Analysis & Proposed Renaming'
    with one row per file.

- READ the date basis legend at the top: \[c\] = date in file content;
  \[p\] = period from filename (e.g. Q1→Jan 1); \[m\] = modified date;
  \[s\] = inferred season.

- IMPORTANT: the message input box has returned to 'Message Cowork' —
  Cowork has STOPPED. NO changes have been made in OneDrive yet. This is
  the Human-in-the-Loop preview gate.

8.  Scroll through all sections (Shared Files, Archive, Retail,
    Healthcare). Note any name you want to adjust.

9.  In the message box, type: 'proceed with suggesting renaming and
    create new folder for all latest renamed files' then press ↑.

![](./media/image6.png)

*Screenshot 6 — All 3 steps complete: rename mapping table displayed,
HITL approval gate open*

![](./media/image7.png)

*Screenshot 7 — Rename table: Shared Files and Archive Candidates
sections*

![](./media/image8.png)

*Screenshot 8 — Rename table: Retail section showing season inference
\[s\] and duplicate flagging*

![](./media/image9.png)

*Screenshot 9 — Healthcare section + 'Things worth knowing' disclosure +
approval prompt*

## Task 3: Approve Folder Creation and Execute Batch Rename

10. After you send the approval message, watch the Workspace panel
    expand from '3/3' to '3/5': two new steps appear — 'Create new
    consolidated folder' and 'Rename and move all 28 files'.

![](./media/image10.png)

*Screenshot 10 — Workspace expands to 5 steps: 'Create folder?' dialog
appears*

![](./media/image11.png)

*Screenshot 11 — Approval message sent: execution mode begins*

![](./media/image12.png)

11. A 'Create folder?' dialog appears: Name: 'Renamed Files 2026-06-19'.
    Review the folder name — it uses today's date for audit
    traceability.

12. Click the dark 'Create' button to approve folder creation. DO NOT
    type in the message box while this dialog is open.

*Screenshot 12 — Create folder dialog: full 5-step plan visible in
Workspace*

![](./media/image13.png)

*Screenshot 13 — Cursor on Create button: about to approve folder
creation*

![](./media/image14.png)

13. A 'Use Microsoft Graph?' approval dialog will appear for the first
    file rename. Click the ▼ dropdown next to Approve and select 'Always
    allow Call graph' to grant batch permission.

14. If a 'Failed 1 action' error appears (locked file), note it and
    continue — Cowork will retry later. Watch for '5/5 ✓' in the
    Workspace when all renames complete.

*Screenshot 14 — Folder created: file ID retrieval begins, test-first
validation announced*

![](./media/image15.png)

*Screenshot 15 — 'Use Microsoft Graph?' first rename+move approval for
test file*

![](./media/image16.png)

*Screenshot 16 — Test file approved: all 27 remaining files queued for
batch processing*

![](./media/image17.png)

*Screenshot 17 — Test success confirmed: 'Always allow Call graph'
option presented*

![](./media/image18.png)

*Screenshot 18 — 'Always allow Call graph' option: session-scoped batch
permission granted*

![](./media/image19.png)

*Screenshot 19 — 'Failed 1 action': locked file isolated, batch
continues for remaining files*

![](./media/image20.png)

*Screenshot 20 — Exercise 1 complete: structured completion report with
'Still pending' section*

## Task 4: Create Topic Subfolders and Verify in OneDrive

15. In the message box type: 'Create subfolders by topic and move files
    accordingly' then press ↑.

16. Watch the Workspace panel grow from '5/5' to '5/7': two new steps
    appended — 'Creating topic subfolders' and 'Move files into topic
    subfolders'.

17. A 'Create folder?' dialog appears for each subfolder (Retail,
    Healthcare, Finance, Project Planning, Archive). Select 'Always
    allow Create folder' in the dropdown.

![](./media/image21.png)

*Screenshot 21 — 'Create subfolders by topic' instruction typed:
Workspace about to grow to 7 steps*

![](./media/image22.png)

*Screenshot 22 — 'Create folder?' for first topic subfolder: 'Always
allow Create folder' option*

![](./media/image23.png)

*Screenshot 23 — All 5 topic subfolders created: Step 7 file move
operations begin*

![](./media/image24.png)

*Screenshot 24 — 🟢 Complete: all 28 files renamed and sorted by topic*

![](./media/image25.png)

*Screenshot 25 — Exercise 1 → 2 transition: Exercise 2 governance audit
prompt typed and ready*

18. When complete, open OneDrive in a new tab: My files → Lab Files →
    Renamed Files 2026-06-19. Verify 5 topic subfolders exist with
    correct file counts.

19. Verify all folders show 'Private' in the Sharing column — Cowork did
    NOT alter any sharing settings.

![](./media/image26.png)

*Screenshot 26 — OneDrive verification: all 5 topic subfolders confirmed
in Renamed Files 2026-06-19*

![](./media/image27.png)

*Screenshot 27 — Archive subfolder: 3 correctly identified legacy files
confirmed*

![](./media/image28.png)

*Screenshot 28 — Finance subfolder: VendorPricing correctly classified
under Finance not Retail*

![](./media/image29.png)

*Screenshot 29 — Healthcare subfolder: 10 renamed clinical files
consolidated*

# Exercise 2 – OneDrive and SharePoint Governance Audit

Duration: 6 minutes | Difficulty: Intermediate

Audit the Lab Files folder for governance issues — duplicate files,
stale content, external sharing risks, and ownership gaps. Produce a
structured audit report with recommendations, then execute one approved
governance action.

## Task 1: Submit the Governance Audit Prompt

Enter the following prompt:

*Audit my 'Lab Files' folder for governance issues: duplicate files,
files not modified in over 6 months, files shared externally or with
'anyone' links, and files with no clear owner or topic. Recommend an
action per finding (archive, delete, restrict sharing) but take no
action yet.*

- Return to Cowork. In the same session from Exercise 1, type the
  governance audit prompt above and press ↑.

- Watch the Workspace panel expand: 3 new governance steps are appended
  to the existing 7 steps (Checking sharing/permissions, Analyze
  duplicates/staleness/ownership, Produce audit report).

20. Cowork confirms: 'I already have the inventory, hashes, and metadata
    from our earlier work' — no re-scanning needed.

21. The sharing permission checks run using read-only Graph API calls —
    no files are modified during the audit.

22. When complete, the full 4-section governance audit report appears.
    READ each section carefully before proceeding.

![](./media/image30.png)

*Screenshot 30 — Exercise 1→2 transition: governance prompt queued in
message box*

![](./media/image31.png)

*Screenshot 31 — Exercise 2 prompt submitted: 3 governance steps
appended to existing plan*

![](./media/image32.png)

*Screenshot 32 — Workspace at 7/10: sharing permission checks running
with read-only tools*

![](./media/image33.png)

*Screenshot 33 — Parallel sharing checks: incremental audit building
underway*

![](./media/image34.png)

*Screenshot 34 — Sharing scan complete: all 28 files confirmed
owner-only*

## Task 2: Review the Audit Report

- READ Section 1 — Duplicate files 🔴 (biggest issue): 3 exact
  duplicates identified by byte-identical content hash and 2 versioned
  near-duplicate pairs.

- READ Section 2 — Stale files ⭕: files identified as archive
  candidates based on filename-embedded dates (metadata dates were
  updated by the Exercise 1 renames).

- READ Section 3 — External shares ✅: all 28 files show owner-only
  permissions (CLEAN — no action needed).

- READ Section 4 — No clear owner 🟡: LegacyPolicy and all 13 empty
  .xlsx placeholder files flagged.

- READ the 'Suggested next steps (on your go-ahead)' numbered action
  menu at the bottom.

![](./media/image35.png)

*Screenshot 35 — Governance audit: Section 1 Duplicate files 🔴 with
exact and near-duplicate findings*

![](./media/image36.png)

*Screenshot 36 — Governance audit: Section 2 Stale files with honest
metadata date disclosure*

![](./media/image37.png)

*Screenshot 37 — Sections 2 continued, 3 (sharing ✅ clean), 4
(ownership 🟡 weak cases)*

![](./media/image38.png)

*Screenshot 38 — 5 recommended actions: numbered menu with deletion
staging disclosure*

## Task 3: Execute One Governance Recommendation

23. In the message box, type: '2' (to approve action \#2: archive the
    2024/2025/legacy items) and press ↑.

24. Cowork executes ONLY action \#2. Actions \#1, \#3, \#4, and \#5
    remain pending — approval of one does not authorise all.

25. When complete, verify in OneDrive that the Archive subfolder now
    contains 7 items (3 pre-existing + 4 newly moved).

26. Ask the Responsible AI question: 'which of these governance actions
    should an agent ever take WITHOUT human approval?' and read Cowork's
    response.

27. Note Cowork's autonomy boundary: 'Safe without approval' = read-only
    analysis only. 'Needs human approval' = any action that changes
    state.

![](./media/image39.png)

*Screenshot 39 — '2' sent: action \#2 only being executed, others remain
pending*

![](./media/image40.png)

*Screenshot 40 — Archive action complete: 7 legacy items now in Archive
subfolder*

![](./media/image41.png)

*Screenshot 41 — OneDrive Archive folder: all 7 items confirmed with
timestamps*

![](./media/image42.png)

*Screenshot 42 — Responsible AI question typed: proactive remaining work
surfacing*

![](./media/image43.png)

*Screenshot 43 — Responsible AI question submitted: 'Thinking...'
reasoning mode active*

![](./media/image44.png)

*Screenshot 44 — Responsible AI framework: 'Safe without approval' vs
'Needs human approval'*

![](./media/image45.png)

*Screenshot 45 — Responsible AI framework complete: Exercise 3 prompt
visible in message box*

# Exercise 3 – AI-Generated Excel Tracking and Teams Reporting

Duration: 6 minutes | Difficulty: Intermediate

Generate an Excel governance tracker with one row per file, then post a
3-line summary to Teams with a workbook link — demonstrating OneDrive →
Excel → Teams cross-app workflow orchestration from a single
instruction.

## Task 1: Submit the Excel and Teams Prompt

Enter the following prompt:

*Create an Excel workbook 'File Governance Tracker.xlsx' in Lab Files
with one row per file: name, type, topic, last modified, sharing status,
action taken. Then post a 3-line summary of today's cleanup to my Teams
channel with a link to the workbook.*

28. In the same Cowork session, type the Excel and Teams prompt above
    and press ↑.

29. Watch the Workspace 'Skills & Plugins' section activate the Excel
    plugin alongside the existing Microsoft Graph permission.

30. Cowork prepares the Excel workbook while simultaneously identifying
    the target Teams channel ('List teams') — both tasks run in
    parallel.

31. A 'Post to channel?' dialog appears — READ the 3-paragraph Teams
    message carefully before clicking Send.

32. Verify the 'Sent by Copilot Cowork' footer is included — this
    attribution is mandatory for all AI-generated Teams posts.

![](./media/image46.png)

*Screenshot 46 — Exercise 3 begins: Excel plugin activates, Teams
discovery runs in parallel*

![](./media/image47.png)

*Screenshot 47 — Workbook generated: Teams post beginning, 'Post to
channel?' dialog about to appear*

![](./media/image48.png)

*Screenshot 48 — 'Post to channel?' dialog: 3-paragraph Teams message
with AI attribution*

## Task 2: Verify the Workbook and Teams Post

33. Open the File Governance Tracker.xlsx from the Workspace Output
    panel link. Verify: 28 rows (one per file), 6 columns (File Name,
    Type, Topic, Last Modified, Sharing Status, Action Taken).

34. Confirm yellow-highlighted rows identify duplicate/flagged files —
    these carry forward from the Exercise 2 duplicate analysis.

35. Navigate to Teams → General channel → verify the governance post is
    live with 3 paragraphs and the 'Sent by Copilot Cowork' footer.

36. Click the 'Lab Files folder' hyperlink in the Teams post to confirm
    it opens the correct OneDrive location.

37. Workspace should show '12/12' — all Exercise 3 steps complete.

![](./media/image49.png)

*Screenshot 49 — File Governance Tracker.xlsx: open and verify all 28
rows*

![](./media/image50.png)

*Screenshot 50 — 'Post to channel?' full dialog: Workspace shows
Output + Skills + Always allowed*

![](./media/image51.png)

*Screenshot 51 — 'Both done': Workspace 12/12, workbook and Teams post
confirmed*

![](./media/image52.png)

*Screenshot 52 — Teams General channel: governance post live with 'Sent
by Copilot Cowork'*

![](./media/image53.png)

*Screenshot 53 — Teams post full view: 3 paragraphs with accurate
governance data*

![](./media/image54.png)

*Screenshot 54 — Teams post permanent record: 'Reply in thread' visible*

![](./media/image55.png)

*Screenshot 55 — Teams channel with compose box: channel ready for human
replies*

# Exercise 4 – Healthcare Documents Reorganisation

Duration: 8 minutes | Difficulty: Intermediate–Advanced

Classify healthcare files by clinical business function, reorganise the
Healthcare folder into 5 clinical category subfolders using a
department-aware naming convention, and update the governance tracker
workbook.

## Task 1: Review the Healthcare Folder and Submit the Classification Prompt

38. Open OneDrive → My files → Lab Files → Renamed Files 2026-06-19 →
    Healthcare. Verify 8 active clinical files are present (the 2
    compliance/HIPAA files archived in Exercise 2 should not be here).

39. Return to Cowork and enter the healthcare classification prompt
    below.

40. READ the classification table Cowork produces — it uses real
    healthcare business function taxonomy (HIM, Clinical Policy, Revenue
    Cycle, Quality/Safety, Clinical Engineering).

41. When asked to choose between subfolder reorganisation or adding a
    Business Function column to the tracker, type: 'add a Business
    Function column to the File Governance Tracker workbook'.

42. Watch Cowork regenerate the workbook as v2 with the new 7-column
    layout. Verify both v1 and v2 appear in the Workspace Output panel.

Enter the following healthcare classification prompt:

*Analyze all files in my Healthcare Documents folder. Categorize
documents into Patient Care, Insurance Claims, Compliance, Medical
Equipment, and Administration. Rename files using the format
YYYY-MM-DD_Department_DocumentType and create subfolders for each
category. Show the proposed changes before making any modifications.*

![](./media/image56.png)

*Screenshot 56 — Healthcare folder: 8 active files confirmed before
Exercise 4*

![](./media/image57.png)

*Screenshot 57 — Exercise 3→4 transition: healthcare classification
prompt queued*

![](./media/image58.png)

*Screenshot 58 — Healthcare classification table: standard clinical
business function taxonomy*

![](./media/image59.png)

*Screenshot 59 — Classification table continued: PHI awareness noted,
user choice offered*

![](./media/image60.png)

*Screenshot 60 — 'Add a Business Function column' instruction typed*

![](./media/image61.png)

*Screenshot 61 — Instruction sent: workbook regeneration begins*

![](./media/image62.png)

*Screenshot 62 — Workbook regeneration: 3-step parallel validation
running*

![](./media/image63.png)

*Screenshot 63 — Workbook v2 complete: cross-domain business function
taxonomy applied to all 28 files*

![](./media/image64.png)

*Screenshot 64 — File Governance Tracker v2 open in Excel: 7-column
layout*

![](./media/image65.png)

*Screenshot 65 — v2 completion summary: version management transparency
and follow-up options*

![](./media/image66.png)

*Screenshot 66 — v2 workbook summary with microphone paused indicator*

![](./media/image67.png)

*Screenshot 67 — File Governance Tracker v2 full workbook view: all 28
rows*

## Task 2: Reorganise the Healthcare Folder into 5 Clinical Subfolders

43. Enter the full Exercise 4 healthcare reorganisation prompt (shown
    below) and press ↑.

44. Cowork finds your Healthcare folder and presents the full proposed
    plan — nothing has been changed yet. READ all proposed renames
    carefully.

45. Note: '(still an exact duplicate)' appears next to
    InsuranceClaims_Cl...-v2.xlsx — the duplicate flag from Exercise 2
    is carried forward.

46. When ready, type 'proceed' in the message box and press ↑. This
    triggers a new 2-step plan: create 5 subfolders, then rename and
    move 8 files.

47. When the 🏁 completion banner appears, open OneDrive → Healthcare to
    verify 5 category subfolders exist with correct files in each.

![](./media/image68.png)

*Screenshot 68 — Exercise 4 reorganisation prompt:
YYYY-MM-DD_Department_DocumentType format*

![](./media/image69.png)

*Screenshot 69 — Cowork searching for Healthcare Documents folder*

![](./media/image70.png)

*Screenshot 70 — Healthcare folder found: proposed categorisation plan
with duplicate folder disambiguation*

![](./media/image71.png)

*Screenshot 71 — Proposed plan: Patient Care and Insurance Claims
sections*

![](./media/image72.png)

*Screenshot 72 — Proposed plan: Medical Equipment, Administration, and
'Three things to confirm'*

![](./media/image73.png)

*Screenshot 73 — 'proceed' typed: single-word approval triggers 3-phase
execution*

![](./media/image74.png)

*Screenshot 74 — New 2-step plan (0/2): subfolder creation begins*

![](./media/image75.png)

*Screenshot 75 — Step 1/2 complete: all 5 subfolders created, parallel
rename batch begins*

![](./media/image76.png)

*Screenshot 76 — Rename batch continuing: drive alias workaround applied
systematically*

![](./media/image77.png)

*Screenshot 77 — Workspace 1/2: subfolders done, rename batch visible
with progress indicators*

![](./media/image78.png)

*Screenshot 78 — 2/2 complete: all 8 healthcare files renamed and
sorted, open items noted*

![](./media/image79.png)

*Screenshot 79 — 🏁 Healthcare folder reorganized: Exercise 4 complete*

# Lab Summary

In this lab, you used Microsoft 365 Copilot Cowork to execute a complete
enterprise file governance workflow from natural language prompts. You
applied AI-powered file classification with an explicit
preview-before-action safety gate, ran a full governance audit across 28
files using cross-exercise session memory, and orchestrated a cross-app
reporting workflow spanning OneDrive, Excel, and Microsoft Teams.

Key Cowork capabilities demonstrated throughout:

- Multi-Step Workflow Decomposition — natural language prompt →
  structured multi-step plan in the Workspace panel

- Human-in-the-Loop Preview Gates — mandatory approval dialogs before
  every bulk file operation

- Progressive Batch Permission (Always allow Call graph) —
  session-scoped consent for repeated Graph API calls

- Cross-Exercise Context Retention — Exercise 1 content hashes and
  metadata reused directly in Exercise 2 and 4

- Graceful Failure Isolation — locked files flagged and retried
  automatically without aborting the batch

- Responsible AI Self-Articulation — Cowork accurately describes its own
  'Safe without approval' vs 'Needs human approval' boundary

- Cross-App Workflow Orchestration — OneDrive file data → Excel
  governance tracker → Teams stakeholder communication

- Healthcare Domain Classification — PHI awareness, clinical business
  function taxonomy, duplicate persistence across exercises
