# Lab 6- Extend Microsoft 365 Copilot Chat with a declarative HR agent using Copilot Studio and SharePoint

## Lab scenario

Zava Ltd. is a global professional services and technology solutions
company with a distributed workforce. The organization uses Microsoft
365, SharePoint, and Power Platform to manage HR operations, employee
learning, and recruitment data.

Zava is looking to enhance employee experience by enabling quick,
conversational access to HR-related information directly within
Microsoft 365 Copilot Chat. Employees frequently ask questions about HR
policies, career growth opportunities, learning pathways, and
recruitment data stored across SharePoint sites.

To address this, Zava\'s IT and HR teams decide to build a dedicated HR
agent using Microsoft Copilot Studio. This agent will be declaratively
defined, hosted inside Microsoft 365 Copilot Chat, and enriched with
organizational knowledge stored in SharePoint. The solution must be
built in a secure, isolated Power Platform environment and seamlessly
integrated into the Microsoft 365 experience.

## Lab Objective

By completing this lab, you will learn how to:

- Create and manage a dedicated Power Platform environment for agent
  development.

- Build a declarative agent using Microsoft Copilot Studio for Microsoft
  365 Copilot Chat.

- Define agent purpose, tone, and behavioral goals using natural
  language prompts.

- Choose the reasoning model that powers the agent, including newly
  available model options.

- Publish and deploy the agent into Microsoft 365 Copilot Chat.

- Create and configure a SharePoint communication site to host
  HR-related data.

- Add SharePoint-based knowledge sources to a Copilot Studio agent.

- Test the agent\'s ability to retrieve and reason over structured
  organizational data within Copilot Chat.

Govern the published agent from the Microsoft 365 admin center ---
review its data & tool access, reassign ownership, and block it if
needed.

## Exercise 1: Create SharePoint site

In this exercise, you will create a SharePoint site and upload the
sample documents there which will be used later in this lab.

1.  From a new browser, navigate to <https://m365.cloud.microsoft/chat/>
    and login with your lab credentials.\
    ![](media/media/image22.png){width="4.791666666666667in"
    height="4.621639326334209in"}

2.  Enter Temporary Access Pass.\
    ![](media/media/image23.png){width="5.544418197725284in"
    height="3.7916666666666665in"}

3.  Select Yes (or No) on the "Stay signed in?" prompt. This same
    sign-in sequence appears every time you\'re asked to log in later in
    this lab.

![](media/media/image24.png){width="4.145100612423447in"
height="3.2291666666666665in"}

4.  Select Apps from the left pane and then select SharePoint once the
    Apps are loaded.

5.  Select + Create site from the SharePoint page.

![](media/media/image25.png){width="6.458333333333333in"
height="3.6770833333333335in"}

6.  Select Communication site from the Select the site type page.

![](media/media/image26.png){width="6.458333333333333in"
height="3.6875in"}

7.  Select a template to be used (for example Standard communication),
    then select Use template.

![](media/media/image27.png){width="6.458333333333333in"
height="3.6979166666666665in"}

8.  Preview the template, then select Use template.\
    ![](media/media/image28.png){width="6.458333333333333in"
    height="3.6979166666666665in"}

9.  Enter Enterprise as the Site name and select Next.

![](media/media/image29.png){width="6.458333333333333in"
height="3.7291666666666665in"}

10. In the next screen, select Create site.\
    ![](media/media/image1b.png){width="6.25in" height="3.875in"}

11. Once created, note down the URL of this site.

![](media/media/image2a.png){width="6.458333333333333in"
height="3.65625in"}

12. Select Documents from the menu bar. Select + Create or upload →
    Files upload. Upload the following documents:

![](media/media/image2b.png){width="6.458333333333333in"
height="3.6979166666666665in"}

## Exercise 2: Creating an agent for Microsoft 365 Copilot Chat

In this exercise you are going to create a declarative agent with
Microsoft Copilot Studio and host it in Microsoft 365 Copilot Chat.

1.  Login to <https://copilotstudio.microsoft.com> using the login
    credentials.

