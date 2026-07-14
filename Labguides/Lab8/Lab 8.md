# Lab 8: Build and Publish a Custom Microsoft 365 Copilot Cowork Plugin

Estimated Duration: 20 minutes

## Lab Overview

Microsoft 365 Copilot can be extended using Copilot Cowork Plugins,
enabling organizations to integrate enterprise knowledge, business
processes, and external services directly into Copilot experiences.

In this lab you will build a Financial Research Plugin that extends
Microsoft 365 Copilot with live financial research capabilities by
connecting to the SEC EDGAR public repository through a Remote Model
Context Protocol (MCP) Server.

Instead of manually authoring the plugin, you will use a single
structured AI prompt to generate a complete, deployment-ready plugin
package. You will then review the generated assets, validate the
package, publish it through the Microsoft 365 Admin Center, and test the
plugin inside Copilot Cowork.

The build prompt specifies the required Microsoft 365 Unified App
Manifest structure, plugin skills, connector configuration, packaging
rules, validation requirements, and deployment process — so the AI
produces a package that is ready to upload without hand-editing.

> [!NOTE]
> **What is MCP?**
>
> The **Model Context Protocol (MCP)** is an open standard that enables AI assistants to securely connect to external tools and data sources through a standardized interface.
>
> In this lab, the plugin uses a **Remote MCP Server**, which hosts the required tools and retrieves live data from the **SEC EDGAR** service at runtime. This means the plugin does **not** store or bundle the data itself—it queries the remote service whenever a user makes a request, ensuring the information is current.

## Learning Objectives

After completing this lab, you will be able to:

- Launch Microsoft 365 Copilot and enable Copilot Cowork.

- Generate a complete Copilot Cowork plugin package using a structured
  AI prompt.

- Understand the structure of a Microsoft 365 Copilot plugin (manifest,
  skills, connector, icons).

- Review the generated manifest, skills, and connector configuration.

- Validate the plugin package against the devPreview schema before
  deployment.

- Publish the plugin through the Microsoft 365 Admin Center.

- Test plugin functionality inside Microsoft 365 Copilot Cowork using
  natural-language queries.

## Lab Prerequisites

- Microsoft 365 Copilot license (Premium).

- Copilot Cowork enabled for your account.

- Microsoft 365 Administrator (Global Admin or equivalent) permissions.

- Internet access and a modern web browser (Microsoft Edge or Chrome
  recommended).

- Access to Microsoft 365 Copilot or Claude for AI-assisted plugin
  generation.

> [!IMPORTANT]
> **Administrator permissions are required** to upload a custom app through the **Microsoft 365 Admin Center**.
>
> If you are using a **training** or **ODL sandbox**, sign in with the **administrator account** provided for the lab—not your personal Microsoft account.
>
> Without administrator permissions, you will **not** be able to complete **Exercises 5 and 6**.

# **Solution Overview**

## **What Are We Building?**

You will build a Financial Research Plugin for Microsoft 365 Copilot
Cowork. The plugin extends Copilot with specialized financial-research
capabilities using publicly available SEC filing data.

Rather than relying only on Copilot's built-in knowledge, the plugin
connects to a Remote MCP Server that exposes SEC EDGAR data. When a user
asks a financial question, Copilot selects the appropriate skill,
retrieves the required information from the SEC EDGAR service, and
returns a summarized, formatted response.

## **Plugin Architecture**

## Plugin Architecture

```mermaid
flowchart TD
    A[Microsoft 365 Copilot] --> B[Financial Research Plugin]

    B --> C[Skills]
    B --> D[Plugin Manifest]
    B --> E[MCP Connector]

    E --> F[SEC EDGAR Public Server]
    F --> G[Financial Filing Data]
```

## **Plugin Components**

The generated plugin package consists of:

- A Microsoft 365 Unified App Manifest (manifest.json).

- Seven Copilot skills (one SKILL.md per skill folder).

