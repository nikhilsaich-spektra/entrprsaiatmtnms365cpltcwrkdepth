# Lab 2: Daily Workday Assistant

| Item | Details |
|------|---------|
| **Estimated Time** | 20 minutes |
| **What You Build** | A personalized morning briefing that reads your calendar, summarizes important emails, and extracts tasks and follow-ups automatically. |
| **Skills Introduced** | Daily Briefing, Calendar Management, Email Triage, Task Extraction |

---

## Lab Objective

By the end of this lab, you will know how to:

- Use Copilot Cowork to build a morning briefing that combines calendar, email, and Teams context in a single prompt.
- Review and prioritize weekly meetings, including spotting missing agendas and scheduling conflicts.
- Triage your inbox into actionable categories: Needs My Reply, Waiting on Others, and FYI Only.
- Extract tasks and commitments from email and Teams, then create them in To Do with due dates.
- Iterate and refine by giving Cowork a follow-up correction and observing how it adjusts.

---

## What is Copilot Cowork?

Copilot Cowork is an AI-powered workspace inside Microsoft 365. Unlike a simple chatbot, Cowork can take multi-step actions across your apps. It reads your Outlook calendar, searches your inbox, scans Teams messages, and creates tasks in Microsoft To Do—all within a single conversation.

Think of it as an intelligent assistant that already has permission to access your work data and surface what matters most, without requiring you to open every app individually.

### Key terms you'll use in this lab

- **New task** – Start a fresh conversation in Cowork (like opening a new chat).
- **Workspace panel** – The right-hand panel that displays Cowork's live Steps and Skills as it works.
- **Steps** – The numbered tasks Cowork is completing on your behalf (visible in the Workspace panel).
- **Skills & Plugins** – The named capabilities Cowork activates for each type of task (for example, **Daily Briefing**, **Calendar Management**).

---

## Before You Begin — Pre-Lab Checklist

Confirm the following before starting the exercises:

- [ ] You have a lab account (provided by your instructor) for Microsoft 365.
- [ ] Your lab account has at least **2–3 calendar events** scheduled for this week.
- [ ] Your lab account has received **some emails in the last 3 days**.
- [ ] You can open a browser and navigate to **https://m365.cloud.microsoft**.

> **Note:** If any of these are missing, ask your instructor before proceeding.

# Exercise 1: Prepare a Personalized Workday Briefing

*Skills used: Daily Briefing — gathers calendar events, email summaries,
and Teams commitments in one pass.*

In this exercise you will write your first multi-source prompt, asking
Cowork to pull together everything you need to start your day in under
two minutes.

## Step 1 — Sign in and open Cowork

1.  Open your browser and navigate to m365.cloud.microsoft (or the
    Microsoft 365 URL your instructor provided). Sign in with your lab
    account credentials.

2.  At the top-left of the page you will see two tabs: Chat and Cowork.
    Click the Cowork tab.

![](./media/18e84db2ace698b5322d1e215a10753eb497bf2a.png)

- *The Cowork tab (highlighted) sits beside the Chat tab at the top-left
  of the Microsoft 365 sidebar. Previous tasks are listed below the
  navigation icons on the left.*

After clicking Cowork, the main area shows “What can I do for you?” —
this is your Cowork home screen. Take a moment to notice the navigation
icons on the left:

- New task — starts a fresh Cowork conversation.

- Search — finds previous tasks by keyword.

- Scheduled — shows any automated or recurring tasks.

- Customize — lets you set preferences and rules for Cowork.

- Below these icons you will see a list of recent task names from
  previous sessions (e.g. “Audit Lab Files for Governance Issues”).
  These are for reference — ignore them for now.

## Step 2 — Start a New Task and enter the briefing prompt

3.  Click New task in the left navigation panel. The central input box
    becomes active. You are ready to give Cowork your first instruction.

![](./media/993785606cf17e6f2ec728d8d2a66e0ac5793a39.png)

- *The Cowork home screen after clicking “New task”. The central text
  box (“What can I do for you?”) is active.*

- *Notice the suggested shortcuts below the input: “Organize my inbox”,
  “Arrange my week”, “Prep for a meeting” — these are quick-start
  templates.*

4.  Type or paste the following prompt into the input box, then press
    Send (the arrow icon) or hit Enter:

## Sample Prompt — Morning Briefing

```text
Create my morning briefing for today. Include:

1. My meetings today with a one-line purpose for each.
2. The three most important unread emails and why they matter.
3. Any deadlines or commitments mentioned in email or Teams in the last 48 hours.

Format it as a short brief that I can read in under two minutes.
```

