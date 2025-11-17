## Step 3: Building Reusable Prompts

Now that you've established instructions for assignments, you want to streamline creating new assignments.

Creating assignments is a repetitive task and involves multiple steps, a perfect scenario for a reusable prompt!

- Creating the assignment
- Updating the website configuration to load the new assignment

### 📖 Theory: Prompt Files

Prompt files (`*.prompt.md`) are reusable prompts to simplify common and useful tasks in your project. They are selected in Copilot Chat using slash commands (`/`).

They can reference other workspace files, prompt files, or instructions files by using Markdown-style links relative to the prompt file location.

Visual Studio Code will look for `*.prompt.md` files in `.github/prompts/` directory by [default](vscode://settings/chat.promptFilesLocations).

> [!TIP]
> Use prompt files to define repeatable tasks and workflows.
>
> When writing prompts focus on **WHAT** needs to be done. You can reference instructions for the **HOW**.

See the [VS Code Docs: Prompt Files](https://code.visualstudio.com/docs/copilot/copilot-customization#_prompt-files-experimental) page for more information.

### ⌨️ Activity: Create an Assignment Prompt

Now let's create a reusable prompt that automates the entire assignment creation process. This is perfect for a prompt file because creating assignments involves multiple repetitive steps that follow the same pattern every time - exactly the kind of workflow that benefits from automation.

1. Create a new file called:

   ```text
   .github/prompts/new-assignment.prompt.md
   ```

1. Add the following content to create a comprehensive assignment generation prompt:

   ```markdown
   ---
   agent: agent
   description: Create a new programming homework assignment
   argument-hint: Provide assignment details
   ---

   # Create New Programming Assignment

   Your goal is to generate a new homework assignment for the Mergington High School students.

   ## Step 1: Gather Assignment Information

   If not already provided by the user, ask what the assignment will be about.

   ## Step 2: Create Assignment Structure

   1. Create a new directory in the `assignments` folder with a unique name based on the assignment topic
   1. Create a new file in the directory named `README.md` with the structure from the [assignment-template.md](../../templates/assignment-template.md) file
   1. Fill out the assignment details in the README file
   1. (Optional) Add starter code or attachments if the assignment needs them - add these files to the same assignment folder

   ## Step 3: Update Website Configuration

   Update the assignments list in [config.json](../../config.json) website configuration file to include the new assignment. For the dueDate field, use the current date plus 7 days unless specified otherwise.
   ```

### ⌨️ Activity: Test the Assignment Prompt

1. Open Copilot Chat in VS Code and ensure you're in `Agent` mode.

1. Run your prompt by typing `/new-assignment` in the chat input. There are 2 options:

   - Type just `/new-assignment` without a description. Copilot will ask what the assignment should be about.
   - Include the topic directly: `/new-assignment Building REST APIs with FastAPI framework`

      <details>
      <summary>💡 Assignment Topic Ideas</summary>

      ```text
      Python Text Processing - working with strings, file I/O, and text manipulation
      ```

      ```text
      Data Structures in Python - lists, dictionaries, sets, and tuples
      ```

      ```text
      Python Data Visualization - using matplotlib or plotly for charts and graphs
      ```

      ```text
      Building REST APIs with FastAPI framework
      ```

      ```text
      Statistics with Python - data analysis and statistical calculations using pandas and numpy
      ```

      </details>

1. Verify the new assignment appears in the assignments list on the website preview.

   <details>
   <summary>Assignment not showing? 🔍</summary>

   Check these items:

   - Refresh the page.
   - A new directory was created in `assignments/`.
   - The `config.json` file was updated with the new assignment.

   </details>

1. Review the generated assignment content to ensure it matches your established conventions.

1. Commit and push your changes:

   - The new prompt file: `.github/prompts/new-assignment.prompt.md`
   - The generated assignment directory and files.
   - Updated `config.json` configuration.

1. Wait for Mona to prepare the next step!

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure the prompt file is in the `.github/prompts/` directory with the `.prompt.md` extension.

</details>
