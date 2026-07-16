# Lab 7: Building a Personal Work Dashboard with Microsoft Copilot Cowork

**Estimated Duration:** 60 minutes

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

# **Exercise 1 — Open Copilot Cowork**

**Objective:** Navigate to Copilot Cowork and confirm it is ready to
receive a task.

## **Step 1 — Sign In to Microsoft 365**

1.  Open your browser and navigate to https://microsoft365.com.

2.  Click Sign In (top right) and enter your work or school email
    address.

3.  Enter your password and complete any multi-factor authentication
    (MFA) prompt.

4.  Confirm you land on the Microsoft 365 home page.

![](./media/image1.png)

**✓ TIP** If you do not see Copilot in the sidebar, try clicking the
nine-dot App Launcher grid (top left) and searching for 'Copilot'.

## **Step 2 — Switch to the Cowork Tab**

5.  Inside Copilot, look for tabs or sections near the top of the panel
    — you should see options such as 'Chat' and 'Cowork' (or 'Tasks').

![](./media/image2.png)

6.  Click Cowork (or the Tasks tab, depending on your version).

7.  You should see a 'New Task' button and possibly a list of any
    previous tasks.

![](./media/image3.png)

**ℹ NOTE** If your Copilot interface only shows a chat box and no Cowork
tab, your tenant may not yet have Cowork enabled. Check with your
administrator.

# **Exercise 2 — Build the Dashboard**

**Objective:** Paste the dashboard-build prompt into Cowork and watch it
gather your live Microsoft 365 data and generate dashboard.html.

## **Step 1 — Create a New Cowork Task**

8.  In the Cowork tab, click New Task (or the + button).

![](./media/image4.png)

9.  A text input area will appear for you to describe the task.

## **Step 2 — Copy Prompt 1**

Below is the complete Prompt 1. Copy the entire block and paste it into
the Cowork task input.

**PROMPT 1 — copy everything in this block**

Build me a personal work dashboard as a single HTML file at
output/dashboard.html.

Gather fresh data in parallel from across my Microsoft Graph:

1\. Calendar — today's remaining events and the next 7 days, including
response status, organizer, and online-meeting status

2\. Inbox — unread, flagged, and high-importance messages from the last
few days

3\. Teams — unread chats with last-message previews

4\. OneDrive — recently modified folders in my personal drive

5\. Search M365 for any action-required emails (access renewals, expense
reminders, training notices)

Infer my top 5–8 active projects by clustering recurring meetings, email
threads, and customer names. Surface a "Next" action for each.

Render a single-page HTML dashboard with this layout:

\- Header: greeting with today's date, last-refresh timestamp (Pacific
time), "Click any item to open it" hint

\- KPI strip (6 tiles): overdue actions, unread emails, meetings
tomorrow, Teams unread, active projects, OOF this week. Color the urgent
ones red, warnings amber, healthy ones green.

\- Urgent banner (red-bordered): items that need attention today

\- Tomorrow's Schedule card: every event with time chip, title, response
badge, organizer, conflict markers

\- Prep Notes card: short crib sheets for meetings that need prep

\- Top Projects card: inferred projects with a "Next" line each

