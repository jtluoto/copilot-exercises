# copilot-exercises
Exercises for GitHub Copilot Workshop

## Custom Instrcutions
Custom instructions is a feature that enables automatically inserting contextual details (e.g. about coding conventions, used technologies, project structure etc) to every prompt you make.

[GitHub Documentation for Custom Instructions](https://docs.github.com/en/enterprise-cloud@latest/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot?tool=visualstudio)

### Exercise 1: Repository Custom Instructions
Repository Custom Instructions enable sharing the same custom instructions among your team.

1. See the documentation linked above for help with the exercise
1. Open a project that you are currently working on in Visual Studio (or alternatively create an empty project)
1. Enabel repository custom instructions in Visual Studio according to the documentation
1. Create a custom instructions file (tip: you can use Copilot to generate content in it). Add instructions that would be relevant in your current project, e.g:
    - Project structure
    - Coding standards
    - Requirements for certain tools (e.g. dependency managers)
    - Documenation of files/functions/methods
    - Naming conventions
    - Etc
1. Try to generate some code and see that the instructions are respected

### Exercise 2: Custom Instructions in VS Code Settings
Custom instructions can be also defined in VS Code Settings. If you define custom instructions in both the .github/copilot-instructions.md file and in settings, Copilot tries to combine instructions from both sources.

[VS Code Documentation on Custom Instructions settings](https://code.visualstudio.com/docs/copilot/copilot-customization)

1. Open settings
2. Search for "instructions" or browse to Extensions -> Copilot Chat -> Experimental
3. Click on "Edit in settings.json"
4. Add custom instructions according to the documentation
5. Try to generata some code and see that that the instrcutions are respected

## Copilot Chat and Edits

### Exercise 1: Slash commands, referencing files, chat participants
[Available slash commands in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-chat-context?view=vs-2022#slash-commands)
