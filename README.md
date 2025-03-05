# GitHub Copilot Hacathon: Exercises for Part 1

## Copilot Chat and Copilot Edits

### Exercise 1: Slash commands, referencing files, chat participants

**Visual Studio**
- [Slash commands](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-chat-context?view=vs-2022#slash-commands)
- [File references](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-chat-context?view=vs-2022#reference)

**VS Code**
- [Slash commands](https://code.visualstudio.com/docs/copilot/copilot-chat#_slash-commands) 
- [Chat participants](https://code.visualstudio.com/docs/copilot/copilot-chat#_chat-participants)

**Steps**
1. Check which chat participants, slash commands and file reference are available in your IDE by opening the chat and typing @, # or / in the chat window.
   - Note: these are only available in the chats, not in Copilot Edits!
3. In teams familiarize yourselves with the chat participants, slash commands and file references available in your IDE, using the documentation
   - Note: Copilot extensions change rapidly and the documenation may not by up-to-date
4. Discuss within your group on how the different helpers work

### Exercixe 2: API implementation
Complete the following steps using Copilot chat, Copilot Edits, chat participants, file references, slash commands and other Copilot features.

1. Using the programming language of your choise, implement the following REST API, one API endpoint at a time. Use in-memory database for storing the data.
<img width="736" alt="image" src="https://github.com/user-attachments/assets/482fd8cf-e506-4973-9d11-ede1d86beebf" />

2. Test that the implementation works using curl
3. Generate unit tests for the API (e.g. using /setupTests and /test and make sure they are working
4. Using Copilot Edits, make a changes to the codebase that affect multiple files. Make sure that application logic, tests, schema etc are changed correctly. Examples:
   - Add versioning to the API endpoints (e.g. /api/v1/pet)
   - Change the definition of the Pet object
   - GET /pet/{id} only returns a Pet if the pet in question has the status "available"
   - Add validation of the Pet object to POST /pet
5. Inject a bug in the code and check if /fix can spot it
6. Use /explain on part of the code and see if it produces the correct explanation

Not confident with REST APIs? Implement a class with the following helper methods and unit tests for them. Perform rest the steps listed above.
- Count vowels
- Is a prime number
- Generate Fibonacci sequence up to n terms
- Count the number of lines in a file
- Check if a string is a palindrome

### Exercise 3: Repository Custom Instructions
Custom instructions is a feature that enables automatically inserting contextual details (e.g. about coding conventions, used technologies, project structure etc) to every prompt you make. Repository Custom Instructions make it possible to share the same custom instructions among your team. 

[GitHub Documentation for Custom Instructions](https://docs.github.com/en/enterprise-cloud@latest/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot?tool=visualstudio)

**Steps**
1. See the documentation linked above for help with the exercise
1. Open a project that you are currently working on in Visual Studio (or alternatively create an empty project)
1. Enabel repository custom instructions in Visual Studio according to the documentation
1. Create a custom instructions file (tip: you can use Copilot to generate content in it). Add instructions that would be relevant in your current project, e.g:
    - Project structure
    - Coding standards
    - Tool requirements (e.g. application frameworks, dependency managers, unit test frameworks)
    - Documenation practices of files/functions/methods
    - Naming conventions
    - Etc
1. Try to generate some code and see that the instructions are respected

### Exercise 4: Custom Instructions in VS Code Settings
Custom instructions can be also defined in VS Code Settings. If you define custom instructions in both the .github/copilot-instructions.md file and in settings, Copilot tries to combine instructions from both sources.

[VS Code Documentation on Custom Instructions settings](https://code.visualstudio.com/docs/copilot/copilot-customization)

1. Open settings
2. Search for "instructions" or browse to Extensions -> Copilot Chat -> Experimental
3. Click on "Edit in settings.json"
4. Add custom instructions according to the documentation
5. Try to generata some code to the pet project and see that that the instrcutions are respected

### Exercise 5: Copilot CLI
- Install the Copilot CLI tool according to the [instructions](https://docs.github.com/en/enterprise-cloud@latest/copilot/managing-copilot/configure-personal-settings/installing-github-copilot-in-the-cli)
- Authenticate to GitHub using the gh command line tool
- Try to explain and create shell commands according to the [instructions](https://docs.github.com/en/enterprise-cloud@latest/copilot/using-github-copilot/using-github-copilot-in-the-command-line)
  - Suggest how to undo the last git commit
  - Suggest how to install a specific version of nginx on Ubuntu 
  - Explain ```find /var/log -type f -name "*.log" -mtime +7 -exec gzip {} \; -exec mv {}.gz /backup/logs/ \;```

### Exercise 6: GitHub.com (requires a GitHub repository)
- Push your code to the repository on GitHub.com
- Use copilot in the browser to make questions about the code base
- Make a change to the code and open a pull request. Let Copilot generate the PR description.