2.  Select +Create blank agent.

![](media/media/image2c.png){width="6.458333333333333in"
height="3.6979166666666665in"}

3.  Enter the agent name and select Create.

Name - HR Advisor

![](media/media/image2d.png){width="6.5in"
height="3.7083333333333335in"}

4.  Paste the description as follows:\
    \
    +++HR Advisor is an AI-powered employee support assistant that helps
    employees quickly find answers to HR-related questions using
    information from the organizations Employee Handbook.+++\
    \
    ![](media/media/image2e.png){width="6.25in"
    height="3.548386920384952in"}

\[!Alert\] This exercise now provisions the agent shell first and layers
on description, instructions, and model choice afterward --- if you
don\'t see fields for Description/Instruction during creation, that\'s
expected; add them on the Overview tab as described above.

## Exercise 3: Adding knowledge to the agent

1.  Scroll down to the Knowledge section.\
    ![](media/media/image1c.png){width="6.25in"
    height="3.3854286964129483in"}

2.  In the SharePoint link placeholder, paste the link copied in
    Exercise 1:\
    ![](media/media/image1d.png){width="5.765944881889764in"
    height="4.21875in"}\
    ![](media/media/image1e.png){width="4.781977252843395in"
    height="3.4270833333333335in"}

3.  Preview the Knowledge source attached:\
    ![](media/media/image31.png){width="6.25in"
    height="3.5729166666666665in"}

.![](media/media/image32.png){width="6.5in" height="3.9375in"}

## Exercise 4: Governing the agent in the Microsoft 365 admin center

1.  Sign in to <https://admin.microsoft.com> with the same lab
    credentials (username, then Temporary Access Pass; select Yes if
    prompted to stay signed in).

2.  Select Agents from the left navigation, then select All agents.

![](media/media/image36.png){width="6.458333333333333in"
height="3.2708333333333335in"}

3.  Confirm the Total agents tile shows the org-wide agent count, and
    locate Agentic HR in the Registry list.

![](media/media/image37.png){width="6.458333333333333in"
height="3.3333333333333335in"}

4.  Open Agentic HR and review the tabs: Details, Users, Data & tools,
    Security, Permissions, Activity.

5.  On the Data & tools tab, confirm the agent\'s Capabilities (Can
    read: OneDrive files, SharePoint files) and that Shared Documents
    appears under Knowledge.

![](media/media/image38.png){width="6.458333333333333in"
height="5.010416666666667in"}

Note: Select Assign new owner, search for a user by name or email,
select them from the results, and select Assign.

![](media/media/image39.png){width="6.458333333333333in"
height="4.947916666666667in"}

![](media/media/image3a.png){width="6.458333333333333in"
height="5.020833333333333in"}

![](media/media/image3b.png){width="6.458333333333333in"
height="1.65625in"}

Note: Blocking the agent removes it from every user who has installed
it. Only do this at the very end of the lab if your instructor asks you
to demonstrate governance controls --- otherwise skip the Block step
above so the agent stays usable for further testing.

## Summary

In this lab, you successfully extended Microsoft 365 Copilot Chat by
creating an Agentic HR declarative agent using Microsoft Copilot Studio.
You set up a dedicated Power Platform environment, named and provisioned
an HR-focused agent, and then layered on its description, instructions,
and reasoning model --- including newly available model choices such as
Claude Sonnet 4.6 --- before publishing and integrating it into the
Microsoft 365 Copilot experience.

You also created a SharePoint communication site, uploaded HR-related
content, and connected it as a knowledge source for the agent through
the updated SharePoint knowledge dialog. You validated the solution by
querying the agent in Copilot Chat and receiving context-aware responses
sourced from SharePoint.

Finally, you reviewed how administrators govern published agents from
the Microsoft 365 admin center\'s agent registry --- inspecting data and
tool access, reassigning ownership, and blocking an agent when
necessary.

This lab demonstrates how Copilot Studio enables organizations to build
domain-specific agents that securely leverage enterprise knowledge, and
how IT admins retain oversight and control once those agents are in
employees\' hands.