> [!TIP]
> **Why this prompt works well**
>
> This prompt is effective because it clearly tells Copilot Cowork:
>
> - **What to include:** Meetings, emails, and deadlines.
> - **How many items:** The **three** most important unread emails.
> - **How to format the response:** A concise briefing that can be read in **under two minutes**.
>
> The more specific your instructions, the more relevant and actionable the response. Vague prompts such as *"Summarize my day"* typically produce more generic results.
## Step 3 — Watch Cowork work

After you send the prompt, Cowork begins working immediately. Watch what
happens in the Workspace panel on the right side of the screen.

![](./media/a66da7e9123ab689b13ab3567ecec3ff099d28d3.png)

- *Cowork acknowledges the task and begins processing. The Workspace
  panel (right) shows Steps 0/3: the first two steps — “Gather context”
  and “Prioritize and classify items” — are queued.*

- *The skill activated is “Daily Briefing”. The chat shows “Preparing to
  work with your daily briefing… Executing the next steps.”*

![](./media/745428714f51a7d830a228dc941c53475f6f849f.png)

- *Cowork is now on Step 1 of 3: “Gathering context”. It is
  simultaneously reading your calendar (View calendar), listing your
  email messages (List messages via Outlook), and searching Teams for
  recent mentions (@me recent, via Teams).*

- *The status line reads “Assembling the pieces.”*

Once Cowork finishes gathering data (Steps 1–3 complete), it writes your
briefing in the main chat area:

![](./media/6495246c2a745843f4077a16e3fbff7eb09c4c1b.png)

- *The completed morning briefing. Cowork surfaces: upcoming meetings
  and their purpose, high-priority emails that need action, and
  commitments from Teams “Workflows” messages flagged as overdue.*

- *At the bottom, “Suggested First Moves” lists specific actions ranked
  by urgency.*

### Review Your Morning Briefing

After Copilot Cowork generates your morning briefing, review the results and consider the following questions:

- Are your scheduled meetings listed correctly?
- Do the **three priority emails** match the ones you would have selected?
- Do the **Suggested First Moves** reflect real deadlines and commitments, or do they appear to be making assumptions?

> [!NOTE]
> It is normal if some information is missing or not entirely accurate. Copilot Cowork can only use the data available in your Microsoft 365 environment. In the next exercise, you'll refine the prompt to improve the quality and relevance of the results.

5.  Read the briefing critically. Note one thing that is missing or
    weighted incorrectly — you will use this observation in the next
    step.

## Step 4 — Add a personalization rule and re-run

6.  In the same chat (do NOT click New task — stay in this
    conversation), type a follow-up instruction that adds a
    personalization rule. Use one of the examples below or write your
    own:

## Sample Follow-up — Personalization Rule

```text
Update my morning briefing with the following preferences:

- Always list emails from my manager first.
- Ignore newsletters and promotional emails.
```

> [!TIP]
> Personalization rules help Copilot Cowork tailor its responses to your work style and priorities. Adding clear preferences—such as prioritizing messages from your manager or excluding low-value emails—results in more relevant and actionable briefings.

![](./media/e349b3305e70dea87ba669dfb145add9f899362c.png)

- *The follow-up prompt typed into the message box at the bottom. The
  previous briefing is visible above. Cowork is about to update its
  saved rules for all future briefings in this session.*

7.  Cowork will confirm the rules it has saved, and explain that they
    will apply automatically to all future briefings.

![](./media/4456f17a1bc73489eef30436f79c3d4e42c3c2ac.png)

- *Cowork confirms it has saved two personalization rules: (1)
  Manager-first — anything from your manager appears at the top of every
  section; (2) Ignore newsletters — promotional email is dropped
  entirely. It also notes a caveat: “manager-first” only activates once
  a manager is set in your org profile.*

## Exercise 1 Checkpoint

Before moving to **Exercise 2**, verify the following:

- [ ] Your briefing includes all three components:
  - Calendar meetings
  - Priority emails
  - Recent commitments or deadlines
- [ ] At least one personalization rule has been applied and confirmed by Copilot Cowork.
- [ ] The **Workspace** panel displays **Daily Briefing** under **Skills & Plugins**.

> [!NOTE]
> If Copilot Cowork does not find any meetings or emails, your lab account may not contain sufficient sample data. Contact your instructor to verify that the required lab data has been seeded before continuing.

# Exercise 2: Review Meetings and Calendar Priorities

*Skills used: Calendar Management — scans your full week, identifies
missing agendas, detects conflicts, and recommends actions.*

In this exercise you will ask Cowork to look across your entire week —
not just today — and give you specific recommendations about which
meetings deserve your attention and which can be shortened or declined.

## About the **Calendar Management** Skill

When Copilot Cowork performs calendar-related tasks, it automatically activates the **Calendar Management** skill. You can see the active skill in the **Workspace** panel under **Skills & Plugins**.

Using this skill, Copilot Cowork can:

- Read meeting titles, dates, times, durations, attendees, and agenda details.
- Detect scheduling conflicts and overlapping meetings.
- Identify meetings that are missing descriptions, agendas, or attendees.
- Distinguish between recurring meetings, one-time meetings, focus time, and calendar holds.