- A single Remote MCP Connector (SEC EDGAR public server).

- Two plugin icons: color.png (192 × 192) and outline.png (32 × 32).

- A single deployment package (ZIP) with manifest.json at the root.

The package follows the Microsoft 365 Unified App Manifest (devPreview)
schema and includes all assets required for deployment.

## **Skills Included in the Plugin**

The plugin contains seven specialized skills that map natural-language
requests to financial-research tasks. Each skill uses the SEC EDGAR MCP
connector to retrieve and summarize public-company information.

## Available Skills

| Skill | Description | Example Prompt |
|-------|-------------|----------------|
| **Company Snapshot** | Retrieves a company's profile, business overview, and key financial information. | `Give me a snapshot of Microsoft.` |
| **Financial Trends** | Analyzes historical revenue, profit, and growth trends over time. | `Show Microsoft's five-year revenue trend.` |
| **Peer Comparison** | Compares two or more public companies using key financial metrics. | `Compare Microsoft and Amazon.` |
| **Risk Factor Analysis** | Reviews risk disclosures from SEC filings and summarizes key risks. | `What risks are listed in Microsoft's latest 10-K?` |
| **Earnings Deep Dive** | Summarizes quarterly earnings reports and highlights business performance. | `Analyze Microsoft's latest earnings.` |
| **Executive Research** | Retrieves executive leadership information and executive compensation details. | `Who is Microsoft's CEO?` |
| **Filing Search** | Searches SEC filings using keywords, phrases, or topics. | `Find filings mentioning Artificial Intelligence.` |

> [!NOTE]
> **Common SEC Filing Types**
>
> - **10-K** – Annual report containing audited financial statements, business overview, and risk factors.
> - **10-Q** – Quarterly report providing financial updates between annual reports.
> - **8-K** – Current report filed to disclose significant business events between regular reporting periods.
> - **DEF 14A** – Proxy statement containing executive compensation, board information, and shareholder voting matters.

## **Plugin Workflow**

The following workflow shows how Microsoft 365 Copilot processes a
financial-research request:

## Request Processing Flow

```mermaid
flowchart TD
    A[User submits a prompt]
    B[Copilot identifies the appropriate skill]
    C[Plugin invokes the skill]
    D[Remote MCP Connector calls SEC EDGAR]
    E[SEC EDGAR returns filing data]
    F[Copilot summarizes and formats the response]
    G[Response displayed to the user]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
```

## Task 1 - Review Plugins and Skills in Cowork

### **Objective**

Verify that Microsoft 365 Copilot and Copilot Cowork are available and
ready for plugin development.

1. Click the **Cowork (1)** tab, then click **New task (2)**.

   ![](./media/n1.png)

1. Click the **+ (1)** icon in the **Start a task** field, then select **Customize (2)**.

   ![](./media/n2.png)

1. On the **Plugins (1)** tab, review the installed and built-in plugins.

   ![](./media/n3.png)

1. On the **Skills** tab, confirm no skills have been added under **Your skills**, and review the **Built-in** skills available, including **PDF**, **Word**, and **Excel**.

   ![](./media/n4.png)

## Task 2 - Generate the Plugin Using Cowork

1. From the Cowork interface, navigate to New Chat to start a new chat session.

