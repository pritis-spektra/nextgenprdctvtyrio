Lab 4- Build the Project Knowledge Assistant Copilot Agent with
Microsoft IQ for trusted customer success

Duration: 30 minutes

# Objective & Scenario

This lab provides hands-on experience in building intelligent Copilot
Agents using Microsoft IQ principles. You will create a
SharePoint-integrated agent with trusted knowledge boundaries, apply the
five-step customer success framework to align it with a Core Unit of
Work, and validate it through PoC testing. The lab also covers advanced
customization using Copilot Studio, including custom instructions, topic
routing, and multi-agent orchestration by connecting with a second
specialized agent.

Store associates and shift managers often lose valuable time searching
through SOPs, policy documents, and operational guidelines during busy
trading hours, slowing response times, and impacting customer service.
The Store OperationsAssistant Copilot Agent empowers frontline retail
workers with instant, contextual access to accurate store procedures in
the flow of work---helping them resolve customer queries faster, ensure
policy compliance, and keep store operations running smoothly during
peak demand.

# Exercise 1: Creating and Configuring Your Copilot Agent 

Microsoft IQ represents a unified intelligence layer that brings
contextual, work-aware AI into your everyday apps and agents. In this
part, you will create a Copilot Agent in SharePoint that is grounded in
verified, organization-specific content --- ensuring responses are both
intelligent and trustworthy.

## Task 1: Access the Agent Creation Tool 

1.  From a new browser, navigate to
    <https://m365.cloud.microsoft/chat/> 
     
 2.  Sign in with 

        - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

            ![](media/media/de1s1.png)

        - **Password:** <inject key="AzureAdUserPassword"></inject>

            ![](media/media/de1s2.png)

2. When prompted with the **Stay signed in?** dialog, select **No** to continue.

    ![](media/media/de1s3.png)

2.  Select **Apps** from the left pane and then
    select **SharePoint** once the Apps are loaded.

    ![](media/media/de2s2.png)

    ![](media/media/de2s2.0.png)

1. In SharePoint, select **Build (1)** from the left navigation pane, then under **Start building**, choose **Site (2)** to begin creating a new SharePoint site.

    ![](media/media/de2s3.png)

4.  Select **Communication site (1)** from the Select the site template page, then select a **template (2)** to be used.

    ![](media/media/de2s4.png "A screenshot of a computer AI-generated content may be incorrect.")

5. Select **Use template** to create the site using the displayed template.

    ![](media/media/de2s5.png "A screenshot of a website AI-generated content may be incorrect.")

7. On the **Set up your site** page, enter **Zava Site** in the **Site name (1)** field, verify that the **Site address (2)** is available, and then select **Create site (3)** to create the SharePoint site.

    ![](media/media/de2s6.png)

    >**Note:** If you receive the message **"The site address is available with modification"**, update the **Site address** by adding the suffix **`2 or 3`** to the end of the site name (for example, `ZavaSite2`), and then continue with the site creation process.

1. Wait until the **Your site is ready!** message appears, and then select **Go to site** to open the newly created SharePoint site.

    ![](media/media/de2s6.0.png)

    ![](media/media/dye1t1s10.png)
    
10. Download the following links and **upload** them in your SharePoint
    site:

- Zava Project Portfolio.xlsx

- Zava Customer Playbook.docx

![](media/media/image49.png){width="6.5in"
height="2.2083333333333335in"}

**Note:** *Before testing your Copilot Agent, ensure that all required
source documents (such as project updates, SOP files, product
specifications, shift handover notes, or any other referenced materials)
are uploaded to the appropriate SharePoint site libraries and folders.
The agent can only generate accurate, grounded responses from content
that exists in the site and is accessible through its configured
knowledge sources.*

## Task 2: Create a New Agent 

With your SharePoint site open and your frontline scenario selected, you
will now build the agent.

1.  Log in to Copilot Studio with your Microsoft credentials.

2.  Select +Create blank agent.\
    ![](media/media/image4a.png){width="6.25in"
    height="1.2720352143482065in"}

3.  Paste the agent name as +++Project Knowledge Assistant+++\
    Select Create.\
    ![](media/media/image52.png){width="6.25in" height="2.6875in"}

4.  Paste the Instructions as:\
    \
    [Instructions:]{.underline}\
    +++You are the project knowledge assistant for Zava Retail. ‌\
    \
    Rules:

- Answer questions using only approved knowledge sources ‌

- Always provide source citations ‌

- Clearly identify project risks ‌

- Structure responses using headings and bullet points ‌

- If information is unavailable, clearly state that ‌

