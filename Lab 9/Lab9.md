Lab 9: Securing & Orchestrating Multi-Agent AI for Zava Retail with
Microsoft Copilot Studio

## Lab scenario

Zava Retail, a fictional outdoor-gear and apparel retailer, wants a
\"Zava Concierge\" agent for customers that can answer general
storefront questions (hours, returns, product availability), and hand
off order-tracking questions to a dedicated \"Zava Order Status\"
specialist agent. Because the flow touches order data, it must be
secured: only signed-in Zava customers can check order status, risky
topics are blocked, and responses are moderated.

## Learning objectives

By the end of this lab, you will be able to:

- Create a Copilot Studio agent and define a topic with instructions.

- Connect a second specialist agent so the orchestrator can delegate
  tasks to it.

- Apply baseline security controls: authentication, blocked/sensitive
  topics, and content moderation.

- Test the multi-agent conversation end-to-end.

## Lab prerequisites

- Access to [Copilot Studio](https://copilotstudio.microsoft.com/) with
  a Power Platform environment (a trial environment works).

- Maker/Environment Admin permissions in that environment.

- Nothing to install --- everything happens in the browser.

## Exercise 1- Create the orchestrator agent 

1.  Navigate to
    +++[https:/copilotstudio.microsoft.com](https://m365.cloud.microsoft/chat/)+++
    to open Microsoft 365 Copilot.

2.  Sign in with your Microsoft 365 Copilot account credentials.

![](media/media/image.png){width="4.75in" height="3.7604166666666665in"}

1.  Enter the password and click **Yes**, to stay signed in.

![](media/media/image2.png){width="4.5in" height="3.6354166666666665in"}

2.  After successful login, you will see **Copilot Studio** home page.

> ![](media/media/image3.png){width="6.5in"
> height="3.4166666666666665in"}

3.  Navigate to Agents\> **+Create blank agent.**\
    ![](media/media/image4.png){width="6.25in"
    height="1.6458333333333333in"}

4.  Paste the name as +++**Zava Concierge**.+++

> ![](media/media/image5.png){width="6.5in"
> height="2.6041666666666665in"}

5.  Paste the **Description** as-

+++Answers general storefront questions for Zava Retail customers, such
as store hours, returns policy, and outdoor-gear product availability.
Delegates order-tracking questions to the Zava Order Status agent.+++\
![](media/media/image6.png){width="6.5in" height="3.6145833333333335in"}

6.  Click Publish.\
    ![](media/media/image7.png){width="6.25in"
    height="2.4791666666666665in"}

## Exercise 2-Give it retail knowledge

1.  Go to the Knowledge tab → Add knowledge.\
    ![](media/media/image8.png){width="6.25in"
    height="5.354166666666667in"}![](media/media/image9.png){width="6.25in"
    height="4.416666666666667in"}

2.  Upload the txt. file with a mock Zava Retail returns policy (e.g.,
    \"Zava Retail accepts returns within 60 days with a receipt; hiking
    boots and clearance items are final sale.\"). Click Add to Agent.

![](media/media/imagea.png){width="6.25in" height="4.34375in"}

## Exercise 3 -Create the specialist agent

1.  Navigate to Copilot Studio home page.

2.  Go to **Agents\>+Create a blank agent.**\
    ![](media/media/imageb.png){width="6.25in"
    height="1.6458333333333333in"}

3.  Paste the name as +++**Zava Order Status+++**

> Paste the **description** as-\
> \
> +++L*ooks up the status of a Zava Retail customer\'s order given an
> order number. Only answers order-status questions.*+++\
> ![](media/media/imagec.png){width="6.5in"
> height="5.583333333333333in"}

4.  Go to Topics → + Add a topic → From blank.\
    ![](media/media/imaged.png){width="6.25in"
    height="3.4791666666666665in"}

5.  Paste the Trigger phrases as\
    +++ \"where is my order\", \"track my order\", \"order status\"+++\
    ![](media/media/imagee.png){width="6.25in"
    height="4.458333333333333in"}

6.  Click +Ask a Question to add a question node asking for the order
    number.\
    ![](media/media/imagef.png){width="6.25in" height="4.8125in"}

7.  Paste the question- +++What is my order number?+++\
    And Identify response as- User's Entire Response.\
    ![](media/media/image10.png){width="6.25in"
    height="5.291666666666667in"}

8.  Rename the variable as +++Order Number+++\
    ![](media/media/image11.png){width="6.25in"
    height="5.291666666666667in"}

9.  Add a Message node that returns a mock status\
    Paste this in the message box- +++Zava order {OrderNumber} is out
    for delivery.+++\
    Note: Use {x} to insert variable Order Number.\
    ![](media/media/image12.png){width="6.25in"
    height="3.84375in"}![](media/media/image13.png){width="6.25in"
    height="4.897836832895888in"}

10. Rename the trigger as +++Order Status+++ and Click Save.\
    ![](media/media/image14.png){width="6.25in"
    height="5.166666666666667in"}

11. Save and Publish this agent (top right).\
    ![](media/media/image15.png){width="6.25in"
    height="3.4791666666666665in"}

## Exercise 4- Connect the specialist to the orchestrator

1.  Switch back to the **Zava Concierge** agent.

2.  Go to Agents (or Tools → Agents, depending on your tenant\'s UI) → +
    Add an agent.\
    ![](media/media/image16.png){width="6.25in"
    height="5.583333333333333in"}

3.  Select Zava Order Status from the list of agents in your
    environment.\
    ![](media/media/image17.png){width="6.25in"
    height="4.416666666666667in"}

4.  Paste the description as:\
    +++Use this agent only for Zava order tracking and delivery status
    questions.+++\
    Select Add & Configure.\
    ![](media/media/image18.png){width="6.25in" height="4.28125in"}5.
    Click Save.\
    ![](media/media/image19.png){width="6.25in"
    height="4.927083333333333in"}

## Exercise 5 --- Apply security controls 

### Task 1- Require sign-in (authentication)

1.  Go to **Settings** \>**Security** on the **Zava Concierge** agent.\
    ![](media/media/image1a.png){width="6.25in" height="2.5625in"}

2.  Under **Authentication**, choose **Authenticate with Microsoft** (or
    your Entra ID tenant) instead of \"No authentication.\"\
    ![](media/media/image1b.png){width="6.25in"
    height="2.9583333333333335in"}Note: If the setting is selected by
    default, you wont need to save it again.

### 

### Task 2- Turn on content moderation

1.  Navigate to **Settings\>Generative AI.**\
    ![](media/media/image1c.png){width="6.25in"
    height="3.3020833333333335in"}

2.  Set the **content moderation** level to **Medium** or **High**.
    Click **Save**.\
    ![](media/media/image1d.png){width="6.25in"
    height="3.4895833333333335in"}

> Note: This filters unsafe or manipulated inputs/outputs at both the
> orchestrator and specialist layers.

### Task 3- Add a human-handoff safety net

Add a fallback **Escalate** topic (that transfers to a human agent when
the customer asks about something outside scope (e.g., refund disputes,
account cancellation) or when confidence is low.

1.  Navigate to Topics\>Create a blank topic.\
    ![](media/media/imaged.png){width="6.25in"
    height="3.4791666666666665in"}

2.  Name the topic as +++Fallback escalate trigger+++

> Paste the trigger phrase:\
> +++This tool can handle queries like these: I need more help, this
> isnt working, can i talk to someone, escalate issue, speak to a
> human+++\
> ![](media/media/image1e.png){width="4.540262467191601in"
> height="3.8854166666666665in"}

3.  Add a message node. Paste the message:\
    +++It looks like your request is outside the scope of what I can
    assist with. Let me transfer you to a human agent for further
    help.+++

Click **Save.**

![](media/media/image1f.png){width="6.944444444444444e-3in"
height="6.944444444444444e-3in"}\
![](media/media/image20.png){width="6.5in" height="5.125in"}

## Exercise 6- Test the multi-agent flow

1.  Open the Test pane on Zava Concierge (top right chat icon).\
    ![](media/media/image21.png){width="6.25in"
    height="3.4895833333333335in"}

2.  Try: \"What\'s Zava\'s return policy?\" → should answer from the
    knowledge source.\
    ![](media/media/image22.png){width="4.3125in" height="6.25in"}

3.  Review the output:\
    ![](media/media/image23.png){width="6.25in" height="3.21875in"}

## Lab Summary

### **Lab Summary**

In this lab, you secured a retail AI agent by implementing **layered
security and governance controls** to protect customer and order
information while keeping the agent focused on its intended business
role.

By the end of the lab, you:

- **Enabled authentication** to prevent anonymous users from accessing
  sensitive retail data.

- **Configured blocked and sensitive topics** to keep the agent within
  its approved scope and prevent disclosure of restricted information.

- **Enabled content moderation** to help filter unsafe, manipulated, or
  inappropriate inputs and outputs.

- **Added human escalation** so complex, low-confidence, or out-of-scope
  requests can be routed to a human.

- **Scoped connected agents** using a least-privilege approach, ensuring
  each agent has access only to the capabilities required for its
  specific task.

**Outcome:** The retail agent is now protected through multiple layers
of **authentication, topic controls, content safety, human oversight,
and least-privilege access**, reducing the risk of data exposure and
unsafe or unauthorized agent behavior.
