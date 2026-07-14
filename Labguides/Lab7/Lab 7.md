# Lab 7: Building a Personal Work Dashboard with Microsoft Copilot Cowork

**Duration:** Approximately 40 minutes

**Prerequisites:** Microsoft 365 account · Copilot Cowork access ·
Outlook, Teams, Calendar, and OneDrive enabled

**What you build:** A self-refreshing HTML work dashboard emailed to
your inbox every morning.

# **1. Overview & What You Will Build**

Modern workdays suffer from app-switching overload. You start in
Outlook, jump to Teams, check your calendar, hop into OneDrive — and
before long, an hour has passed without meaningful work.

In this lab you will use Microsoft Copilot Cowork to build a single HTML
page that answers one question every morning:

***“What deserves my attention right now?”***

## **What the Dashboard Includes**

- **Header** — today's date, last-refresh timestamp, and a hint that
  everything is clickable.

- **KPI Strip** — six at-a-glance tiles: overdue actions, unread emails,
  meetings tomorrow, Teams unread, active projects, and out-of-office
  teammates.

- **Urgent Banner** — red-bordered block surfacing items needing
  attention today.

- **Tomorrow's Schedule** — every event with time, response status, and
  conflict markers.

- **Prep Notes** — short crib sheets for meetings that need preparation.

- **Top Projects** — your 5–8 active projects with an inferred 'Next'
  action each.

- **Week Calendar Load** — a pure CSS bar chart showing meeting density
  per day.

- **Time Allocation** — a CSS doughnut chart breaking the week by
  category.

- **Emails Needing a Reply** — filtered to only messages that need a
  response.

- **OOF Radar** — teammates out of office this week and next.

- **Unread Teams Chats** — top chats with one-line previews.

- **Recent Files in Flight** — most recently modified OneDrive folders.

**ℹ NOTE** Every item on the dashboard is clickable and opens directly
back into Outlook, Teams, or OneDrive — you never have to copy-paste a
reference again.

*Screenshot: Final dashboard open in a browser — full page view showing
all sections.*

# **2. Understanding the Tools**

## **What Is Microsoft Copilot Cowork?**

Copilot Cowork is a task-automation layer inside Microsoft Copilot that
can:

- Run multi-step, long-horizon tasks on your behalf.

- Query Microsoft Graph (your calendar, inbox, Teams, OneDrive) in
  parallel.

- Write and save files to a built-in output/ folder.

- Schedule recurring tasks — including sending emails with attachments.

**ℹ NOTE** Cowork is different from a regular Copilot chat. In a regular
chat, Copilot answers questions. In Cowork, Copilot executes multi-step
jobs that can run automatically on a schedule.

## **What Is Microsoft Graph?**

Microsoft Graph is the unified API that gives Copilot Cowork secure,
permission-gated access to your Microsoft 365 data. The dashboard uses
these Graph endpoints:

- **Calendar** — /me/calendarView fetches events, response status,
  organizer, and webLink.

- **Inbox** — /me/messages fetches unread, flagged, and high-importance
  messages with webLink.

- **Teams** — /me/chats fetches unread chat threads with last-message
  previews and webUrl.

- **OneDrive** — /me/drive/recent fetches recently modified folders and
  files with webUrl.

- **Search** — M365 search finds action-required emails (access
  renewals, expense reminders, training).

# **3. Prerequisites Checklist**

Before starting the lab, confirm each item below. If any item is
missing, contact your Microsoft 365 administrator.

- **Microsoft 365 account** — you can sign in at microsoft365.com with
  your work or school account.

- **Copilot Cowork access** — you see a 'Cowork' option or tab when you
  open Microsoft Copilot.

- **Outlook enabled** — you can open Outlook and see your inbox.

- **Calendar enabled** — you can open the M365 Calendar and see your
  meetings.

- **Teams enabled** — you can open Microsoft Teams and see your chats.

- **OneDrive enabled** — you can access OneDrive and see recent files.

- **At least 5 upcoming events** — you have meetings on your calendar so
  the dashboard has real data to show.

**⚠ WARNING** Cowork requires specific Microsoft 365 licensing. If you
do not see the Cowork option inside Copilot, you may need an upgraded
plan. Contact your IT administrator or visit microsoft.com/copilot for
licensing details.

## Task 1 - Open Copilot Cowork

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

