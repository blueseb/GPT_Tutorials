# Tutorial: Integrating GitHub API with GPTs
This tutorial will let you connect GPTs to your Github account. For sake of semplicity we will only give access to gists to perform CRUD operations, but you can easily extend it to repository actions.

**Warning**: This tutorial will let GPT use your personal gists. If you make the GPT public *anybody will be able to modify and delete your gists* so keep it private!

## Prerequisites
- Basic understanding of GitHub and OpenAI’s GPT.
- A ChatGPT plus subscription
- A GitHub account.
- Familiarity with GitHub’s Personal Access Tokens (PATs).

## Step 1: Create a GitHub Personal Access Token
1. **Visit GitHub’s documentation**: If you don't know how to create a personal access token, there is a detailed explanation at [GitHub’s Personal Access Token page](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token).
2. **Generate New Token**: Follow the documentation until you reach the `Generate new token` button and click it.
3. **Give It a Name**: description is optional.
4. **Select Repository Access**: You don't need any repository access for this tutorial. I strongly recommend selecting `Public Repositories (read only)` unless you plan to add repository actions at a later time.
5. **Select Permissions**: This is very important, expand the `Account permissions` and ang change gists acces to `Read and Write`
6. **Generate Token**: Click `Generate token` at the bottom of the page.
7. **Copy and Secure the Token**: Ensure you copy and securely store the token; it won’t be shown again.

## Step 2: Set Up Your GPT with OpenAI
1. **Read the docs**: Go to the [OpenAI Platform](https://platform.openai.com/docs/actions).
2. **Create a New GPT**: Go to ChatGPT, click on `Explore` then `Create GPT`.
3. **Configure the GPT**: Click on the `Configure` tab and give it a name. You can use my custom instructions stored in [Gists Instructions](https://github.com/blueseb/GPT_Tutorials/blob/a8ece3e90e8ebe141617042ffd7b28262bc85966/Gists_Instructions.md) or you can experiment with your own.

## Step 3: Integrate GitHub API
1. **Add GitHub actions**: At the bototm of the `Configure` tab, click on `Create new action`
2. **Implement API Calls**: Under `Schema`, copy/paste the schema definition from [Actions_GitHub_API.yaml](https://github.com/blueseb/GPT_Tutorials/blob/main/Actions_GitHub_API.yaml)
3. **Authenticate API Calls**: under `Authentication` select `API Key` then paste PAT created in Step 1 for authenticating your GitHub API calls. Select `Bearer` and click `Save`

## Step 5: Publish it
In the upper right corner click `Save`, select `Only me` and click `Confirm`.
**Warning**: If don't select `Only me`, *anybody will be able to modify and delete your gists!*

That's it! You can now test GitHub integration by asking your GPT to read, write and delete gists in your account. new gists will be private by default but you can explicitly ask GPT to make them public.

## Conclusion
This tutorial provides a foundational approach to integrating GitHub API calls with GPTs. The integration not only enhances the capabilities of GPTs but also opens up new avenues for automating and managing tasks through GitHub.