> [!IMPORTANT]
> The **Calendar Management** skill only analyzes your calendar. It **does not** create, modify, reschedule, or delete meetings unless you explicitly instruct Copilot Cowork to do so.

## Step 5 — Run the calendar review prompt

1.  Continue in the same Cowork conversation (do not start a new task).
    Type or paste the prompt below:

## Sample Prompt — Weekly Calendar Review

```text
Review my calendar for the rest of this week.

- Identify meetings that do not have an agenda or description.
- Highlight any scheduling conflicts or overlapping meetings.
- Recommend which meetings I should prioritize, shorten, reschedule, or decline.
- Explain the reasoning behind each recommendation.
```

> [!TIP]
> This prompt helps Copilot Cowork analyze your calendar by asking it to:
>
> - **Assess meeting quality** by identifying events with missing agendas or descriptions.
> - **Detect conflicts** such as overlapping or back-to-back meetings.
> - **Provide actionable recommendations** for prioritizing, shortening, rescheduling, or declining meetings.
> - **Explain its reasoning**, making it easier to decide whether to act on the suggestions.
>
> Asking for both recommendations and explanations helps you understand *why* Copilot Cowork suggests a particular action rather than simply listing calendar events.

![](./media/b03f4e837f265da87d7e0804dc6016fc83edd58a.png)

- *The calendar prompt typed at the bottom of the existing conversation.
  Note that the Workspace panel now shows an updated Steps list: “Scan
  calendar for rest of week and classify events” and “Triage and present
  recommendations” — two new steps have been added to the session.*

![](./media/3df4aed3c19121ea7044f0ae63fab17d0641df9a.png)

- *Cowork begins processing the calendar prompt. The Workspace panel
  (right) shows Steps 3/5: “Generate briefing” is complete (checked),
  and “Scan calendar for rest of week and classify events” is now
  active. The Skills & Plugins section now shows both “Daily Briefing”
  and “Calendar Management”, reflecting that both capabilities are in
  use for this session.*

![](./media/249220b3e29477509190e43f978bae676df005bf.png)

- *Cowork has completed the calendar scan (Steps 5/5 all checked). The
  response begins with a “Week at a Glance” table listing each event
  with its date, event name, type (Meeting / Focus block / No-meetings
  hold), and status (e.g., “No agenda” flagged in orange, “Full agenda”
  shown in green, “Protected” for focus blocks).*

![](./media/a63cfe7e0756849d70c2fbf61e9f7dda3676afe5.png)

- *The calendar analysis continues below the table, broken into three
  clear sections: (1) Meetings with no agenda — lists the specific
  meeting(s) lacking a description or purpose; (2) Conflicts — confirms
  whether any events overlap; (3) Recommendations — labelled
  “Prioritize”, “Defend”, and “Fix or drop”, each with a specific
  rationale for the action. Scroll down to read all three sections.*

## Review Your Calendar Analysis

After Copilot Cowork completes the calendar review, verify the following:

- Did it identify the meeting that was intentionally seeded without an agenda or description?
- Were any overlapping or conflicting meetings detected correctly?
- Do the recommendations to **prioritize**, **shorten**, **reschedule**, or **decline** meetings make sense based on the meeting purpose and attendees?

> [!NOTE]
> If the seeded scheduling conflict was **not** detected, continue the conversation with this follow-up prompt:

```text
Are any of my meetings tomorrow overlapping?
```

This helps Copilot Cowork perform a more focused analysis of your calendar and can surface conflicts that may have been missed in the initial review.

2.  Read each recommendation. For each one, ask yourself: “Would I
    actually do this?” The goal is to build judgment about when to trust
    AI calendar advice.

## Exercise 2 Checkpoint

Before moving to **Exercise 3**, verify the following:

- [ ] The calendar review includes a structured weekly overview.
- [ ] At least one meeting has been identified as missing an agenda or description.
- [ ] The **Workspace** panel displays **Calendar Management** under **Skills & Plugins**.
- [ ] You can explain the purpose of the following recommendation types:
  - **Prioritize** – High-value meetings that should remain on your calendar.
  - **Defend** – Focus time or important work blocks that should be protected from interruptions.
  - **Fix or Drop** – Meetings that should be updated (for example, by adding an agenda or rescheduling) or removed if they no longer provide value.

> [!NOTE]
> If your results do not match the expected outcomes, verify that your lab account contains the required seeded calendar events before continuing.

# Exercise 3: Summarize Important Emails and Pending Actions

*Skills used: Email Triage — groups inbox messages into actionable
categories and drafts reply angles for urgent items.*

Managing email by opening every message is slow and reactive. In this
exercise, Cowork reads your last 3 days of email and organizes it into
three buckets so you can act on only what truly needs your attention.

