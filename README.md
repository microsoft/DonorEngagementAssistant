> [!WARNING]  
> This repository is no longer being actively maintained and will be removed from GitHub on December 31, 2025.

# Donor Engagement Assistant

Donor Engagement Assistant is a customized experience for the Microsoft Dynamics 365 Fundraising and Engagement platform to allow users of the system to create targeted email communications to donors. Based on their needs, users will interact with the Microsoft Azure OpenAI Service to create a personal letter and send it to a donor.



## Prerequisites

- Dynamics 365 Sales Enterprise
- Microsoft Cloud for Nonprofit – Fundraising and Engagement https://learn.microsoft.com/en-us/dynamics365/industry/nonprofit/fundraising-engagement-deploy-installer
- Admin access to Microsoft Power Platform, Microsoft Dynamics 365 or tenant admin



## Environment Variables

- AI Letter Generator URL: the URL of the Canvas App in the deployed environment (You can leave this blank. It will be filled in later)
- Azure OpenAI Base URL: the partial URL of a deployed model, e.g. “openai/deployments/**gpt-turbo**” (**remove all trailing slashes**), where "gpt-turbo" is the name of your Azure OpenAI deployment. 
- Azure OpenAI Host URL: the endpoint of your Azure OpenAI instance, e.g. "**myazureopenai**.openai.azure.com" (**remove all trailing slashes**), where "myazureopenai" is the name of your Azure OpenAI resource.

## Manual Solution Installation

1. Navigate to the Power Apps Portal
2. Click on Solutions in the left-hand navigation
3. Click on Import Solution in the top navigation bar
4. Click on browse and locate the unmanaged solution zip file on your computer
5. Follow the remaining prompts to import the solution

## Setting AI Letter Generator URL

1. Go to Power Apps Make Portal
2. Click on "Solutions" on the left panel.
3. Click on "Donor Engagement Assistant" from the list.
4. Click on the "OpenAI Letter Generator" elipesis menu and click on "Details". Copy the "Web link" address.
5. Click on the "AI Letter Generator URL" and paste the copied URL into the "Current Value" field.
6. Click on the "OpenAI Letter Generator". The editor will open and prompt you for the OpenAI key.
7. After setting the key, go back and save the changes.

## Usage

1. Import or create potential donors as Contacts
    -Can also create/import organizations as Accounts. The Canvas App will appeal to the Primary Contact of the Account, using their biography and email address
2. Create a Campaign and a Designation. Enter descriptions for each
3. Create an Opportunity. The following fields will be pulled into the Canvas App:
    - Potential Donor (or Primary Contact of Potential Donor)
    - Expected Amount
    - Source Campaign
    - Default Designation of the Opportunity
    - Opportunity Manager – this determines the generated email’s “From” email address
4. Open the Opportunity. A button labeled OpenAI Letter on the command bar/ribbon will open a side pane containing the Canvas App
5. Upon first execution, you will be prompted to enter credentials for the custom Azure OpenAI connector. You may also be prompted to enter credentials for the Outlook connector

## Developer Notes

- Find instructions on how to deploy Azure OpenAI [here](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/how-to/create-resource?pivots=web-portal).


## FAQ
### Should the assistant use GPT -3.5 or GPT-4?
The app was tested with GPT-3.5 

### Can the assistant use Azure Open AI?
The app functions with both OpenAI or Azure Open AI. The repo currently uses Azure OpenAI. 
[Request access to Azure OpenAI.](https://customervoice.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7en2Ais5pxKtso_Pz4b1_xUOFA5Qk1UWDRBMjg0WFhPMkIzTzhKQ1dWNyQlQCN0PWcu)