1. Enter the task **prompt (1)** describing the plugin package to build, then click the **Send (2)** button.

   ![](./media/n5.png)

    ```
    # Microsoft 365 Copilot Cowork Plugin Generation Prompt
    
    Build a Microsoft 365 Copilot Cowork (Frontier) plugin package called
    **Financial Research** that:
      - Adds seven SEC EDGAR research skills.
      - Includes one Remote MCP Connector (SEC EDGAR public server).
      - Produces a single ZIP package ready for upload via the
        Microsoft 365 Admin Center.
      - Validates against the Microsoft 365 Unified App Manifest
        (devPreview) schema.
      - Binds to Microsoft 365 Copilot Cowork (not just Microsoft Teams).
    
    -------------------------------------------------------------------
    Output Path
      Place all source files under:
        output/microsoft-financial-research-tools/
      Place the final ZIP at:
        output/microsoft-financial-research-tools.zip
    
    -------------------------------------------------------------------
    Package Structure
      microsoft-financial-research-tools/
      |-- manifest.json
      |-- color.png    (192 x 192 RGBA, Microsoft blue background)
      |-- outline.png  (32 x 32 RGBA, transparent bg, white glyph)
      `-- skills/
          |-- company-snapshot/SKILL.md
          |-- financial-trends/SKILL.md
          |-- peer-comparison/SKILL.md
          |-- risk-factor-analysis/SKILL.md
          |-- earnings-deep-dive/SKILL.md
          |-- executive-research/SKILL.md
          `-- filing-search/SKILL.md
    
    -------------------------------------------------------------------
    manifest.json  (use this canonical structure)
    agentSkills and agentConnectors MUST be top-level properties and
    MUST NOT be nested under copilotAgents.
    
    {
      "$schema": "https://developer.microsoft.com/json-schemas/teams/
                vDevPreview/MicrosoftTeams.schema.json",
      "manifestVersion": "devPreview",
      "version": "1.0.0",
      "id": "<NEW GUID v4>",
      "packageName": "com.microsoft.financial-research-tools",
      "developer": {
        "name": "Microsoft",
        "websiteUrl": "https://www.microsoft.com",
        "privacyUrl": "https://privacy.microsoft.com",
        "termsOfUseUrl": "https://www.microsoft.com/legal/terms-of-use"
      },
      "name": {
        "short": "Financial Research",
        "full": "Microsoft Financial Research Tools"
      },
      "description": {
        "short": "SEC EDGAR research skills for public-company analysis.",
        "full": "Seven skills plus the SEC EDGAR MCP connector for company
                snapshots, financial trends, peer comparison, risk-factor
                analysis, earnings deep dives, executive research, and
                full-text filing search."
      },
      "icons": { "color": "color.png", "outline": "outline.png" },
      "accentColor": "#0078D4",
      "agentSkills": [
        { "folder": "./skills/company-snapshot" },
        { "folder": "./skills/financial-trends" },
        { "folder": "./skills/peer-comparison" },
        { "folder": "./skills/risk-factor-analysis" },
        { "folder": "./skills/earnings-deep-dive" },
        { "folder": "./skills/executive-research" },
        { "folder": "./skills/filing-search" }
      ],
      "agentConnectors": [
        {
          "id": "secedgar",
          "displayName": "SEC EDGAR",
          "description": "Public SEC EDGAR data: company search, filings
            (10-K/10-Q/8-K/DEF 14A), XBRL financials, full-text search.",
          "toolSource": {
            "remoteMcpServer": {
              "mcpServerUrl": "https://secedgar.caseyjhand.com/mcp",
              "authorization": { "type": "None" }
            }
          }
        }
      ],
      "validDomains": [ "secedgar.caseyjhand.com" ]
    }
    
    -------------------------------------------------------------------
    Schema Rules
      - agentSkills and agentConnectors MUST be top-level properties.
      - Do NOT place them under copilotAgents.
      - copilotAgents only accepts declarativeAgents.
      - packageName MUST be included.
      - manifestVersion MUST be "devPreview".
      - Use the Microsoft Teams vDevPreview schema URL.
      - agentConnectors[].toolSource.remoteMcpServer.authorization.type
        MUST be "None".
      - validDomains MUST include: secedgar.caseyjhand.com
      - Generate a new GUID v4 for the id.
    
    -------------------------------------------------------------------
    SKILL.md Frontmatter  (every skill must use this)
    ---
    name: <kebab-case folder name>
    description: |
      <2-4 sentence description>
      Use when the user asks:
      "<trigger phrase 1>"
      "<trigger phrase 2>"
      "<trigger phrase 3>"
    license: MIT
    metadata:
      author: Microsoft
      version: "1.0"
      cowork.category: Finance
      cowork.icon: <PascalCase Fluent UI icon>
    ---
    # <Display Name>
    ## What This Skill Does
    ## When to Use
    ## Workflow
    ## Output Format
    
    IMPORTANT: cowork.category and cowork.icon MUST be nested under
    metadata.
    
    -------------------------------------------------------------------
    Skills, Fluent icons, and trigger phrases
      company-snapshot   (icon: BuildingBank)
        - snapshot of <ticker>
        - overview of <company>
        - tell me about <company>
      financial-trends   (icon: ChartMultiple)
        - 5-year financials for <company>
        - revenue trend / how has <company> grown
      peer-comparison    (icon: ScaleFill)
        - compare A vs B / benchmark <company>
        - rank companies by revenue
      risk-factor-analysis (icon: ShieldError)
        - what are the risks for <company>
        - risk factors in <company>'s 10-K
      earnings-deep-dive (icon: DocumentBulletList)
        - analyze latest earnings / earnings recap
      executive-research (icon: People)
        - who runs <company> / leadership of <company>
        - executive compensation
      filing-search      (icon: SearchInfo)
        - find filings mentioning <phrase>
        - which companies disclosed <topic>
    
    Each skill should invoke these MCP tools:
      - secedgar_company_search
      - secedgar_get_filing
      - secedgar_get_financials
      - secedgar_search_filings
    
    -------------------------------------------------------------------
    Icons
      color.png   : 192 x 192 RGBA, Microsoft Blue (#0078D4),
                    white centered chart/document glyph.
      outline.png : 32 x 32 RGBA, transparent bg, white outline glyph.
      Generate icons using Pillow. Do NOT use external image services.
    
    -------------------------------------------------------------------
    Packaging
      Use Python's zipfile module.
      Place manifest.json at the ROOT of the ZIP.
      Generate: output/microsoft-financial-research-tools.zip
    
    -------------------------------------------------------------------
    Validation Checklist
      [ ] manifest.json is at the ZIP root
      [ ] Uses the Microsoft Teams vDevPreview schema
      [ ] manifestVersion = devPreview
      [ ] packageName is present
      [ ] New GUID v4 generated
      [ ] agentSkills is top-level
      [ ] agentConnectors is top-level
      [ ] Every skill folder exists
      [ ] Every SKILL.md contains valid metadata
      [ ] metadata.cowork.category is nested correctly
      [ ] metadata.cowork.icon is nested correctly
      [ ] color.png is 192 x 192
      [ ] outline.png is 32 x 32
      [ ] validDomains contains secedgar.caseyjhand.com
      [ ] ZIP rebuilt after latest edits
    
    -------------------------------------------------------------------
    Upload
      Upload ONLY through the Microsoft 365 Admin Center:
        Copilot > Agents > All Agents > Upload Agent
      Do NOT upload through the Teams Admin Center (lenient validation
      may register the package as a Teams-only app).
    
    -------------------------------------------------------------------
    Success Criteria
      - microsoft-financial-research-tools.zip exists.
      - All validation checks pass.
      - The plugin uploads successfully.
      - Supported On displays the Copilot icon.
      - Categories are populated.
      - SHA256 hash of the ZIP is reported.
      - A summary of the generated package is provided.
    ```