## About **Email Triage** in Copilot Cowork

When Copilot Cowork performs email triage, it uses the **Outlook** connector to analyze your recent messages and organize them into actionable categories:

- **Needs My Reply** – Emails that require your response, approval, or a decision.
- **Waiting on Others** – Conversations where you've sent a request or question and are awaiting a response.
- **FYI Only** – Informational emails, newsletters, and notifications that do not require action.

For emails in the **Needs My Reply** category, Copilot Cowork also suggests a **one-line response angle** to help you get started. This is intended as a draft or starting point—not a completed reply.

> [!IMPORTANT]
> Copilot Cowork **does not** send emails on your behalf unless you explicitly instruct it to do so. It can read, summarize, and draft email responses, but you remain in control of sending them.

## Step 6 — Run the inbox triage prompt

1.  In the same Cowork conversation, type or paste:

## Sample Prompt — Inbox Triage

```text
Review my inbox from the last three days.

- Group my messages into the following categories:
  - Needs My Reply
  - Waiting on Others
  - FYI Only
- For each email in **Needs My Reply**, suggest a one-line response angle to help me get started.
```

> [!TIP]
> This prompt helps Copilot Cowork organize your inbox by:
>
> - **Identifying emails that require your attention** and separating them from informational messages.
> - **Highlighting pending conversations** where you're waiting for someone else to respond.
> - **Providing a suggested response angle** for each email that needs your reply, making it quicker to draft responses.
>
> By defining both the categories and the desired output, you receive a structured, actionable inbox summary instead of a generic list of emails.

![](./media/a373950ed641eacd8c8090570109f8065b70cd87.png)

- *The inbox triage prompt entered at the bottom of the conversation.
  The Workspace panel (right) now shows Steps 5/5 complete from the
  previous exercise, and a new step — “Review inbox from last 3 days” —
  appears in the updated list. The session is building cumulatively:
  Cowork remembers the previous steps and adds to them.*

![](./media/fb5028bc1195d62a81f3572c9f9b9120be848956.png)

- *Cowork’s triage output — the “Needs My Reply” bucket. Each item is
  listed with: the subject line (bold), a brief summary of what the
  email is about, and an “Angle:” line — a suggested one-line response
  direction. Notice the red dot icon indicating urgency on overdue
  items. The Workspace panel (right) shows Step 6/6 complete.*

![](./media/cf48fd62e9558cc004e414ad0ddaef5139217f95.png)

- *The “Waiting on Others” and “FYI Only” buckets. “Waiting on Others”
  shows an item with an invalid email address (flagged with a warning
  icon) — Cowork has noticed the bounce. “FYI Only” groups repeated
  automated digest emails together under a single entry rather than
  listing them individually. At the bottom, Cowork proactively offers to
  draft replies for the two highest-stakes items.*

**Step 7 — Correct the grouping with a follow-up**

AI triage is not always perfect. This step teaches you how to give
Cowork a correction mid-conversation. Look at the “FYI Only” list — if
you spot an email that should actually be in “Needs My Reply”, use the
prompt below to move it:

## Sample Follow-up — Correct a Group

```text
Treat the contract email as **Needs My Reply** instead of its current category.
```

> [!TIP]
> Follow-up prompts allow you to refine Copilot Cowork's results without starting over. If an email has been categorized incorrectly, simply specify how it should be classified. Cowork will use your feedback to update the current conversation and produce a more accurate inbox triage.

![](./media/79b5d7b9e83972130ff662b09434eb5d671a1110.png)

- *Cowork responds to the correction. It confirms which email it has
  matched (“Northwind Franchise Deal — Legal Sign-off Still Pending”),
  explains why it now qualifies as “Needs My Reply” (the “by Friday”
  exclusivity clause has passed), and saves a standing rule:
  contract/legal sign-off emails will always be treated as reply items
  going forward. The updated “Needs My Reply” list is shown with the
  corrected item now at position \#1.*

![](./media/8ce11bd0f8d0ce4c714a92fdccfe955d4d310ded.png)

- *The follow-up correction message typed at the bottom of the chat.
  Cowork has moved the Northwind Franchise contract email to the “Needs
  My Reply” bucket and updated its reply angle to reflect the overdue
  exclusivity clause.*

![](./media/cd63b92d6ad52558d56d7dce472a0956343e4fc7.png)

- *The updated “Needs My Reply” list after the correction. The Northwind
  Franchise email is now item \#1, with a specific reply angle: “Give
  Priya your decision on the exclusivity clause + escalation next step,
  or a firm new ETA.” The other three items follow. Cowork closes by
  asking a clarifying question — a sign that it is working
  collaboratively rather than just guessing.*

## Exercise 3 Checkpoint

Before moving to **Exercise 4**, verify the following:

