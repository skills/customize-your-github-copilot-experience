## Step 2: File-Specific Instructions

With the general project instructions ready, you realize you need more specific formatting rules related to just the assignments. While your repository-wide instructions work great for general coding standards, you don't want to clutter them with detailed assignment structure requirements that get included in every chat message.

You want to make sure all your assignments follow the same pattern and structure so students have a consistent experience, but these rules should only apply when working on assignment files.

### 📖 Theory: Custom Instruction Files

Instruction files (`*.instructions.md`) provide Copilot targeted guidance for specific files or directories in your project.

Unlike repository-wide instructions that apply everywhere, these files use the `applyTo` field in the [frontmatter](https://jekyllrb.com/docs/front-matter/) using [glob syntax](https://code.visualstudio.com/docs/editor/glob-patterns) to target specific files. This automatically applies the instructions whenever Copilot works on files matching that pattern. Alternatively, you can manually attach instructions using the **Add Context** button in Copilot Chat.

Visual Studio Code will look for `*.instructions.md` files in `.github/instructions/` directory by [default](vscode://settings/chat.instructionsFilesLocations).

> [!TIP]
> Instructions should focus on **HOW** a task should be done - describing the guidelines, standards, and conventions used in that particular part of the codebase

See the [VS Code Docs: Custom Instructions](https://code.visualstudio.com/docs/copilot/copilot-customization#_custom-instructions) page for more information.

### ⌨️ Activity: Create Assignment-Specific Instructions

Now let's create targeted instructions specifically for assignment files to ensure they follow consistent structure and formatting.

1. First, let's examine the existing assignment template. Open `templates/assignment-template.md` to see the structure we want all assignments to follow.

1. Create a new file called:

   ```text
   .github/instructions/assignments.instructions.md
   ```


1. Add the following content to define assignment formatting standards. It will also ensure they are automatically applied for every chat request to Markdown (`.md`) files in `assignments` directory.

   ```markdown
   ---
   applyTo: "assignments/**/*.md"
   ---

   # Assignment Markdown Structure Guidelines

   All assignment markdown files should follow these guidelines:

   ## 1. Template Usage

   - Assignment markdown files must follow the structure in [`templates/assignment-template.md`](../../templates/assignment-template.md).
   - The assignment must be created as a `README.md` file
   - Do not remove or skip required sections from the template.

   ## 2. Section Guidance

   The section headers should reflect the structure in the template, including the exact icon usage.

   - **Title**: Replace `[Assignment Title]` with a short, descriptive name (e.g., `Python Basics`, `Loops and Conditionals`, `Functions and Modules`).
   - **Objective**: Write 1-2 sentences summarizing what the student will learn or accomplish. Focus on the main skills or concepts.
   - **Tasks**: For each task:
      - Use a specific, action-oriented task name
      - In the Description, clearly state what the student must do.
      - In Requirements, use bullet points to list the expected outcomes or features. Be specific and measurable
      - Provide example input/output in code blocks if helpful.

   Do not include extra sections unless explicitly specified.
   ```

### ⌨️ Activity: Test the Assignment Instructions

1. Open the file `assignments/games-in-python/README.md` in VS Code. This assignment doesn't match all the conventions you've setup as a teacher.

1. Take a moment to review the current structure of this assignment file. Notice how it differs from the template structure you examined earlier. You can also view how it currently appears on the **Site Preview** tab.

1. With the assignment file open, ask Copilot in `Agent` mode to update the assignment structure:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Update this assignment file to follow the project standards and template structure
   > ```

1. Observe how Copilot references the general project instructions and the assignment specific instruction files.

   <img width="492" height="376" alt="screenshot of Copilot chat showing attached references" src="https://github.com/user-attachments/assets/dbf26be3-5940-4619-af4e-0a4380f16494" />

1. Compare the suggested changes with the original file structure to see how Copilot applied your instructions. Apply the suggested changes and check how the updated assignment now appears on the **Site Preview**.

1. Commit both files to the `main` branch and push your changes to GitHub.

   - `.github/instructions/assignments.instructions.md`
   - `assignments/games-in-python/README.md`

1. Wait for Mona to prepare the next step!

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you committed both files to `main` branch:
  - `.github/instructions/assignments.instructions.md`
  - `assignments/games-in-python/README.md`

</details>