1. In the task input box, enter the following prompt (1) and then click the **Submit (2)** icon.

    ![](./media/n7.png)

    ```
    Build me a personal work dashboard as a single HTML file at output/dashboard.html.

    Gather fresh data in parallel from across my Microsoft Graph:

    1. Calendar — today's remaining events and the next 7 days, including response status, organizer, and online-meeting status

    2. Inbox — unread, flagged, and high-importance messages from the last few days

    3. Teams — unread chats with last-message previews

    4. OneDrive — recently modified folders in my personal drive

    5. Search M365 for any action-required emails (access renewals, expense reminders, training notices)

    Infer my top 5–8 active projects by clustering recurring meetings, email threads, and customer names. Surface a "Next" action for each.

    Render a single-page HTML dashboard with this layout:

    - Header: greeting with today's date, last-refresh timestamp (Pacific time), "Click any item to open it" hint

    - KPI strip (6 tiles): overdue actions, unread emails, meetings tomorrow, Teams unread, active projects, OOF this week. Color the urgent ones red, warnings amber, healthy ones green.

    - Urgent banner (red-bordered): items that need attention today

    - Tomorrow's Schedule card: every event with time chip, title, response badge, organizer, conflict markers

    - Prep Notes card: short crib sheets for meetings that need prep

    - Top Projects card: inferred projects with a "Next" line each

    - Week Calendar Load: pure CSS bar chart of meeting counts per day for the upcoming week (flex-aligned `<div>` bars with `linear-gradient` fills and inline `style="height: NN%"`)

    - Time Allocation: pure CSS doughnut chart splitting the week by category (`<div>` with `conic-gradient` background and a `::after` hole, paired with a static legend)

    - Emails Needing a Reply card: the few messages that actually want a response — filter out newsletters, alerts, external pitches

    - Long-Term Action Items card: overdue tasks, weekly deadlines, upcoming milestones

    - Training & Learning card: upcoming training sessions

    - OOF Radar card: teammates out this week & next, with a heads-up if any organize a meeting I'm attending

    - People to Follow Up With card: name + one-line context

    - Unread Teams Chats card: top chats with one-line previews

    - Recent Files in Flight card: most recently modified OneDrive folders

    - Footer: refresh schedule note

    Visual style: soft blue gradient background (#f5f7fa to #e8edf3), rounded white cards with subtle shadow, 'Segoe UI' font, Microsoft accent #0078d4, color-coded badges (green #dcfce7/166534 = accepted, amber #fef3c7/92400e = tentative, red #fee2e2/991b1b = no response or overdue, purple #ede9fe/5b21b6 = organizer). Use a 2-column grid for the main sections, 3-column for the smaller cards, collapsing to single column under 1024px.

    PORTABILITY REQUIREMENT — the file must render correctly with zero external network requests and zero JavaScript executing. No `<script src="...">` to any CDN. No Chart.js, D3, or other charting libraries. No external fonts (use the system 'Segoe UI' stack). All charts must be built from HTML + CSS only: bar chart = flex-aligned gradient `<div>` bars; doughnut = `conic-gradient` background with a `::after` pseudo-element hole. All KPI tiles must render their final value directly in the HTML — never start at `0` and rely on JS to fill in the number. Any animation or interactivity (slide-up entry, pulse dot, dark mode toggle) is allowed but must be additive: CSS-driven where possible, and any inline script must gracefully no-op if blocked (e.g. wrap `localStorage` access in `try/catch`). The dashboard will be opened in sandboxed previews, email-attachment viewers, and locked-down browsers where scripts and CDNs frequently do not run.

    Premium touches to include (all must work without JavaScript or external requests):

    - Dark mode toggle in the header (pill button with sun/moon icon, CSS-variable theming). Persist preference via `localStorage` wrapped in `try/catch` so it gracefully no-ops where storage is blocked. The page must render correctly in light mode by default even if the toggle script never runs.

    - KPI tiles render their final value directly in the HTML (e.g. `<div class="kpi-value">22</div>`). Optional polish: a CSS-only entry animation (e.g. `@keyframes` opacity/translate). Do not start the tile text at `0` and rely on JS to count it up — that breaks in any context where scripts don't execute.

    - Slide-up entrance animation on KPI tiles and cards via pure CSS `@keyframes`.

    - 3-color header gradient (#0078d4 → #00bcf2 → #5e60ce) with radial-gradient overlay highlights.

    - Pulse dot animation on the "Last refreshed" timestamp via pure CSS `@keyframes`.

    - CSS bar chart for Week Calendar Load — `<div>` columns whose heights are inline `style="height: NN%"` percentages. Fill classes: `.heavy` (red `linear-gradient` when count ≥ 7), `.light` (gray when = 2), `.normal` (blue otherwise). Number labels sit at the top of each bar in white text.

    - CSS doughnut for Time Allocation — `<div class="donut">` with `conic-gradient(...)` background, segment angles computed at build time from the percentages, and a `::after` pseudo-element using the card background color to punch out the center hole. Render the legend as static HTML next to it.

    - Project health dots next to each project name — red (hot), green (active), amber (watch), with a soft box-shadow glow.

    - Avatar initials circles on the People card (avatar-1 through avatar-5 with gradient backgrounds).

    - Decorative ⚠ watermark in the urgent banner using a `::before` pseudo-element.

    CRITICAL — every item must be clickable. Wrap every event, email, chat, file, project card, training item, action item, and person in an <a href="..." target="_blank"> anchor tag:

    - Calendar events → fetch via QueryGraph on /me/calendarView with $select including webLink; use the event's webLink

    - Emails → fetch via QueryGraph on /me/messages with $select including webLink; use the message's webLink

    - Teams chats → fetch via QueryGraph on /me/chats with $select including webUrl; use the chat's webUrl

    - OneDrive folders → use the item's webUrl

    - People → mailto:<email> for email follow-ups, or the 1:1 chat webUrl for Teams follow-ups

    - Project cards / training items without a canonical link → use an Outlook inbox search URL like https://outlook.office.com/mail/inbox?searchquery=<keyword>

    Style anchors with class names so they look like regular cards (color: inherit; text-decoration: none; display: block or flex; subtle hover background).

    Save to output/dashboard.html. After writing, confirm the file exists in output/.
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

1. In the task input box, enter the following prompt (1) and then click the **Submit (2)** icon.

    ![](./media/n12.png)

    ```
    Set up a scheduled task that refreshes output/dashboard.html every weekday at :55 past the hour, from 6:55 AM through 5:55 PM Pacific time - auto-detect this from the device/browser's local timezone rather than the account's configured IST setting, and don't ask me to confirm it. If the device timezone can't be detected, default to America/Los_Angeles and proceed without asking.
    Use the same data-gathering and rendering instructions from the dashboard we just built - capture webLink/webUrl for every item so links stay clickable on every refresh.
    At the 9 AM Pacific run only (and no other hour), also send me an email:

    To: <inject key="AzureAdUserEmail"></inject>
    Subject: "Your Daily Work Dashboard - [today's date in M/D format]"
    Body: brief greeting noting the dashboard is attached, every item is clickable, and the in-session version refreshes hourly
    Attachment: output/dashboard.html

    For all other hours, refresh the file silently - no email.
    Handle daylight saving automatically by re-deriving the Pacific offset at each run rather than hardcoding it, so the :55 anchor never drifts.
    Name the task "Refresh work dashboard (hourly at 9 AM, email at 9 AM)"
    ```

1. On the **Create recurring task?** prompt, review the **Name**, **Repeat**, **Run in**, and **Description** details, ensure **Run once now** is checked, then click **Always allow Setup scheduled prompt**.

   ![](./media/n31.png)

1. Confirm that the message **"Done — your scheduled task is now active"** is displayed, verifying that the **Refresh work dashboard** task has been scheduled successfully.

   ![](./media/n32.png)

1. Under **Workspace**, verify that the **Refresh work dashboard** task is listed under **Scheduled task**, running **Every week on Monday, Tuesday**, and click on it to open the task.

   ![](./media/n33.png)

1. On the **Refresh work dashboard** blade, verify that the task status is **Active**.

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

1. Go through the **dashboard.html** file and review all the sections available, including **Overview**, **Needs your attention today**, **Tomorrow's Schedule**, **Prep Notes**.**Week Calendar Load** and **Time Allocation**.

   ![](./media/n22.png)

   ![](./media/n23.png)

1. On the **dashboard.html** file, click on **Theme** to toggle between light and dark mode.

   ![](./media/n25.png)

1. Verify that the **dashboard.html** file switches to **dark mode**.

   ![](./media/n24.png)

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

1. Click the **Cowork (1)** tab and then select **Scheduled (2)**.

   ![](./media/n28.png)

1. Confirm the schedule is now active, with **Manage schedules (1)** and click **... (2)** to review the **Edit**, **Run now**, **Pause**, and **Delete** options.

   ![](./media/n39.png)