- [ ] Your inbox has been organized into the following categories:
  - **Needs My Reply**
  - **Waiting on Others**
  - **FYI Only**
- [ ] Each email in the **Needs My Reply** category includes a one-line response angle.
- [ ] You successfully reclassified at least one email using a follow-up prompt.
- [ ] Copilot Cowork confirmed the updated categorization and applied it as a standing rule for the current conversation.
- [ ] No emails were sent—Copilot Cowork only analyzed your inbox and suggested responses.

> [!NOTE]
> Copilot Cowork does not send emails automatically. It summarizes, categorizes, and drafts suggestions, but all sending actions require your explicit approval.

**Exercise 4: Extract Tasks and Follow-up Items**

*Skills used: Task Extraction — reads email and Teams threads,
identifies commitments assigned to you, creates To Do tasks with due
dates.*

Buried in email threads and Teams conversations are commitments you made
— deadlines you agreed to, replies you promised, figures you offered to
confirm. In this exercise, Cowork finds all of them and turns them into
proper tasks.

## About **Task Extraction**

Copilot Cowork extracts tasks by analyzing information from multiple Microsoft 365 sources:

- **Outlook Email** – Scans email subjects and message content for action-oriented phrases such as:
  - "I'll send..."
  - "Can you confirm..."
  - "By Friday..."
  - "Action required"
- **Microsoft Teams** – Reviews recent Teams conversations to identify commitments and follow-up actions.
  > **Note:** In some lab environments, Teams data may be generated by automated workflow bots rather than direct user conversations.

When Copilot Cowork identifies a task with a **clear due date**, it automatically creates the task in **Microsoft To Do**. If the due date is unclear or ambiguous, it asks you to confirm the deadline instead of making assumptions—demonstrating responsible AI behavior.

If **Microsoft To Do** is unavailable in the lab environment, Copilot Cowork maintains a tracked task list within the conversation and asks you to confirm any missing deadlines before finalizing the tasks.

> [!IMPORTANT]
> Copilot Cowork only creates tasks when it has sufficient information. If a due date or assignment is unclear, it requests clarification rather than guessing.

---

## Step 8 — Run the task extraction prompt

1.  In the same Cowork conversation, type or paste:

## Sample Prompt — Task Extraction

```text
Review my email and Microsoft Teams messages from this week.

- Extract every task or commitment assigned to me.
- Create a task for each item that includes a due date when one is specified.
- List any tasks where the due date is unclear so I can confirm it before the task is created.
```

> [!TIP]
> This prompt helps Copilot Cowork:
>
> - **Identify action items** from both Outlook email and Microsoft Teams conversations.
> - **Create tasks automatically** when a clear due date is available.
> - **Flag ambiguous deadlines** and ask for confirmation instead of making assumptions.
> - **Consolidate commitments** into a single task list, making it easier to track and complete your work.
>
> Asking Cowork to identify unclear deadlines ensures your task list remains accurate and demonstrates responsible AI behavior by avoiding incorrect due dates.

![](./media/57d651bc22755e7277f6999e1b7344d0d201a037.png)

- *The task extraction prompt entered at the bottom of the conversation.
  The Workspace panel updates to show a new step: “Extracting
  commitments”. The session now has 6/7 steps completed from all
  previous exercises — Cowork is maintaining full context throughout.*

![](./media/529717391d2bf0301939a40014cd730ef0fac414.png)

- *Cowork begins processing. The Workspace panel shows Steps 6/7 active,
  with “Extract commitments from email + Teams and create tasks” now
  visible. The chat shows: “I’ll pull the full week from both email and
  Teams, then read the key threads closely to extract exact commitments
  and deadlines.” Then: “Executing tasks…”*

![](./media/fe37c15d15accf1a953db70a5ab4234f341a0ac6.png)

- *Cowork completes the Teams scan and reports a finding: “The Teams
  activity this week was all automated pipeline digests from the
  Workflows bot — no person-assigned tasks there.” It falls back
  gracefully: “Let me set them up as proper tasks in your To Do.” It
  then attempts to find the task list — and reports a minor issue:
  “Finding your task list: Failed. Microsoft To Do isn’t accessible in
  this environment.” This is expected behavior in some lab setups.*

![](./media/1500502a7913c85750d72d62a9b073baf51f8764.png)

- *The task extraction results. Cowork presents two sections: (1) Tasks
  created — showing the Northwind Franchise task as Due Friday Jun 19
  (overdue), with full context about the commitment and why it is
  flagged red; (2) Not created — flagging for your call: the Project
  Planning Workshop invite bounce (not a true task assignment) with a
  note explaining why it was excluded. A “Note on Teams” explains why no
  Teams tasks were found.*

![](./media/c9f938d8b33036620171b669fbcfcb264e7c96d2.png)