\- Week Calendar Load: pure CSS bar chart of meeting counts per day for
the upcoming week (flex-aligned \`\<div\>\` bars with
\`linear-gradient\` fills and inline \`style="height: NN%"\`)

\- Time Allocation: pure CSS doughnut chart splitting the week by
category (\`\<div\>\` with \`conic-gradient\` background and a
\`::after\` hole, paired with a static legend)

\- Emails Needing a Reply card: the few messages that actually want a
response — filter out newsletters, alerts, external pitches

\- Long-Term Action Items card: overdue tasks, weekly deadlines,
upcoming milestones

\- Training & Learning card: upcoming training sessions

\- OOF Radar card: teammates out this week & next, with a heads-up if
any organize a meeting I'm attending

\- People to Follow Up With card: name + one-line context

\- Unread Teams Chats card: top chats with one-line previews

\- Recent Files in Flight card: most recently modified OneDrive folders

\- Footer: refresh schedule note

Visual style: soft blue gradient background (#f5f7fa to \#e8edf3),
rounded white cards with subtle shadow, 'Segoe UI' font, Microsoft
accent \#0078d4, color-coded badges (green \#dcfce7/166534 = accepted,
amber \#fef3c7/92400e = tentative, red \#fee2e2/991b1b = no response or
overdue, purple \#ede9fe/5b21b6 = organizer). Use a 2-column grid for
the main sections, 3-column for the smaller cards, collapsing to single
column under 1024px.

PORTABILITY REQUIREMENT — the file must render correctly with zero
external network requests and zero JavaScript executing. No \`\<script
src="..."\>\` to any CDN. No Chart.js, D3, or other charting libraries.
No external fonts (use the system 'Segoe UI' stack). All charts must be
built from HTML + CSS only: bar chart = flex-aligned gradient
\`\<div\>\` bars; doughnut = \`conic-gradient\` background with a
\`::after\` pseudo-element hole. All KPI tiles must render their final
value directly in the HTML — never start at \`0\` and rely on JS to fill
in the number. Any animation or interactivity (slide-up entry, pulse
dot, dark mode toggle) is allowed but must be additive: CSS-driven where
possible, and any inline script must gracefully no-op if blocked (e.g.
wrap \`localStorage\` access in \`try/catch\`). The dashboard will be
opened in sandboxed previews, email-attachment viewers, and locked-down
browsers where scripts and CDNs frequently do not run.

Premium touches to include (all must work without JavaScript or external
requests):

\- Dark mode toggle in the header (pill button with sun/moon icon,
CSS-variable theming). Persist preference via \`localStorage\` wrapped
in \`try/catch\` so it gracefully no-ops where storage is blocked. The
page must render correctly in light mode by default even if the toggle
script never runs.

\- KPI tiles render their final value directly in the HTML (e.g. \`\<div
class="kpi-value"\>22\</div\>\`). Optional polish: a CSS-only entry
animation (e.g. \`@keyframes\` opacity/translate). Do not start the tile
text at \`0\` and rely on JS to count it up — that breaks in any context
where scripts don't execute.

\- Slide-up entrance animation on KPI tiles and cards via pure CSS
\`@keyframes\`.

\- 3-color header gradient (#0078d4 → \#00bcf2 → \#5e60ce) with
radial-gradient overlay highlights.

\- Pulse dot animation on the "Last refreshed" timestamp via pure CSS
\`@keyframes\`.

\- CSS bar chart for Week Calendar Load — \`\<div\>\` columns whose
heights are inline \`style="height: NN%"\` percentages. Fill classes:
\`.heavy\` (red \`linear-gradient\` when count ≥ 7), \`.light\` (gray
when = 2), \`.normal\` (blue otherwise). Number labels sit at the top of
each bar in white text.

\- CSS doughnut for Time Allocation — \`\<div class="donut"\>\` with
\`conic-gradient(...)\` background, segment angles computed at build
time from the percentages, and a \`::after\` pseudo-element using the
card background color to punch out the center hole. Render the legend as
static HTML next to it.

\- Project health dots next to each project name — red (hot), green
(active), amber (watch), with a soft box-shadow glow.

\- Avatar initials circles on the People card (avatar-1 through avatar-5
with gradient backgrounds).

\- Decorative ⚠ watermark in the urgent banner using a \`::before\`
pseudo-element.

CRITICAL — every item must be clickable. Wrap every event, email, chat,
file, project card, training item, action item, and person in an \<a
href="..." target="\_blank"\> anchor tag:

\- Calendar events → fetch via QueryGraph on /me/calendarView with
$select including webLink; use the event's webLink

\- Emails → fetch via QueryGraph on /me/messages with $select including
webLink; use the message's webLink

\- Teams chats → fetch via QueryGraph on /me/chats with $select
including webUrl; use the chat's webUrl

\- OneDrive folders → use the item's webUrl

\- People → mailto:\<email\> for email follow-ups, or the 1:1 chat
webUrl for Teams follow-ups

\- Project cards / training items without a canonical link → use an
Outlook inbox search URL like
https://outlook.office.com/mail/inbox?searchquery=\<keyword\>

Style anchors with class names so they look like regular cards (color:
inherit; text-decoration: none; display: block or flex; subtle hover
background).

Save to output/dashboard.html. After writing, confirm the file exists in
output/.

![](./media/image5.png)

## **Step 3 — Paste and Submit the Prompt**

10. Click inside the Cowork task input area and paste Prompt 1.

11. Click Submit, Send, or press Enter to start the task.

![](./media/image6.png)

![](./media/image7.png)

![](./media/image8.png)

## **Step 4 — Wait for Cowork to Complete the Task**

After submitting, Cowork will begin working. You will see it:

- Fan out parallel queries to your calendar, inbox, Teams, and OneDrive.

- Infer your active projects from recurring meeting and email patterns.

- Generate the HTML file and save it to output/dashboard.html.

![](./media/image9.png)

**ℹ NOTE** The first run typically takes 5–10 minutes.

![](./media/image10.png)

![](./media/image11.png)

## **Step 5 — Confirm the File Was Created**

12. When the task finishes, Cowork will display a completion message.

13. Look for a confirmation that says something like 'Saved to
    output/dashboard.html'.

14. If a preview link or download button appears, click it to open the
    dashboard.

![](./media/image12.png)

![](./media/image13.png)

![](./media/image14.png)

![](./media/image15.png)

![](./media/image16.png)

![](./media/image17.png)

**✓ Exercise 2 Complete**

# **Exercise 3 — Schedule the Hourly Refresh**

**Objective:** Use Prompt 2 to create a scheduled task that regenerates
the dashboard every hour on weekdays and emails it to your inbox at 9
AM.

With the dashboard built, you now want it to stay fresh automatically —
without having to re-run anything manually. Prompt 2 sets up a recurring
scheduled task inside Cowork.

## **Step 1 — Start a New Cowork Task for the Schedule**

15. In the Cowork tab, click New Task again.

16. A fresh input area will appear.

## **Step 2 — Copy and Paste Prompt 2**

**PROMPT 2 — copy everything in this block**

Set up a scheduled task that refreshes output/dashboard.html every
weekday at :55 past the hour, from 6:55 AM through 5:55 PM Pacific. Use
the same data-gathering and rendering instructions from the dashboard we
just built — capture webLink/webUrl for every item so links stay
clickable on every refresh.

At the 9 AM run only (and no other hour), also send me an email:

To: \<odl_user_2270231@gpssandboxlabs100124.onmicrosoft.com\>

Subject: "Your Daily Work Dashboard — \[today's date in M/D format\]"

Body: brief greeting noting the dashboard is attached, every item is
clickable, and the in-session version refreshes hourly

Attachment: output/dashboard.html

For all other hours, refresh the file silently — no email.

Name the task "Refresh work dashboard (hourly at 9 AM, email at 9 AM)".

![](./media/image18.png)

## **Step 3 — Submit and Confirm the Scheduled Task**

17. Paste Prompt 2 into the new task input.

18. Double-check that your email address is correct in the prompt.

19. Click Submit.

20. Wait for Cowork to confirm the task was created. A task should
    appear in the Cowork task list with the name you gave it.

![](./media/image19.png)

![](./media/image20.png)

![](./media/image21.png)

![](./media/image22.png)

![](./media/image23.png)

![](./media/image24.png)

![](./media/image25.png)

![](./media/image26.png)

## **Step 4 — Verify the Scheduled Task Is Active**

21. Click on the task name in the Cowork task list to open its details.

22. Confirm the schedule shows weekdays, :55 past the hour, 6:55 AM–5:55
    PM Pacific.

![](./media/image27.png)

![](./media/image28.png)

23. Confirm the task status shows Active or Running (not Paused).

![](./media/image29.png)

![](./media/image30.png)

![](./media/image31.png)

![](./media/image32.png)

![](./media/image33.png)

![](./media/image34.png)

**⚠ WARNING** Editing a scheduled task automatically pauses it. If you
ever modify the task, remember to resume it from the Cowork task list
afterward.

**✓ Exercise 3 Complete**

# **7. Exploring the Dashboard**

Now that the dashboard is built and scheduled, take a few minutes to
explore each section. Use the guide below to understand what you are
looking at.

## **Header & KPI Strip**

- The header shows your name, today's date, and the last-refreshed
  timestamp (with a pulsing dot). Click any item in any section — they
  all open the original source.

- The KPI strip has six tiles. Red tiles indicate urgency, amber
  indicates a warning, green means healthy.

![](./media/image35.png)

## **Tomorrow's Schedule & Prep Notes**

- Each meeting row has a color-coded badge: green = Accepted, amber =
  Tentative, red = No Response or Needs Action.

- If Cowork detects that a meeting needs preparation (customer demo,
  manager 1:1), a Prep Notes card appears with a short crib sheet.

- Click any meeting to open it directly in Outlook Calendar.

![](./media/image36.png)

![](./media/image37.png)

![](./media/image38.png)

## **Week Calendar Load & Time Allocation Charts**

- The bar chart shows how many meetings fall on each day of the upcoming
  week. Heavy days (7+ meetings) appear in red.

- The doughnut chart splits your week by category: customer-facing,
  training, internal syncs, focus time, and admin.

- Both charts are built from pure CSS — they work even in email viewers
  and locked-down browsers.

![](./media/image39.png)

![](./media/image40.png)

![](./media/image41.png)

## **Dark Mode Toggle**

- Look for the sun/moon pill button in the top-right corner of the
  dashboard header.

- Click it to switch between light and dark modes. Your preference is
  saved in the browser.

![](./media/image42.png)

![](./media/image43.png)

# **8. Troubleshooting Common Issues**

- **No Cowork tab visible** — Cowork may not be enabled for your tenant.
  Contact your Microsoft 365 administrator or check your Copilot
  licensing tier.

- **Task runs but dashboard is empty** — you may have very little
  calendar or email data. Add a few test meetings and emails, then
  re-run Prompt 1.

- **KPI tiles all show zero** — this is normal if your mailbox has no
  unread messages or no upcoming meetings. The values reflect live data.

- **Links in the dashboard don't open** — some email clients strip links
  from HTML attachments. Open the attachment in a browser instead of the
  email preview.

- **Scheduled task shows 'Paused'** — you or Cowork may have edited the
  task. Open the task in Cowork and click Resume.

- **Morning email never arrives** — check that the task is Active and
  that your email address is correct. Also check your Junk/Spam folder.

- **Charts look broken** — the charts require a modern browser. Try
  Chrome, Edge, or Firefox. Older Outlook preview panes may not render
  CSS correctly.

- **Dark mode resets on refresh** — the preference is stored in browser
  localStorage. If you opened the HTML in a sandboxed viewer,
  localStorage is blocked — this is expected.

# **9. Customization Tips**

Once you are comfortable with the base dashboard, try these
customizations.

## **Lock the Layout**

After the dashboard looks exactly how you want it, tell Cowork:

> ***“Lock this dashboard format in for all future ones.”***

This updates the scheduled task so every hourly refresh preserves the
approved layout, CSS, and premium visual touches.

![](./media/image44.png)

![](./media/image45.png)

![](./media/image46.png)

![](./media/image47.png)

![](./media/image48.png)

![](./media/image49.png)

![](./media/image50.png)

![](./media/image51.png)

## **Add or Remove Sections**

Tell Cowork which sections you want to add or remove. For example:

> *"Remove the Training & Learning card — I don't use it."*
>
> *"Add a card showing my top 5 external contacts from this week's
> emails."*
>
> *"Move the OOF Radar card to the top, just under the KPI strip."*

## **Change the Refresh Frequency**

24. Open the scheduled task in Cowork.

25. Edit the schedule to your preferred interval (e.g., every 30
    minutes, or only once at 7 AM).

26. Remember to Resume the task after editing.

**✓ TIP** The morning email is only sent at 9 AM — all other refreshes
silently overwrite the file. If you want the email at a different time,
update that in the prompt when you edit the scheduled task.

# **10. Summary & Next Steps**

## **What You Accomplished**

- Navigated to Copilot Cowork and created a new task.

- Used Prompt 1 to generate a fully functional personal work dashboard
  from live Microsoft 365 data.

- Used Prompt 2 to schedule the dashboard to refresh every hour on
  weekdays and email it to your inbox each morning.

- Explored all sections of the dashboard and understood what each tile
  and chart represents.

- Learned how to troubleshoot common issues and customize the dashboard.

## **Next Steps**

- Run the dashboard for a full week and note which sections you use
  most.

- Lock the layout once you are happy with the design.

- Share the recipe with a colleague and have them build their own.

- Explore other Copilot Cowork use cases — the same pattern works for
  project status reports, client briefings, and team digests.
