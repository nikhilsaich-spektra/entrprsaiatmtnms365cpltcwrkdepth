# Lab 8: Build and Publish a Custom Microsoft 365 Copilot Cowork Plugin (Read Only)

### Estimated Duration: 20 Minutes

## Overview
Organizations can extend Microsoft 365 Copilot beyond its built-in capabilities by developing custom plugins that integrate enterprise knowledge, business processes, and external services. Using Copilot Cowork Plugins and the Model Context Protocol (MCP), developers can securely connect Microsoft 365 Copilot to external data sources, enabling users to retrieve live information and perform specialized tasks through natural language.

In this lab, you will use Microsoft Copilot Cowork to generate a complete Financial Research plugin package using a structured AI prompt. The plugin extends Microsoft 365 Copilot with financial research capabilities by connecting to the SEC EDGAR public repository through a Remote MCP Server. You will review the generated plugin components, validate the deployment package, publish the plugin through the Microsoft 365 Admin Center, and test its functionality within Copilot Cowork using natural-language financial queries. By the end of the lab, you will understand the end-to-end process of building, deploying, and using custom Copilot Cowork plugins.

>**Note:** This is a read-only lab intended to introduce the key concepts of publishing custom Microsoft 365 Copilot Cowork plugins through the Microsoft 365 Admin Center. No hands-on activities are performed, as this requires the AI Administrator role, which is not assigned to participants. Participants will gain the foundational knowledge needed to understand how plugins are generated, validated, and published.

## Objectives
After completing this lab, you will be able to:

- Explore the plugin and skills framework available in Microsoft Copilot Cowork.
- Generate a complete Microsoft 365 Copilot Cowork plugin package using a structured AI prompt.
- Review the generated plugin components, including the manifest, skills, connector configuration, and icons.
- Validate the plugin package against the Microsoft 365 Unified App Manifest (devPreview) schema.
- Publish a custom plugin through the Microsoft 365 Admin Center.
- Enable the published plugin in Microsoft Copilot Cowork.
- Test the plugin by executing natural-language financial research queries powered by the SEC EDGAR Remote MCP Server.

## Task 1 - Review Plugins and Skills in Cowork

In this task, you will explore the Plugins and Skills available in Microsoft Copilot Cowork, review the built-in capabilities, and verify that your environment is ready for custom plugin development.

1. Click the **Cowork (1)** tab, then click **New task (2)**.

   ![](./media/n1.png)

1. Click the **+ (1)** icon in the **Start a task** field, then select **Customize (2)**.

   ![](./media/n2.png)

1. On the **Plugins (1)** tab, review the installed and built-in plugins.

   ![](./media/n3.png)

1. On the **Skills** tab, confirm no skills have been added under **Your skills**, and review the **Built-in** skills available, including **PDF**, **Word**, and **Excel**.

   ![](./media/n4.png)

## Task 2 - Generate the Plugin Using Cowork

In this task, you will use Microsoft Copilot Cowork to generate a complete Financial Research plugin package from a structured AI prompt. You will review the generated plugin assets, including the manifest, skills, connector configuration, icons, and deployment package.

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

In this task, you will publish the generated Financial Research plugin through the Microsoft 365 Admin Center, making it available for Microsoft 365 Copilot users across your organization.

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

   >**Note:** If the plugin deployment does not complete successfully through the Microsoft 365 Admin Center, you can still enable the plugin manually from Microsoft 365 Copilot. Follow the below steps.

   1. Navigate to Customize → Plugins, search for **Financial Research (1)** and click on the **plugin (2)**.

      ![](./media/n21(1).png)

   2. Click on **Install**.

      ![](./media/n21(2).png)

   3. After the installation is complete, toggle the plugin to enable it for use in Cowork.

      ![](./media/n21(3).png)



## Task 4 - Enable and Test Plugin in Cowork

In this task, you will enable the published Financial Research plugin in Microsoft Copilot Cowork and validate its functionality by executing natural-language financial research queries powered by the SEC EDGAR Remote MCP Server.

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
In this lab, you explored the plugin capabilities available in Microsoft Copilot Cowork and generated a complete Financial Research plugin package using a structured AI prompt. You reviewed the generated package, including the Microsoft 365 Unified App Manifest, seven specialized skills, Remote MCP connector configuration, plugin icons, and deployment ZIP file, ensuring that the package met the required validation standards.

You then published the plugin through the Microsoft 365 Admin Center, making it available to Microsoft 365 Copilot users across the organization. After enabling the plugin in Copilot Cowork, you validated its functionality by executing natural-language financial research queries that retrieved live information from the SEC EDGAR public repository through the Remote MCP Server. This demonstrated how custom plugins can extend Microsoft 365 Copilot with specialized capabilities while securely integrating external data sources.

You have successfully built, validated, deployed, and tested a custom Microsoft 365 Copilot Cowork plugin, gaining practical experience in extending Microsoft 365 Copilot with enterprise-grade plugins powered by the Model Context Protocol (MCP).

## You have successfully completed the Lab!