- *The extracted task list continued. Two tasks have unclear deadlines:
  the Zava co-marketing fund (no date given by the finance director) and
  the Approval Request Brief ID 2 (30-day payment terms, no deadline
  stated). Cowork lists both under “Created, but deadline was unclear —
  please confirm” and asks: “Want me to set due dates on \#2 and \#3, or
  draft Priya’s overdue reply first?” This is the agent asking rather
  than guessing.*

**Step 9 — Confirm ambiguous due dates**

When Cowork flags ambiguous deadlines, your job is to decide. This is a
key AI work habit: agents should ask when they don’t know, and humans
should decide. Type a response to confirm the dates:

## Sample Follow-up — Set Due Dates

```text
Set due dates for tasks 1 and 2 as follows:

- Task 1: Due tomorrow at 5:00 PM.
- Task 2: Due this Friday at 3:00 PM.
```

> [!TIP]
> Use follow-up prompts to update tasks after they have been extracted. Specify the task number or title and provide a clear due date. Copilot Cowork will update the tasks or ask for clarification if the date is ambiguous.

![](./media/99ba7298a9fa6d0c1f3cbca6cb0b214377fa34fc.png)

- *Cowork presents a “Due date” picker for task \#2 (the Zava
  co-marketing fund). It offers three suggested dates with
  reasoning: (1) Fri Jun 26 — end of week, keeps the deal moving without
  rushing; (2) Wed Jun 24 — mid-week, tighter given the active deal; (3)
  Mon Jun 22 — tomorrow, treat as urgent. A “Describe another option”
  field and a “Skip” button are also available.*

![](./media/f62370e264a17470ae74cbd724c28861e8f3ac48.png)

- *The due date picker with option 2 (Wed Jun 24) selected (highlighted
  in blue). The “Submit” button is active at the bottom right. Click
  your preferred option to submit.*

2.  Select your preferred due date option (option 2 — Wed Jun 24 is
    recommended for this lab) and click Submit.

![](./media/0014b72519b35a779b6c74a6242f71b2ebcb4f96.png)

- *The due date selection confirmed. The Submit button is now active
  (visible at the bottom right of the date picker). Cowork is processing
  the selection.*

![](./media/3283f202e50fb04744636b92c9255def3542e846.png)

- *After submitting the date, Cowork asks for the due date of task \#3
  (Approve or reject Brief ID 2). It shows the task name again and asks:
  “What due date should I set for the Zava co-marketing fund task
  (confirm minimum order value & reply to Raj)? Wed Jun 24.” This
  confirms the first date was saved and Cowork is now handling the
  second ambiguous task.*

![](./media/862b85cedff042ff25e32aa25788cb0664780f9a.png)

- *Task \#2 (Zava co-marketing fund) is confirmed as due Wednesday
  Jun 24. Cowork shows the updated task list: (1) Northwind Franchise —
  Due Fri Jun 19 (overdue); (2) Zava co-marketing fund — Due Wed Jun
  24; (3) Approve/reject Brief ID 2 — deadline still TBC. It asks: “Want
  me to set a date on Brief ID 2 too, or draft Priya’s overdue reply
  first?”*

## Step 10 — Review the complete task list

![](./media/ea2be624665dde870324d7ec56dc2b8d24d9bd39.png)

- *The final session task list. Cowork presents an “Open tasks” table
  with task numbers, descriptions, and due dates. Below, a “Completed
  this session” section confirms all actions taken in this conversation:
  morning briefing, 3-day inbox triage, and commitment extraction (steps
  1–7). Cowork closes by offering to draft Priya’s reply next.*

3.  Open Microsoft To Do (or Planner) or Calendar in a separate browser
    tab to verify the tasks were created. Confirm the task names, due
    dates, and that no extra tasks were invented.

![](./media/835b2de1f0abba3f7fdf3ad57e91261de9a56129.png)

- *Outlook Calendar (opened separately to verify the week’s data). The
  Work Week view shows June 22–26, 2026. Events visible: Monday 8 AM
  “meeting with OD” (no agenda — this is the meeting Cowork flagged in
  Exercise 2), Monday/Wednesday 9 AM “Focus Time” blocks (protected),
  Tuesday 9 AM “Project Sync” (full agenda), and Friday “No Meetings
  Hold”. This confirms the calendar data Cowork was reading throughout
  the lab.*

## Exercise 4 Checkpoint

Before moving to the next exercise, verify the following:

- [ ] Task extraction analyzed both **Outlook Email** and **Microsoft Teams**.
- [ ] At least one task was created with a confirmed due date.
- [ ] Copilot Cowork identified tasks with ambiguous deadlines and requested clarification instead of guessing.
- [ ] You confirmed at least one due date using the **date picker** rather than entering the date manually.
- [ ] You can view the created tasks in **Microsoft To Do** or, if To Do was unavailable, in the **Cowork task list** displayed within the conversation.