- Never generate information not found in connected knowledge
  sources+++\
  \
  ![](media/media/image4b.png){width="6.25in" height="3.46875in"}\
  \
  5. Click +Add knowledge to link SharePoint document with the agent.

![](media/media/image4c.png){width="6.5in"
height="5.552083333333333in"}\
6. Paste the SharePoint site link to your ZavaSite.\
![](media/media/image53.png){width="6.5in"
height="5.489583333333333in"}8. Review the linked Knowledge site.

![](media/media/image4d.png){width="6.5in" height="5.458333333333333in"}

## Task 3: Test Your Agent 

Testing your agent validates both grounding knowledge and the quality of
its responses. This step reflects the Trust dimension of Microsoft IQ
--- agents should only surface verified, relevant information.

1.  Open the Test pane from the right-hand side pane.

![](media/media/image50.png){width="6.5in"
height="3.4583333333333335in"}

2.  In the chat field, paste the following prompt and select **Execute
    button:**\
    **+++What is the current status of Apex Financial Project+++**\
    \
    *"*![](media/media/image51.png){width="4.458333333333333in"
    height="6.25in"}

3.  Review the output:\
    ![](media/media/image4e.png){width="6.25in" height="5.84375in"}

## 

# Exercise 2: Advanced Instruction Authoring in Copilot Studio

## Task 2: Add a Topic: Out-of-Scope Redirect

Topics in Copilot Studio are rule-based conversation flows that trigger
when specific phrases or conditions are detected. You will create a
short topic that politely redirects users who ask questions outside the
agent\'s domain.

1.  In Copilot Studio, navigate to **Topics** in the upper menu bar.\
    ![](media/media/image14.png){width="6.25in"
    height="3.385429790026247in"}

2.  Select + **Add a topic \> From blank.**\
    ![](media/media/image2d.png){width="6.25in"
    height="2.9895997375328083in"}

3.  Paste the name of the topic-\
    "*Out-of-Scope Redirect*."\
    ![](media/media/image2e.png){width="6.25in"
    height="3.385419947506562in"}

4.  In the Trigger section, paste the following phrases as trigger
    phrases (one per line):

- *I need help with something else*

- *Can you help me with HR?*

- *This is not related to my work*

- *I have a different question*

> ![](media/media/image2f.png){width="6.5in" height="3.4896052055993in"}

5.  Click **+ icon** below the trigger node to add a Message node.
    Select **Send a Message**.

![](media/media/image30.png){width="6.25in"
height="5.447916666666667in"}\
![](media/media/image31.png){width="6.5in" height="5.604166666666667in"}

6.  Paste the following text in the message description box:

*\"I\'m specialized for HR & Payroll Assistant questions. For other
topics, please contact your team lead or visit the company intranet. Is
there anything else I can help you with in my area?\"*\
\
![](media/media/image32.png){width="6.5in" height="5.635416666666667in"}

7.  Click Save topic, then publish the agent again.\
    \
    ![](media/media/image33.png){width="6.25in"
    height="3.5729166666666665in"}

## Task 3: Test the agent

1.  Select **Test** from the upper navigation bar.\
    ![](media/media/image34.png){width="6.25in"
    height="3.1146052055993in"}

2.  Paste the following prompt, and select **the Execute** button-\
    "*Can you help me with
    HR?"*![](media/media/image35.png){width="6.25in"
    height="2.9687740594925636in"}

3.  Review the output:\
    \
    ![](media/media/image36.png){width="4.25in" height="6.25in"}

# Exercise 3: Designing a Multi-Agent Orchestration Pattern

Real enterprise deployments rarely rely on a single agent. Complex
workflows --- such as a procurement request that touches both inventory
data and HR approval processes --- require multiple specialized agents
working in coordination. This exercise introduces the concept of
multi-agent orchestration and has you design (and partially configure) a
handoff pattern between your primary agent and a second specialized
agent.

## Task 1: Create the Handoff Topic

You will now create a new topic in your primary agent that triggers
whenever a user asks a question outside the primary scope. This topic
will surface a handoff message and --- when the license supports it ---
redirect the user to the second agent.

1.  In Copilot Studio, navigate to **Topics**. Select **+Add a New topic
    \> From blank**.\
    ![](media/media/image2d.png){width="6.25in"
    height="2.9687685914260715in"}

2.  Paste the following information in the topic:\
    **Name**- Handoff to Secondary Agent

**Trigger phrases**:\
*\"payroll\", \"leave request\", \"HR policy\", \"annual leave\",
\"employee record\"*\
![](media/media/image17.png){width="6.25in"
height="3.3229385389326334in"}

3.  Click **+** to add a new node.\
    ![](media/media/image37.png){width="4.638861548556431in"
    height="3.9739588801399823in"}