1. Verify Cowork begins processing the task, working through the **Steps** in the Workspace panel: **Setting up structure and building icons**, **Write manifest.json**, **Write seven SKILL.md files**, and **Package ZIP and validate**.

   ![](./media/n6.png)

1. Verify all four steps are complete and confirm the generated files listed under **Output**, including **m...ools.zip**, **SKILL.md**, **outline.png**, **manifest.json**, and **color.png**.

   ![](./media/n7.png)

    >**Note**: Cowork can take upto 5-10 minutes to complete the task

1. Click the **... (1)** menu next to the ZIP file in the Output section, then select **Open in OneDrive (2)**.

   ![](./media/n8.png)

1. Review the contents of the **microsoft-financial-research-tools** package, confirming **color.png**, **manifest.json**, **outline.png**, and the **skills** folder are present, then click the **Download (1)** icon.

   ![](./media/n9.png)

1. Click **Open file** under the downloaded **microsoft-financial-research-tools (1).zip** in the **Downloads** panel.

   ![](./media/n10.png)

1. Double-click the **skills** folder to open it.

   ![](./media/n11.png)

1. Review the **skills** available in the folder.

   ![](./media/n12.png)

## Task 3 - Publish the Plugin

1. Navigate to the Microsoft 365 Admin Center using the URL.

     ```
     https://admin.cloud.microsoft
     ```