> [!NOTE]
> Depending on your lab environment, Microsoft To Do may not be available. In that case, Copilot Cowork will maintain a task list within the chat while still allowing you to review and confirm due dates.

**Bonus: Draft a Reply Email (Optional)**

If you finished early, continue in the same session to see Cowork draft
an email reply on your behalf. This is not part of the formal lab but
demonstrates how Cowork can extend from triage to action.

## Bonus Prompt — Draft Priya's Reply

```text
Draft a professional reply to Priya's email.

- Acknowledge the key points in the email.
- Answer any questions or requests.
- Clearly state the next steps and any deadlines.
- Keep the tone concise, professional, and friendly.
- Do not send the email—only prepare it as a draft for my review.
```

> [!TIP]
> This prompt demonstrates how Copilot Cowork can generate a polished email draft while keeping you in control. Always review the draft for accuracy, completeness, and tone before sending.

![](./media/cd256af27270f0bc4a9136d85524681ddc1cb6c5.png)

- *Cowork saves the Priya reply draft in Outlook. It summarizes what the
  draft contains: acknowledges the delay (it’s past the Friday
  commitment), leaves a placeholder for the actual legal position on the
  §4.3 exclusivity clause, recommends escalating to Marcus, and re-asks
  the open question about whether legal has the latest contract version.
  Three “Before this goes out” items are listed — things you must fill
  in before sending.*

![](./media/5c4ce24dd3c4b22567f3a7fe4f02d9c3fee22600.png)

- *The user follows up: “adjust the tone/escalation stance first and
  draft marcus escalation itself.” Cowork accepts and begins working on
  both drafts simultaneously, as shown in the Workspace panel.*

![](./media/b10c1b70179f09be5866cb695769ba9396d70c2e.png)

- *Cowork updates the Priya draft in Outlook (Update draft via Outlook)
  and searches for Marcus’s contact (“Searching people for Marcus VP
  Operations”). When no match is found, it tries a broader search
  (“Searching people for Marcus”). The step counter now reads 7/10,
  showing how a single follow-up can trigger multiple actions.*

![](./media/215d95d8ed834eb070868fec6393152a7f3ac5df.png)

- *Both drafts are saved. The response is structured into two
  sections: (1) Priya reply — tone & stance adjusted (now reads as a
  clear decision rather than a hedge); (2) Marcus escalation — drafted
  (concise executive-appropriate subject and body, three key facts from
  the thread, CC’d to Priya). A “Before sending” checklist gives two
  manual steps required before either email goes out.*

![](./media/fa37538e3f1b1cae9bf195883a4ba40fd7a7fb4b.png)

- *The Marcus escalation draft continues, showing: subject line, CC
  field, bullet-point body. A warning note: “No recipient set — Marcus
  isn’t in your directory, so you’ll need to add his email address.”
  Cowork leaves both as drafts, awaiting your final review and approval
  before sending.*

## Key Learning from the Bonus Exercise

In this exercise, notice how Copilot Cowork handled the email drafting process responsibly:

1. **Drafted the email** without sending it automatically.
2. **Identified missing information**, such as the **§4.3 stance** and **Marcus's email address**, before completing the draft.
3. **Requested clarification** instead of guessing the recipient's email address or other missing details.

> [!IMPORTANT]
> Copilot Cowork is designed to support **responsible AI** practices. For actions that are difficult or impossible to undo—such as sending an email—it always asks for your confirmation before proceeding. You remain in control of reviewing, editing, and approving the final action.

### Final Validation Checklist 

Use this checklist to confirm you have completed all four exercises
successfully. Tick each item before submitting your lab work to your
instructor.

# Lab 2 — Final Validation

Use this checklist to verify that you have successfully completed all exercises in this lab.

---

## Exercise 1 — Morning Briefing

- [ ] The morning briefing includes:
  - Calendar meetings with a one-line purpose for each
  - The three most important unread emails
  - Commitments and deadlines from the last 48 hours
- [ ] At least one personalization rule (for example, **manager-first** or **ignore newsletters**) was applied and confirmed.
- [ ] The **Daily Briefing** skill appeared in the **Workspace** panel under **Skills & Plugins**.

---

## Exercise 2 — Calendar Review

- [ ] A weekly calendar overview was generated, including meeting types and agenda status.
- [ ] At least one meeting was identified as missing an agenda or description.
- [ ] The seeded scheduling conflict was detected, or you successfully identified it using the follow-up overlap prompt.
- [ ] The **Calendar Management** skill appeared in the **Workspace** panel under **Skills & Plugins**.

---

## Exercise 3 — Email Triage

- [ ] Your inbox was organized into the following categories:
  - **Needs My Reply**
  - **Waiting on Others**
  - **FYI Only**
- [ ] Each email in the **Needs My Reply** category included a one-line response angle.
- [ ] You successfully moved at least one email to a different category using a follow-up prompt.