4.  Select **Send a Message** to add a message node.\
    ![](media/media/image18.png){width="6.25in"
    height="3.3683891076115486in"}

5.  In the Message description box, paste the following information:\
    \"*That question is outside my area. I\'m connecting you to the HR &
    Payroll Agent who can help with that --- one moment please.\"*

![](media/media/image19.png){width="6.5in" height="3.5208552055993in"}

6.  Click Save and **Publish** to save the node and publish the setting
    again.\
    \
    ![](media/media/image38.png){width="6.25in" height="3.1875in"}

## Task 2: Configure the Secondary Agent

If your lab environment supports multi-agent connections, follow these
steps to create a lightweight secondary agent that handles the
out-of-scope queries.

1.  In Copilot Studio, Select **New Agent** from the left navigation
    bar.\
    ![](media/media/image6.png){width="6.25in"
    height="2.954727690288714in"}

2.  In the name section, paste the following name of the agent- **HR &
    Payroll Assistant**.\
    ![](media/media/image1c.png){width="6.23962489063867in"
    height="3.3437849956255468in"}

3.  In the Instructions field, paste the following instructions:

*You are the HR & Payroll Assistant. You handle queries specifically
related to store operations. Use only verified content from your
connected sources. Always cite source and section. If a query falls
outside your scope, say: \"That\'s outside my remit. Please contact the
appropriate team.*\
![](media/media/image39.png){width="6.5in" height="5.9375in"}

4.  In the Knowledge section, add the relevant [HR
    document](https://lodsprodmca.sharepoint.com/:f:/s/ZavaSite83/IgDF9aJMDXKzQYNYGImaIZrhAU1-t5HrDkAplqqKRSRnX8k?e=nUlcXI).
    You can download the file, save it to your **SharePoint** site, and
    paste the **URL** here. ![](media/media/image1e.png){width="6.25in"
    height="2.4583333333333335in"}

5.  Select **Publish** to publish the secondary
    agent.![](media/media/image3a.png){width="6.25in"
    height="3.489600831146107in"}

## Task 3: Add the Secondary Agent to the Primary Agent. 

1\. Go to the **Project Knowledge Assistant** Agent.\
![](media/media/image3b.png){width="6.5in"
height="2.5104166666666665in"}

2\. In the Agent section, **Select +Add.**
![](media/media/image1f.png){width="6.5in"
height="2.6875185914260715in"}

3\. Select the **HR & Payroll Assistant** from the list.\
![](media/media/image20.png){width="6.5in" height="4.8125in"}

4\. Paste the following description in the description box:\
\
*"Use this agent when users ask about HR or payroll matters, including
payslips, leave balances, salary deductions, attendance, tax forms,
employee benefits, or HR policy questions. Routes employee-related
workforce support queries to the HR & Payroll Assistant for accurate
resolution."*\
![](media/media/image21.png){width="5.135997375328084in"
height="4.4528433945756785in"}

5\. In the completion step, paste the following message to display:\
\
*"Your request relates to HR and payroll support. Transferring you now
to the HR & Payroll Assistant for accurate assistance."*\
![](media/media/image22.png){width="6.5in"
height="3.5104265091863516in"}

6\. Select **Publish** to publish the agent.\
![](media/media/image3c.png){width="6.5in"
height="3.6666983814523184in"}

## Task 4: Test the End-to-End Orchestration

With both agents published, validate the complete handoff flow using the
test scenarios below.

1.  Navigate to **Project Knowledge Assistant** agent.\
    ![](media/media/image11.png){width="6.25in"
    height="3.3125306211723533in"}

2.  Select **Test** in the upper menu bar.\
    ![](media/media/image3d.png){width="6.25in"
    height="3.5000251531058617in"}

3.  Paste the following prompt in the chat interface:\
    \
    *"What is my leave balance?"*\
    \
    ![](media/media/image3e.png){width="6.25in" height="3.5625in"}

4.  Review the output:\
    ![](media/media/image3f.png){width="6.25in"
    height="3.2395833333333335in"}![](media/media/image40.png){width="6.25in"
    height="3.2395833333333335in"}

# Lab Summary 

In this lab, you created and configured a SharePoint-grounded Project
Knowledge Assistant in Microsoft Copilot Studio, using verified
SharePoint content to ensure accurate and trusted responses. You scoped
and prioritized agent use cases, defined a Core Unit of Work, and mapped
capabilities using the Work IQ framework. You also conducted a
structured proof of concept, evaluated results for scaling
opportunities, authored advanced conditional instructions, created
out-of-scope redirects, and designed a multi-agent orchestration flow
with structured handoffs between primary and specialized agents.