1. From the **Microsoft 365 admin center** home page, click **Copilot** in the left navigation menu.

   ![](./media/n13.png)

1. Click **Settings (1)** in the left navigation menu, select **Integrated apps (2)**, then click **Upload custom apps (3)**.

   ![](./media/n14.png)

1. Confirm the **App type (1)** field is set to **Teams app**, then click **Choose File (2)** to upload the manifest ZIP file.

   ![](./media/n15.png)

1. Select the **microsoft-financial-research-tools (1)** ZIP file, then click **Open (2)**.

   ![](./media/n16.png)

1. Confirm the **Manifest file validated** message appears, then click **Next**.

   ![](./media/n17.png)

1. Verify the app details for **Financial Research** under **Apps to deploy**, then click **Next**.

   ![](./media/n18.png)

1. Select **All users (1)** under **Assign users**, then click **Next (2)**.

   ![](./media/n19.png)

1. Verify the **Apps to deploy** shows **Financial Research** and **Assigned users** shows **Entire organization**, then click **Finish deployment**.

   ![](./media/n20.png)

1. Confirm the **Deployment completed** message shows **Financial Research** as **Deployed**, then click **Done**.

   ![](./media/n21.png)

## Task 4 - Enable and Test Plugin in Cowork

1. Navigate back to **Microsoft 365 Copilot** using the URL

    ```
    https://m365.cloud.microsoft/
    ```

1. Click the **Cowork (1)** tab, select **Customize (2)**, then click the **Plugins (3)** tab and confirm **Financial Research** now appears under **Installed**, though its toggle is currently off.

   ![](./media/n22.png)

1. Click the toggle next to **Financial Research** to enable the plugin.

   ![](./media/n23.png)

1. Click **New task (1)**, enter a prompt in the task field, then click the **Send (3)** button.

    ```
    Give me a snapshot of Microsoft
    ```

   ![](./media/n24.png)

1. Confirm Cowork invokes the **Financial Research (company-snapshot)** custom skill listed under **Skills & Plugins**, and verify it pulls Microsoft's data from SEC EDGAR filings to generate the company snapshot.

   ![](./media/n25.png)

1. Review the result generated by cowork using our custom plugins and skills.

   ![](./media/n26.png)

1. Enter a **prompt (1)** in the task field, then click the **Send (2)** button.

    ```
    Show Microsoft's five-year revenue trend
    ```

   ![](./media/n27.png)

1. confirm Cowork invokes the **Secedgar get financials** skill to generate the **Microsoft Revenue - 5-Year Trend**.

   ![](./media/n28.png)

1. Review the result generated by cowork using our custom plugins and skills.

   ![](./media/n29.png)


# Lab Summary

In this lab, you:

- Enabled Microsoft 365 Copilot Cowork.

- Generated a complete Financial Research plugin package using a single
  structured AI prompt.

- Reviewed the generated manifest, seven skills, connector, and icons.

- Validated the package against the devPreview schema.

- Published the plugin through the Microsoft 365 Admin Center.

- Enabled and tested the plugin in Copilot Cowork using natural-language
  financial queries backed by live SEC EDGAR data.