---

## Exercise 4 — Task Extraction

- [ ] Tasks were extracted from Outlook email (Microsoft Teams may show no tasks if only automated bot messages were available).
- [ ] At least one task was created with a confirmed due date.
- [ ] Copilot Cowork identified ambiguous deadlines and requested confirmation instead of making assumptions.
- [ ] You verified the created tasks in **Microsoft To Do** or, if To Do was unavailable, in the **Cowork task list** displayed within the conversation.

> [!SUCCESS]
> **Congratulations!** You have successfully completed **Lab 2 – Executive Productivity Workflows**. You have learned how to use Copilot Cowork to generate a morning briefing, review and optimize your calendar, triage email, extract actionable tasks, and safely refine AI-generated results using follow-up prompts—all while maintaining user control through responsible AI practices.

### Key Concepts Recap

# Key Concepts

| Concept | What it means in this lab |
|---------|----------------------------|
| **Cowork** | The Microsoft 365 AI assistant that performs multi-step tasks across Outlook, Teams, and Microsoft To Do within a single conversation. |
| **Workspace Panel** | The panel in Copilot Cowork that displays the agent's live **Steps** (current actions) and **Skills & Plugins** (active capabilities). |
| **Skill / Plugin** | A specialized capability that Copilot Cowork activates to perform a specific task. Examples include **Daily Briefing** and **Calendar Management**. |
| **Daily Briefing Skill** | Used in **Exercise 1** to gather information from your calendar, email, and Teams, then generate a personalized morning briefing. |
| **Calendar Management Skill** | Used in **Exercise 2** to analyze your Outlook calendar, identify scheduling conflicts and missing agendas, and recommend actions for each meeting. |
| **Prompt Specificity** | The quality of Copilot Cowork's responses improves when prompts clearly specify **what to include**, **how many items**, and **how the output should be formatted**. |
| **Follow-up Correction** | A prompt submitted within the same conversation to refine or correct a previous response. Copilot Cowork uses this feedback as a standing rule for the remainder of the session. |
| **Ambiguous Deadlines** | When Copilot Cowork cannot determine a task's due date with confidence, it asks for confirmation instead of making assumptions. |
| **Draft vs. Send** | Copilot Cowork creates email drafts for review but never sends emails automatically. Sending an email always requires your explicit approval. |

> [!TIP]
> Throughout this lab, pay attention to the **Workspace** panel. It shows which **Skills & Plugins** Copilot Cowork activates for each task, helping you understand how different capabilities work together to complete multi-step workflows.

## Troubleshooting Common Issues

## Troubleshooting

## Copilot Cowork Found No Emails or Meetings

**Possible Cause**

The lab account may not contain the required sample data, or Outlook permissions have not yet synchronized.

**Resolution**

- Ask your instructor to verify that the lab account has been seeded with the required data.
- To check Outlook connectivity, run the following prompt:

```text
Check if you can access my Outlook calendar.
```

---

## Calendar Conflict Was Not Detected

**Possible Cause**

The conflicting meetings may belong to different calendar categories, or the events were created after the most recent synchronization.

**Resolution**

Run the following follow-up prompt to perform a more targeted search:

```text
Are any of my meetings tomorrow overlapping?
```

---

## Microsoft To Do Is Not Available

**Possible Cause**

Some lab environments restrict access to Microsoft To Do. This is a known limitation in certain Microsoft 365 sandbox tenants.

**Resolution**

If Microsoft To Do is unavailable, Copilot Cowork automatically displays a tracked task list within the conversation. Use this task list to complete the exercise and validation checkpoint.

> [!NOTE]
> These issues are commonly related to the lab environment rather than Copilot Cowork itself. If the problem persists after following the suggested steps, contact your instructor for assistance.

## End of Lab 2

Congratulations! You have completed **Lab 2 – Executive Productivity Workflows**.

In this lab, you used **Microsoft 365 Copilot Cowork** to build an AI-powered morning productivity workflow from a single conversation. You learned how to:

- Generate a personalized morning briefing using your calendar, email, and Teams data.
- Review and optimize your calendar by identifying conflicts, missing agendas, and scheduling priorities.
- Organize your inbox into actionable categories and draft response suggestions.
- Extract tasks and commitments from email and Teams, then create or track them with appropriate due dates.

> [!IMPORTANT]
> The techniques practiced throughout this lab—**writing specific prompts**, **using follow-up corrections**, and **confirming ambiguous information**—are essential skills for working effectively with AI assistants. These practices help produce more accurate, relevant, and trustworthy results while ensuring you remain in control of important decisions and actions.

---

## Next Steps

In the next lab, you'll build on these foundational skills by exploring more advanced Copilot Cowork capabilities, including multi-step workflows, automation, and enterprise productivity scenarios.
