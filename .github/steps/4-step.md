## Step 4: Creating Custom Agents

Now that you have instructions, prompts, and templates working together, you want to take customization one step further. When brainstorming new assignments, you'd like a specialized chat experience that focuses purely on ideation rather than implementation.

### 📖 Theory: Custom Agents

Custom agents (`*.agent.md`) fundamentally change how Copilot behaves, creating specialized conversation experiences with specific tools and response formats, even unique personalities! They are selected from a dropdown list in the Copilot Chat interface.

Visual Studio Code will look for `*.agent.md` files in `.github/agents/` directory.

> [!TIP]
> Learn more about Custom Agents:
>
> - [VS Code Docs: Custom Agents](https://code.visualstudio.com/docs/copilot/customization/custom-agents)
> - [GitHub Docs: Custom Agents Configuration](https://docs.github.com/en/copilot/reference/custom-agents-configuration)


### ⌨️ Activity: Create an Assignment Brainstorming Custom Agent

Now let's create a specialized custom agent for brainstorming assignment ideas.

1. Create a new file called:

   ```text
   .github/agents/assignment-brainstorming.agent.md
   ```

1. Add the following content to create a focused brainstorming experience:

   ```markdown
   ---
   name: assignment-brainstorming
   description: Assignment brainstorming assistant
   tools: ["search", "fetch"]
   ---

   # 💡 Assignment Brainstorming Assistant

   **BRAINSTORM MODE ACTIVATED** 🚀

   I'm your assignment brainstorming partner for Mergington High School! I analyze your existing curriculum and suggest creative next assignments that build on what your students have already learned.

   ## My Response Style

   Every response follows this format:

   🔍 QUICK SCAN: [Brief analysis of existing assignments]
   💡 IDEA BURST: [3-5 rapid-fire suggestions]
   🎯 NEXT QUESTION: [What I need to know to help more]

   ## Rules

   - ⚡ Keep responses short
   - 🎯 Always end with a specific question
   - 💡 Focus on concepts, not details
   - 🚫 Never write assignment specs
   - 📊 Base ideas on existing curriculum gaps
   ```

### ⌨️ Activity: Test the Brainstorming Custom Agent

1. Open Copilot Chat in VS Code.

1. Select your custom agent from the agent dropdown list.

   <img width="379" height="218" alt="copilot agent: assignment brainstorming agent selected" src="https://github.com/user-attachments/assets/4effffa7-b8ef-4830-8050-9c777f9f0189" />

1. Test the custom agent with questions a teacher might ask. Notice the different response format!

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > What assignment topics are missing from my current curriculum?
   > ```

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Suggest 3 advanced Python assignments for my students.
   > ```

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > What would be a good follow-up assignment after the data analysis assignment?
   > ```

1. Try asking follow-up questions to see how the custom agent maintains its personality throughout the conversation.

1. Commit and push your changes for the new custom agent file: `.github/agents/assignment-brainstorming.agent.md`

1. Wait for Mona to give you a final review!

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure the custom agent file is in `.github/agents/` directory with the `.agent.md` extension.
- Custom agents are selected from the dropdown list at the bottom of the chat interface, not with `@` mentions.
- If the custom agent doesn't appear in the dropdown, restart VS Code or reload the window.

</details>
