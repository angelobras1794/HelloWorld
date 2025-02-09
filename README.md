# Assignment 1: Introduction to Visual Studio Code, .NET, and GitHub

## Pre-requisites:
- **Visual Studio Code installed:** Download and install Visual Studio Code from the Visual Studio Code [website](https://code.visualstudio.com/Download).
- **.NET SDK installed:** Download and install the .NET SDK from the .NET [website](https://dotnet.microsoft.com/download).
- **GitHub account and Git installed:** Create a GitHub account if you don't already have one. You can sign up at GitHub. Additionally, install Git on your computer from the Git [website](https://git-scm.com/downloads).

## Part 1: Hello World in Visual Studio Code
1. **Objective:** Create a simple "Hello World" application using Visual Studio Code and the command line.
2. **Steps:**
   - **Open a terminal:**
     - **Windows:** Open Command Prompt or PowerShell.
     - **Mac:** Open Terminal.
   - **Create a new .NET project:**
     - Navigate to the directory where you want to create your project using the `cd` command.
     - Run `dotnet new console -o HelloWorld` to create a new console application in a folder named "HelloWorld".
   - **Open the project in Visual Studio Code:**
     - Navigate to the project directory using `cd HelloWorld`.
     - Open Visual Studio Code in the current directory by running `code .`.
   - **Write the code:**
     - In Visual Studio Code, open the `Program.cs` file.
     - Replace the existing code with the following:
       ```csharp
       using System;

       namespace HelloWorld
       {
           class Program
           {
               static void Main(string[] args)
               {
                   Console.WriteLine("Hello World!");
               }
           }
       }
       ```
   - **Run the program:**
     - In the terminal within Visual Studio Code, run `dotnet run` to compile and run your program. You should see "Hello World!" printed in the terminal.



## Part 2: Introduction to GitHub
1. **Objective:** Understand the basics of GitHub and essential Git commands to manage your code, while also managing which files to include and exclude in your Git repository.

2. **Steps:**

 - **Initialize a local Git repository:**
   1. In the terminal, navigate to your project directory if you're not already there.
   2. Initialize a Git repository by running:
      ```bash
      git init
      ```

 - **Create a `.gitignore` file:**
   1. This file will tell Git which files or directories to ignore when committing changes.
   2. In the project root, create a `.gitignore` file and open it in a text editor.
   3. Add entries for files you don't want to track. For example:
      ```plaintext
      # Ignore .NET build files
      bin/
      obj/
      *.user
      *.suo
      *.userosscache
      *.sln.docstates

      # Ignore Visual Studio Code files
      .vscode/
      ```
   4. Save and close the `.gitignore` file.

 - **Add your project files to the repository:**
   1. Stage all your project files for the initial commit by running:
      ```bash
      git add .
      ```
   2. Git will automatically ignore the files and folders specified in the `.gitignore` file.

 - **Commit your changes:**
   1. Commit the staged files with a meaningful message by running:
      ```bash
      git commit -m "Initial commit"
      ```




## Part 3: Creating and Configuring an SSH Key
1. **Objective:** Generate an SSH key and configure it on GitHub for secure authentication.
2. **Steps:**
   - **Generate an SSH key:**
     - **Windows:**
       - Open Command Prompt or PowerShell.
       - Run the following command, replacing `your_email@example.com` with your GitHub email address:
         ```sh
         ssh-keygen -t ed25519 -C "your_email@example.com"
         ```
       - Follow the prompts to save the key to the default location and **not** set a passphrase.
     - **Mac:**
       - Open Terminal.
       - Run the following command, replacing `your_email@example.com` with your GitHub email address:
         ```sh
         ssh-keygen -t ed25519 -C "your_email@example.com"
         ```
       - Follow the prompts to save the key to the default location and **not** set a passphrase.
   - **Add the SSH key to your GitHub account:**
     - Copy the SSH public key to your clipboard:
       - **Windows:**
         ```sh
         clip < ~/.ssh/id_ed25519.pub
         ```
       - **Mac:**
         ```sh
         pbcopy < ~/.ssh/id_ed25519.pub
         ```
     - Go to GitHub and log in to your account.
     - In the upper-right corner of any page, click your profile photo, then click **Settings**.
     - In the left sidebar, click **SSH and GPG keys**.
     - Click **New SSH key** or **Add SSH key**.
     - Paste your key into the "Key" field and add a descriptive title.
     - Click **Add SSH key**.

## Part 4: Working with GitHub
1. **Objective:** Practice using GitHub commands and understand the importance of making small, frequent commits.
2. **Steps:**
- **Create an account on GitHub**
    - Go to [GitHub](https://github.com) and create an account with your **University email account**

- **Create a new repository on GitHub:**
     - Go to GitHub and log in to your account.
     - Click on the "+" icon in the top right corner and select "New repository."
     - Name your repository (e.g., "HelloWorld") and click "Create repository."
   - **Link your local repository to the GitHub repository:**
     - Copy the URL of your new GitHub repository.
     - In your terminal, run `git remote add origin <repository-URL>`, replacing `<repository-URL>` with the copied URL.

 - **Push your changes to GitHub:**
   - Push your initial commit to GitHub by running:
      ```bash
      git push -u origin main
      ```
   - **Make a small change to your program:**
     - Open `Program.cs` in Visual Studio Code.
     - Change the message in the `Console.WriteLine` statement to something else (e.g., "Hello, GitHub!").
   - **Commit the change:**
     - Stage the modified file by running `git add .`.
     - Commit the change with a descriptive message by running `git commit -m "Changed greeting message"`.
   - **Push the change to GitHub:**
     - Push your commit to GitHub by running `git push`.
   - **Repeat the process:**
     - Make a few more small changes to your program (e.g., add another `Console.WriteLine` statement).
     - For each change, stage, commit, and push the changes to GitHub.

## Part 5: Working with GitClassroom

  - Go to GitHub Classroom and connect with your GitHub Account.

    1. Visit [GitHub Classroom](https://classroom.github.com/).
    2. Log in using your GitHub account if you are not already logged in.

  - Accept the assignment and press the link.

    1. Once logged in, you should see the assignment provided by your instructor.
    2. Click on the link to accept the assignment.
    3. Follow the instructions to create a repository for the assignment and begin working on it.



## Part 6: Changing the Remote Repository
1. **Objective:** Learn how to change the remote repository linked to your local repository.
2. **Steps:**
   
   - **Change the remote URL of your local repository:**
     - Copy the URL of the new GitHub repository from the assigment accespted on Classroom.
     - In your terminal, run `git remote set-url origin <new-repository-URL>`, replacing `<new-repository-URL>` with the copied URL.
   - **Push your changes to the new repository:**
     - Push your commits to the new repository by running `git push -u origin main`.

## Discussion: Importance of Small Commits
- **Objective:** Understand why making small, frequent commits is crucial in software development.
- **Explanation:**
  - **Tracking changes:** Small commits make it easier to track changes and understand the history of the project.
  - **Identifying bugs:** When a bug is introduced, small commits help in pinpointing the exact commit where the issue occurred, making it easier to fix.
  - **Collaboration:** In a team setting, small commits facilitate better collaboration by reducing the chances of merge conflicts and making code reviews more manageable.
  - **Continuous integration:** Small, incremental changes are easier to integrate and test, leading to a more stable codebase.