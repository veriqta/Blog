# Part 1B: Preparing the Local Computer

## Goal

The goal of this lesson is to prepare your computer for the three projects in Volume 1.

You will install and verify the main tools required to:

* Create website files.
* Write HTML and CSS.
* Run commands in a terminal.
* Track project changes with Git.
* Store your project source code on GitHub.
* Work with AWS from the command line.
* Create an organized local workspace.
* Open and manage the projects in Visual Studio Code.

By the end of this lesson, your computer should contain the following workspace:

```text
aws-beginner-projects/
├── static-website/
├── cloud-resume/
└── ec2-web-server/
```

You will also confirm that the following commands work:

```bash
code --version
git --version
aws --version
```

The AWS CLI is included in this lesson, but you will not connect it to your AWS account yet. AWS credentials and account authentication will be covered after the AWS account and administrative identity have been created.

---

# 1. What You Are Preparing

The three projects in this volume require several tools on your local computer.

## Project 1: Static Website

You will use your computer to:

* Create `index.html`.
* Create `style.css`.
* Create `error.html`.
* Test the website in a browser.
* Upload the files to Amazon S3.
* Update the files after deployment.

## Project 2: Cloud Resume

You will use your computer to:

* Build a resume website.
* Write a project README.
* Create a Git repository.
* Commit changes with Git.
* Push the repository to GitHub.
* Upload the public website files to Amazon S3.

## Project 3: EC2 Web Server

You will use your computer to:

* Store an EC2 private key.
* Open a terminal.
* Connect to an EC2 Linux instance through SSH.
* Run Linux commands on the remote server.
* Test the public website in a browser.

Your computer is the development and administration environment for all three projects.

---

# 2. Required Computer Specifications

You do not need an expensive computer for these projects.

A basic modern laptop or desktop computer should be sufficient.

## 2.1 Supported Operating Systems

This manual provides instructions for:

* Windows
* macOS
* Linux

Recommended versions include:

* A currently supported version of Windows
* A currently supported version of macOS
* A maintained Linux distribution

Common Linux distributions include:

* Ubuntu
* Debian
* Fedora
* Rocky Linux
* Linux Mint
* Red Hat Enterprise Linux

Some commands differ between operating systems. Use the instructions that match your computer.

---

## 2.2 Recommended Hardware

A practical minimum configuration is:

* A 64-bit processor
* 4 GB of memory
* At least 5 GB of free storage
* A keyboard
* A stable internet connection
* A screen large enough to use a browser and text editor

A more comfortable configuration is:

* 8 GB or more of memory
* 10 GB or more of free storage
* A modern multi-core processor
* A second monitor, although this is optional

You will not run large virtual machines on your local computer. The EC2 virtual server will run inside AWS.

Your local computer mainly needs to support:

* A browser
* Visual Studio Code
* Git
* AWS CLI
* A terminal
* Small HTML and CSS files

---

## 2.3 Check Whether Your Windows Computer Is 64-Bit

On Windows:

1. Open **Settings**.
2. Select **System**.
3. Select **About**.
4. Find **System type**.

You may see information similar to:

```text
64-bit operating system, x64-based processor
```

Use 64-bit installers when your computer supports them.

---

## 2.4 Check Your Available Storage

### On Windows

1. Open **File Explorer**.
2. Select **This PC**.
3. Review the available space under your main drive.

### On macOS

1. Open the Apple menu.
2. Select **System Settings** or **About This Mac**.
3. Open the storage information.

### On Linux

Run:

```bash
df -h
```

Example output:

```text
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2       100G   40G   55G  43% /
```

The `Avail` column shows available storage.

---

## Verification: Computer Readiness

Confirm that:

* Your operating system is supported and updated.
* You have administrator access when installation requires it.
* You have at least 5 GB of free storage.
* Your keyboard works correctly.
* You can download files from the internet.
* You can create folders and files on the computer.

---

# 3. Required Internet Connection

You need an internet connection throughout this volume.

The connection will be used to:

* Download software.
* Create your AWS account.
* Access the AWS Management Console.
* Access GitHub.
* Upload website files.
* Connect to an EC2 instance.
* Open your deployed websites.
* Read service documentation.
* Download software updates.

## 3.1 Recommended Connection Quality

A normal broadband, fibre, cable, mobile, or reliable Wi-Fi connection should be sufficient.

You do not need an extremely fast connection, but it should be stable.

An unstable connection can interrupt:

* Software downloads
* GitHub uploads
* S3 uploads
* AWS Console sessions
* SSH connections
* CloudFront testing

---

## 3.2 Avoid Untrusted Public Networks

Avoid performing sensitive account setup on an untrusted public Wi-Fi network.

Sensitive activities include:

* Creating your AWS account
* Entering payment details
* Signing in to AWS
* Configuring MFA
* Downloading or using private SSH keys
* Signing in to GitHub

Use a trusted home, school, work, or personal mobile connection where possible.

---

## 3.3 Test the Connection

Open your browser and confirm that several websites load.

You can also test from a terminal.

### Windows PowerShell

```powershell
Test-Connection github.com -Count 4
```

### macOS or Linux

```bash
ping -c 4 github.com
```

A failed `ping` does not always mean the website is unavailable because some networks block ping traffic.

The most important test is whether the required websites open in your browser.

---

## Verification: Internet Connection

Confirm that:

* Your browser can access websites.
* Downloads complete successfully.
* Your connection does not disconnect repeatedly.
* You are using a trusted network for account setup.
* You can access GitHub and AWS websites.

---

# 4. Required Accounts

You will need two main online accounts.

## 4.1 Email Account

You need an active email address that you can access.

It may be used for:

* AWS account verification
* AWS security notifications
* AWS billing alerts
* AWS budget alerts
* GitHub verification
* Password recovery
* MFA recovery processes
* Project notifications

Use an email address that you expect to keep for a long time.

Do not use a temporary email address.

---

## 4.2 AWS Account

You will create an AWS account in Part 1C.

The AWS account will contain:

* Your AWS identities
* Your AWS resources
* Billing information
* Account security settings
* Budget alerts
* The three project environments

Do not create multiple AWS accounts for the same beginner exercise unless you have a specific reason.

Using one account makes it easier to:

* Find your resources.
* Track costs.
* Configure security.
* Complete cleanup.
* Follow the manual.

---

## 4.3 GitHub Account

You will need a GitHub account for the Cloud Resume project.

GitHub will store:

* Your resume project source code
* Your README file
* Your Git commit history
* Your project documentation
* Portfolio evidence

Choose a professional GitHub username where possible.

Avoid usernames that include:

* Sensitive personal information
* Your full date of birth
* Private identification numbers
* Your home address
* Password-related information

You do not need to create a GitHub repository yet. That will happen during the Cloud Resume project.

---

## 4.4 Password Security

Create a different strong password for each account.

Do not reuse your:

* Email password
* AWS password
* GitHub password
* Computer login password

Use a password manager when available.

Enable multi-factor authentication on important accounts.

Never place account passwords inside:

* HTML files
* CSS files
* README files
* Git repositories
* Terminal scripts
* Screenshots
* Public notes

---

## Verification: Required Accounts

Before continuing, confirm that:

* You have access to a permanent email account.
* You can receive verification messages.
* You know which email address you will use for AWS.
* You have or will create a GitHub account.
* You have not stored passwords in project files.

The AWS account itself will be created in Part 1C.

---

# 5. Choosing a Web Browser

A web browser is required for:

* Opening the AWS Management Console.
* Using GitHub.
* Testing local websites.
* Testing S3 websites.
* Testing CloudFront websites.
* Testing the EC2 web server.
* Viewing documentation.

## 5.1 Recommended Browsers

Choose a current version of one of the following:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox
* Safari on macOS

You only need one main browser, although a second browser can be useful for troubleshooting.

---

## 5.2 Keep the Browser Updated

An outdated browser can create problems with:

* Security
* AWS Console pages
* Authentication
* Website rendering
* JavaScript features
* HTTPS connections

Use the browser’s update feature before starting.

---

## 5.3 Browser Profiles

Consider creating a separate browser profile for AWS learning.

A separate profile can help keep:

* AWS bookmarks
* GitHub sessions
* Training history
* Project tabs
* Saved links

separate from your personal browsing.

Do not allow a shared or public computer to save your AWS password.

---

## 5.4 Useful Bookmarks

After creating your accounts, useful bookmarks may include:

* AWS Management Console
* AWS Billing dashboard
* AWS documentation
* GitHub
* Your project repository
* Your CloudFront domain
* Your S3 website endpoint

Do not bookmark temporary URLs that expose credentials or sensitive tokens.

---

## 5.5 Browser Developer Tools

Modern browsers include developer tools.

You may use them to inspect:

* HTML
* CSS
* Network requests
* Missing files
* Browser errors
* Page layout

Common shortcuts include:

### Windows and Linux

```text
F12
```

or:

```text
Ctrl + Shift + I
```

### macOS

```text
Command + Option + I
```

You will use browser developer tools later when troubleshooting website styling and missing files.

---

## Verification: Browser

Confirm that:

* The browser opens correctly.
* It is updated.
* JavaScript is enabled.
* Downloads are allowed.
* Pop-up restrictions do not prevent required AWS sign-in pages.
* You can open a local HTML file.

---

# 6. Installing Visual Studio Code

## 6.1 What Is Visual Studio Code?

Visual Studio Code, commonly called **VS Code**, is a code editor.

You will use it to:

* Create project folders.
* Write HTML.
* Write CSS.
* Write Markdown.
* View the project structure.
* Use an integrated terminal.
* Review Git changes.
* Open multiple project files.

VS Code is different from the full Visual Studio development environment.

For these projects, install **Visual Studio Code**.

The official VS Code installer supports Windows, macOS, and common Linux package formats. On Windows, its standard installer can add the `code` command to the system path, while macOS users can install the application and separately enable the shell command when required.

---

# 7. Install Visual Studio Code on Windows

## Step 1: Download the Installer

Open the official Visual Studio Code download page.

Choose the Windows version that matches your computer.

For most modern Windows computers, choose the 64-bit User Installer.

---

## Step 2: Open the Installer

Open the downloaded file.

The filename may look similar to:

```text
VSCodeUserSetup-x64-version.exe
```

The exact version number changes over time.

---

## Step 3: Accept the Licence Agreement

Read the licence terms.

Select the option to accept the agreement, then continue.

---

## Step 4: Review the Installation Location

The default User Setup location is usually suitable.

The Windows User Setup generally installs VS Code within the current user’s profile rather than making it available to every Windows user.

---

## Step 5: Select Additional Tasks

When the installer displays additional options, consider enabling:

* Add “Open with Code” to the file context menu.
* Add “Open with Code” to the directory context menu.
* Register Code as an editor for supported file types.
* Add Visual Studio Code to PATH.

Adding VS Code to PATH allows you to run:

```powershell
code .
```

from PowerShell or another terminal.

---

## Step 6: Complete the Installation

Select **Install**.

Wait until the installation finishes.

Open Visual Studio Code.

---

## Step 7: Restart PowerShell

If PowerShell was open during installation, close and reopen it.

Environment changes such as adding `code` to PATH may not appear in terminals that were already running. The official Windows guidance recommends restarting the console after installation before testing `code .`.

---

## Step 8: Verify the Installation

Open PowerShell and run:

```powershell
code --version
```

Example output:

```text
1.xx.x
commit-information
x64
```

The version will depend on the installed release.

You can also launch VS Code by running:

```powershell
code
```

---

## Windows Verification

Confirm that:

* VS Code appears in the Start menu.
* VS Code opens.
* `code --version` returns a version.
* You can create a new text file.
* You can close and reopen VS Code.

---

# 8. Install Visual Studio Code on macOS

## Step 1: Download the macOS Installer

Download the current `.dmg` file for your Mac.

Choose the version that matches the processor where necessary:

* Apple silicon
* Intel processor
* Universal build, when offered

---

## Step 2: Open the Disk Image

Open the downloaded `.dmg` file.

A window should display the Visual Studio Code application.

---

## Step 3: Move VS Code to Applications

Drag:

```text
Visual Studio Code.app
```

into the **Applications** folder.

This is the standard installation method documented for macOS.

---

## Step 4: Open Visual Studio Code

Open:

```text
Applications → Visual Studio Code
```

You can also use Spotlight:

1. Press `Command + Space`.
2. Type `Visual Studio Code`.
3. Press Enter.

The first launch may display a macOS security confirmation.

Confirm that you want to open the application.

---

## Step 5: Install the `code` Shell Command

The `code` command may not be available automatically on macOS.

Inside Visual Studio Code:

1. Open the Command Palette.
2. Use:

```text
Command + Shift + P
```

3. Search for:

```text
Shell Command: Install 'code' command in PATH
```

4. Select the command.
5. Close and reopen Terminal.

---

## Step 6: Verify the Installation

Open Terminal and run:

```bash
code --version
```

Then test:

```bash
code
```

VS Code should open.

---

## macOS Verification

Confirm that:

* VS Code is inside Applications.
* VS Code opens.
* The `code` shell command has been installed.
* `code --version` returns a version.
* Terminal can open VS Code.

---

# 9. Install Visual Studio Code on Linux

VS Code offers installation packages for common Linux systems, including `.deb` and `.rpm` packages.

Use the method appropriate for your distribution.

---

## 9.1 Ubuntu, Debian, and Linux Mint

Download the `.deb` package.

Open a terminal in the folder containing the download.

Install it with:

```bash
sudo apt install ./code_*.deb
```

The exact filename may contain the current version and processor architecture.

You can also install a specific downloaded file:

```bash
sudo apt install ./code_1.xx.x_amd64.deb
```

Replace the example filename with the actual downloaded filename.

---

## 9.2 Fedora, Rocky Linux, or Related Systems

Download the `.rpm` package.

Install it with:

```bash
sudo dnf install ./code-*.rpm
```

On systems using `yum`, use:

```bash
sudo yum install ./code-*.rpm
```

---

## 9.3 Open Visual Studio Code

Run:

```bash
code
```

You may also find Visual Studio Code in the desktop application menu.

---

## 9.4 Verify the Installation

Run:

```bash
code --version
```

---

## Linux Verification

Confirm that:

* The correct package type was used.
* Installation completed without package errors.
* VS Code opens.
* `code --version` works.
* Your user can create and save a file.

---

# 10. Visual Studio Code First-Time Setup

When VS Code opens, you may see a welcome screen.

You do not need to install many extensions yet.

## 10.1 Choose a Theme

Select a light or dark theme according to your preference.

The theme does not affect the code.

---

## 10.2 Understand the Main Areas

The VS Code window contains several important areas.

### Activity Bar

Usually displayed on the left.

It provides access to:

* Explorer
* Search
* Source Control
* Run and Debug
* Extensions

### Explorer

Displays project folders and files.

### Editor

Displays the file currently being edited.

### Status Bar

Displays information about the current file and workspace.

### Integrated Terminal

Allows you to run terminal commands without leaving VS Code.

Open it through:

```text
Terminal → New Terminal
```

Common keyboard shortcut:

```text
Ctrl + `
```

On macOS, the shortcut may also use the backtick key with Control.

---

## 10.3 Do Not Install Unnecessary Extensions

Extensions can add useful features, but too many can:

* Slow the editor.
* Create confusing suggestions.
* Change formatting unexpectedly.
* Introduce security risks.
* Distract beginners.

For these projects, VS Code’s built-in HTML, CSS, Markdown, terminal, and Git support is enough to begin.

---

## Verification: Visual Studio Code

Create a temporary file:

1. Select **File**.
2. Select **New Text File**.
3. Type:

```text
Visual Studio Code is ready.
```

4. Save the file temporarily.
5. Close it.

Confirm that editing and saving work.

---

# 11. Installing Git

## 11.1 What Is Git?

Git is a distributed version control system.

It tracks changes made to files over time.

Git allows you to:

* Create a repository.
* See changed files.
* Stage selected changes.
* Create commits.
* Review project history.
* Return to earlier versions.
* Connect a local project to GitHub.

Git and GitHub are related, but they are not the same.

### Git

Git is the version control software installed on your computer.

### GitHub

GitHub is an online platform that can host Git repositories.

You can use Git without GitHub.

You will use both during the Cloud Resume project.

---

# 12. Install Git on Windows

## Step 1: Download Git for Windows

Download the maintained Windows installer from the official Git project.

The current release changes over time, so do not depend on a version number printed in an older manual. The official Git download page provides the current maintained Windows build.

---

## Step 2: Open the Installer

The filename may look similar to:

```text
Git-version-64-bit.exe
```

Open it.

Approve the Windows security prompt when appropriate.

---

## Step 3: Review the Installation Options

Git for Windows presents several configuration screens.

For a beginner, the default options are normally suitable.

Important selections may include:

* Installation directory
* Components
* Default editor
* Initial branch behaviour
* PATH environment configuration
* HTTPS transport
* Line-ending behaviour
* Terminal emulator
* Credential helper

---

## Step 4: Choose an Editor

You may select Visual Studio Code as Git’s default editor if it appears as an option.

Otherwise, keep the default and configure VS Code later.

---

## Step 5: Configure PATH

Select an option that allows Git to be used from:

* Git Bash
* PowerShell
* Command Prompt
* Other supported tools

A common installer choice is similar to:

```text
Git from the command line and also from third-party software
```

This makes the `git` command available outside Git Bash.

---

## Step 6: Complete the Installation

Continue with the recommended defaults.

Install Git.

Close and reopen PowerShell after installation.

---

## Step 7: Verify Git

Run:

```powershell
git --version
```

Example:

```text
git version 2.xx.x.windows.x
```

The exact version will differ.

---

## Step 8: Open Git Bash

Git for Windows normally includes Git Bash.

Open the Start menu and search for:

```text
Git Bash
```

Run:

```bash
git --version
```

Git should work in both Git Bash and PowerShell when PATH was configured correctly.

---

# 13. Install Git on macOS

There are several ways to install Git on macOS.

## Method 1: Apple Command Line Tools

Open Terminal and run:

```bash
git --version
```

If Git is not installed, macOS may ask whether you want to install the command-line developer tools.

Follow the displayed instructions.

After installation, run:

```bash
git --version
```

again.

---

## Method 2: Official Git Installer

You can use an installer provided through the official Git download guidance.

Follow the installer instructions and reopen Terminal afterward.

---

## Method 3: Homebrew

Homebrew is a package manager for macOS.

Use this method only when Homebrew is already installed and you understand how it is managed.

Run:

```bash
brew install git
```

Then verify:

```bash
git --version
```

Homebrew is not required for this volume.

---

# 14. Install Git on Linux

Git is available through the package manager of most Linux distributions.

## Ubuntu, Debian, and Linux Mint

Update the package list:

```bash
sudo apt update
```

Install Git:

```bash
sudo apt install git -y
```

Verify:

```bash
git --version
```

---

## Fedora

Install Git:

```bash
sudo dnf install git -y
```

Verify:

```bash
git --version
```

---

## Rocky Linux or Red Hat-Based Systems

Use:

```bash
sudo dnf install git -y
```

On an older system that still uses `yum`:

```bash
sudo yum install git -y
```

Verify:

```bash
git --version
```

---

# 15. Configure Your Git Identity

Git records an author name and email address in commits.

Configure them after installation.

Replace the example information with your own details.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Example:

```bash
git config --global user.name "Ann"
git config --global user.email "ann@example.com"
```

Use the email address you intend to associate with your Git activity.

Do not copy the example address literally.

---

## 15.1 Verify the Git Configuration

Run:

```bash
git config --global user.name
```

Then:

```bash
git config --global user.email
```

You can also view the full global configuration:

```bash
git config --global --list
```

Example output:

```text
user.name=Your Name
user.email=your-email@example.com
```

---

## 15.2 Configure VS Code as the Git Editor

Optional:

```bash
git config --global core.editor "code --wait"
```

The `--wait` option tells Git to wait until the VS Code editor window or file is closed before continuing.

Verify:

```bash
git config --global core.editor
```

Expected result:

```text
code --wait
```

---

## Verification: Git Installation

Confirm that:

* `git --version` works.
* Git is available from your normal terminal.
* Your Git name is configured.
* Your Git email is configured.
* You understand that Git is installed locally.
* You understand that GitHub is an online repository platform.

Do not create a repository yet. You will do that during the Cloud Resume project.

---

# 16. Installing the AWS CLI

## 16.1 What Is the AWS CLI?

The AWS Command Line Interface is a tool for managing AWS services from a terminal.

Instead of selecting buttons in the AWS Console, you can type commands.

Examples include:

```bash
aws s3 ls
```

```bash
aws ec2 describe-instances
```

```bash
aws sts get-caller-identity
```

These commands will not work against your account until authentication has been configured.

AWS recommends using AWS CLI version 2 for current installations. Its official installer documentation provides supported installation and update methods for Windows, macOS, and Linux.

---

## 16.2 Why Install the AWS CLI Now?

The first projects can be completed mostly in the AWS Console.

However, installing the CLI now allows you to:

* Become familiar with command-line tools.
* Verify the local environment.
* Use commands in later exercises.
* Learn how automation differs from console work.
* Prepare for advanced AWS projects.

You will install it now but configure account access later.

---

# 17. Install AWS CLI Version 2 on Windows

## Step 1: Download the Windows Installer

Download the official AWS CLI version 2 MSI installer for Windows.

Use the 64-bit installer on a normal modern 64-bit computer.

---

## Step 2: Open the Installer

Open the downloaded `.msi` file.

The filename is commonly:

```text
AWSCLIV2.msi
```

---

## Step 3: Follow the Installation Wizard

Proceed through the installer.

Accept the appropriate options and complete the installation.

---

## Step 4: Close and Reopen PowerShell

If PowerShell was already running, close it.

Open a new PowerShell window.

---

## Step 5: Verify the Installation

Run:

```powershell
aws --version
```

Example output:

```text
aws-cli/2.x.x Python/3.x.x Windows/...
```

The exact version information will change.

---

## Step 6: Locate the Command

Optional:

```powershell
Get-Command aws
```

This displays the command location.

You may see a path similar to:

```text
C:\Program Files\Amazon\AWSCLIV2\aws.exe
```

---

# 18. Install AWS CLI Version 2 on macOS

AWS provides a graphical package installer for macOS.

## Step 1: Download the macOS Package

Download the official AWS CLI version 2 package.

The downloaded file is commonly named:

```text
AWSCLIV2.pkg
```

---

## Step 2: Open the Package

Open the `.pkg` file.

Follow the installation wizard.

You may need to enter the password for an administrator account.

---

## Step 3: Complete the Installation

Allow the installer to finish.

Close and reopen Terminal.

---

## Step 4: Verify the Installation

Run:

```bash
aws --version
```

Optional:

```bash
which aws
```

The `which` command displays the location of the executable found in your shell path.

---

# 19. Install AWS CLI Version 2 on Linux

The commands depend on the processor architecture.

Most desktop Linux computers use `x86_64`.

Some computers use ARM64.

## 19.1 Check the Architecture

Run:

```bash
uname -m
```

Possible results include:

```text
x86_64
```

or:

```text
aarch64
```

---

## 19.2 Install Required Tools

You need tools capable of downloading and extracting the installer.

### Ubuntu or Debian

```bash
sudo apt update
sudo apt install curl unzip -y
```

### Fedora or Related Systems

```bash
sudo dnf install curl unzip -y
```

---

## 19.3 Install on x86_64 Linux

Download the installer:

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```

Extract it:

```bash
unzip awscliv2.zip
```

Install it:

```bash
sudo ./aws/install
```

---

## 19.4 Install on ARM64 Linux

Download the ARM64 installer:

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-aarch64.zip" -o "awscliv2.zip"
```

Extract it:

```bash
unzip awscliv2.zip
```

Install it:

```bash
sudo ./aws/install
```

These package URLs and installer methods are maintained in the official AWS CLI version 2 installation documentation.

---

## 19.5 Verify the Installation

Run:

```bash
aws --version
```

Optional:

```bash
which aws
```

---

## 19.6 Remove the Downloaded Installer Files

After a successful installation:

```bash
rm -rf aws
rm awscliv2.zip
```

Be careful when using `rm -rf`.

Confirm that you are deleting only the extracted AWS installer folder.

---

# 20. Verify the AWS CLI Installation

Run:

```bash
aws --version
```

A successful result starts with something similar to:

```text
aws-cli/2
```

This confirms that AWS CLI version 2 is installed.

---

## 20.1 Test the Help System

Run:

```bash
aws help
```

The command may open a help viewer.

Press:

```text
q
```

to exit when required.

You can also run:

```bash
aws s3 help
```

This displays help related to Amazon S3 commands.

---

## 20.2 Do Not Configure Credentials Yet

Do not run `aws configure` with permanent access keys during this lesson.

Account access will be addressed after:

* The AWS account is created.
* The root user is secured.
* MFA is enabled.
* The administrative identity is created.
* The appropriate authentication method is chosen.

AWS CLI configuration can store settings such as a default Region and output format. It can also use different authentication methods, including IAM Identity Center in supported organizational environments.

For now, only confirm that the command is installed.

---

## 20.3 Expected Error Before Authentication

A command such as:

```bash
aws sts get-caller-identity
```

may return an error because credentials have not been configured.

An error similar to this is expected:

```text
Unable to locate credentials
```

This does not mean the AWS CLI installation failed.

It means:

* The `aws` program exists.
* The command started.
* No AWS identity has been configured yet.

---

## Verification: AWS CLI

Confirm that:

* `aws --version` works.
* The output shows AWS CLI version 2.
* `aws help` opens the help system.
* You have not entered root-user credentials.
* You have not created unnecessary access keys.
* You understand that installation and authentication are separate steps.

---

# 21. Understanding Terminals

## 21.1 What Is a Terminal?

A terminal is a text-based environment where you enter commands.

A graphical interface lets you use:

* Buttons
* Windows
* Menus
* Icons

A command-line interface lets you perform actions by typing commands.

AWS describes a CLI as a mechanism for interacting with an operating system or software through typed commands.

Example:

```bash
mkdir aws-beginner-projects
```

This command asks the operating system to create a directory.

---

## 21.2 Terminal, Shell, and Command-Line Interface

These words are related but not identical.

### Terminal

The application window where you type and view command output.

### Shell

The program that interprets your commands.

Examples include:

* PowerShell
* Bash
* Zsh

### Command-Line Interface

A text-based way to interact with a program.

For example, the AWS CLI provides commands beginning with:

```text
aws
```

---

## 21.3 Command Structure

A command may contain:

```text
command option argument
```

Example:

```bash
mkdir static-website
```

Breakdown:

```text
mkdir
└── Command used to create a directory

static-website
└── Name of the directory to create
```

Another example:

```bash
git commit -m "Create initial project"
```

Breakdown:

```text
git
└── Program

commit
└── Git operation

-m
└── Option for supplying a message

"Create initial project"
└── Commit message
```

---

## 21.4 The Current Working Directory

The current working directory is the folder where the terminal is currently operating.

When you run:

```bash
mkdir test-folder
```

the new folder is created inside the current working directory.

You must always know where your terminal is before running file commands.

---

## 21.5 Display the Current Location

### Windows PowerShell

```powershell
Get-Location
```

PowerShell also supports:

```powershell
pwd
```

### macOS or Linux

```bash
pwd
```

The `pwd` command means **print working directory**.

Example:

```text
/home/ann
```

or:

```text
C:\Users\Ann
```

---

## 21.6 List Files and Folders

### Windows PowerShell

```powershell
Get-ChildItem
```

Short form:

```powershell
ls
```

or:

```powershell
dir
```

### macOS or Linux

```bash
ls
```

Detailed listing:

```bash
ls -la
```

---

## 21.7 Change Directory

Use:

```bash
cd folder-name
```

Example:

```bash
cd aws-beginner-projects
```

Move to the parent directory:

```bash
cd ..
```

---

## 21.8 Clear the Terminal

### PowerShell

```powershell
Clear-Host
```

Short form:

```powershell
cls
```

### macOS or Linux

```bash
clear
```

---

## 21.9 Stop a Running Command

Use:

```text
Ctrl + C
```

This usually interrupts the current command.

It does not copy text inside most terminals.

---

## 21.10 Command History

Use the Up and Down arrow keys to review earlier commands.

This is useful when:

* Correcting a typo.
* Repeating a command.
* Reviewing what you entered.

Read the command before pressing Enter again.

---

# 22. Opening PowerShell on Windows

PowerShell is the recommended Windows terminal for this volume.

## Method 1: Start Menu

1. Open the Start menu.
2. Search for:

```text
PowerShell
```

3. Open **Windows PowerShell** or the current PowerShell application available on your system.

---

## Method 2: Windows Terminal

Some Windows systems include Windows Terminal.

1. Open the Start menu.
2. Search for:

```text
Terminal
```

3. Open Windows Terminal.
4. Select a PowerShell tab.

Windows Terminal is an application that can host different shells, including PowerShell.

---

## Method 3: Open PowerShell in a Folder

In File Explorer:

1. Open the required folder.
2. Click the address bar.
3. Type:

```text
powershell
```

4. Press Enter.

PowerShell should open in that folder.

Depending on your Windows version, you may also right-click inside the folder and select an option such as:

```text
Open in Terminal
```

---

## Verify PowerShell

Run:

```powershell
Get-Location
```

Then:

```powershell
Get-ChildItem
```

Confirm that the commands return your current location and its contents.

---

# 23. Opening Terminal on macOS

## Method 1: Spotlight

1. Press:

```text
Command + Space
```

2. Type:

```text
Terminal
```

3. Press Enter.

---

## Method 2: Applications

Open:

```text
Applications → Utilities → Terminal
```

---

## Verify Terminal

Run:

```bash
pwd
```

Then:

```bash
ls
```

---

## Default macOS Shell

Recent versions of macOS commonly use Zsh as the default interactive shell.

For the basic commands in this volume, Bash and Zsh behave similarly.

Commands such as these work in both:

```bash
pwd
ls
cd
mkdir
```

---

# 24. Opening Terminal on Linux

The exact method depends on the distribution and desktop environment.

## Method 1: Keyboard Shortcut

Many Linux desktop environments support:

```text
Ctrl + Alt + T
```

---

## Method 2: Application Menu

Open the application menu and search for:

```text
Terminal
```

Possible application names include:

* Terminal
* GNOME Terminal
* Konsole
* Xfce Terminal

---

## Method 3: File Manager

Some file managers provide an option such as:

```text
Open in Terminal
```

This opens the terminal in the selected directory.

---

## Verify Terminal

Run:

```bash
pwd
```

Then:

```bash
ls -la
```

---

# 25. Choosing Where to Store the Projects

Create the workspace somewhere easy to find.

Suitable locations include:

* Your Documents folder
* A dedicated Projects folder
* Your home directory

Avoid creating the workspace inside:

* A temporary downloads folder
* A system directory
* A restricted administrator directory
* The Git program installation directory
* The VS Code installation directory
* A public shared folder
* A folder you frequently delete

---

## Recommended Location

### Windows

Example:

```text
C:\Users\YourName\Documents\aws-beginner-projects
```

### macOS

Example:

```text
/Users/YourName/Documents/aws-beginner-projects
```

### Linux

Example:

```text
/home/yourname/aws-beginner-projects
```

You may create the workspace in another location, but remember where it is stored.

---

# 26. Create the Local Project Workspace

## 26.1 Windows PowerShell Method

Open PowerShell.

Move to your Documents folder:

```powershell
cd $HOME\Documents
```

Create the main folder:

```powershell
mkdir aws-beginner-projects
```

Enter it:

```powershell
cd aws-beginner-projects
```

Create the three project folders:

```powershell
mkdir static-website
mkdir cloud-resume
mkdir ec2-web-server
```

Display the folders:

```powershell
Get-ChildItem
```

---

## 26.2 Windows One-Line Alternative

PowerShell can create all three project folders with:

```powershell
mkdir static-website, cloud-resume, ec2-web-server
```

For beginners, entering one command at a time makes errors easier to identify.

---

## 26.3 macOS or Linux Method

Open Terminal.

Move to Documents when that folder exists:

```bash
cd ~/Documents
```

Create the main folder:

```bash
mkdir aws-beginner-projects
```

Enter it:

```bash
cd aws-beginner-projects
```

Create the project folders:

```bash
mkdir static-website
mkdir cloud-resume
mkdir ec2-web-server
```

List them:

```bash
ls
```

---

## 26.4 macOS or Linux One-Line Alternative

You can create all three directories with:

```bash
mkdir static-website cloud-resume ec2-web-server
```

---

## 26.5 Commands Used

The complete basic sequence is:

```bash
mkdir aws-beginner-projects
cd aws-beginner-projects
mkdir static-website
mkdir cloud-resume
mkdir ec2-web-server
```

---

# 27. Verify the Workspace

## Windows PowerShell

Run:

```powershell
Get-Location
```

Expected location should end with:

```text
aws-beginner-projects
```

Then run:

```powershell
Get-ChildItem
```

Expected folder names:

```text
static-website
cloud-resume
ec2-web-server
```

---

## macOS or Linux

Run:

```bash
pwd
```

Expected location should end with:

```text
aws-beginner-projects
```

Then run:

```bash
ls
```

Expected output:

```text
cloud-resume
ec2-web-server
static-website
```

The order may differ. That is not a problem.

---

# 28. Expected Folder Structure

Your workspace should look like this:

```text
aws-beginner-projects/
├── static-website/
├── cloud-resume/
└── ec2-web-server/
```

At this stage, the three project folders are empty.

Later, they will contain files similar to:

```text
aws-beginner-projects/
├── static-website/
│   ├── index.html
│   ├── style.css
│   └── error.html
│
├── cloud-resume/
│   ├── index.html
│   ├── style.css
│   └── README.md
│
└── ec2-web-server/
    ├── README.md
    └── notes/
```

The EC2 project’s actual website file will be created on the remote Linux instance. The local EC2 folder can store safe documentation and notes.

Do not place the EC2 private key in a public repository.

---

# 29. Open the Workspace in Visual Studio Code

Make sure the terminal is currently inside:

```text
aws-beginner-projects
```

Verify with:

```bash
pwd
```

or on PowerShell:

```powershell
Get-Location
```

Then run:

```bash
code .
```

The period means:

```text
Open the current directory
```

VS Code should open the complete workspace.

The Explorer should display:

```text
AWS-BEGINNER-PROJECTS
├── static-website
├── cloud-resume
└── ec2-web-server
```

The VS Code installer supports opening the current folder through `code .` after the command has been added to PATH.

---

# 30. Open the Workspace Manually

When `code .` does not work, open the folder manually.

## Step 1: Open Visual Studio Code

Launch VS Code from your operating system.

## Step 2: Open the Folder

Select:

```text
File → Open Folder
```

## Step 3: Locate the Workspace

Find:

```text
aws-beginner-projects
```

Select the main folder, not only one of the project folders.

## Step 4: Confirm

Select **Open** or **Select Folder**.

The three project folders should appear in the Explorer.

---

# 31. Trust the Workspace Carefully

VS Code may ask whether you trust the authors of the files in the folder.

Because you created this empty workspace yourself, you can confirm that you trust it.

Be more careful when opening:

* Downloaded projects
* Unknown repositories
* Email attachments
* Folders created by strangers

A workspace can include scripts, tasks, and extensions that perform actions on your computer.

---

# 32. Understanding the Folder Structure

## 32.1 Main Workspace Folder

```text
aws-beginner-projects/
```

This is the parent folder for Volume 1.

It keeps all three projects together.

---

## 32.2 Static Website Folder

```text
static-website/
```

This folder will contain Project 1.

Expected files:

```text
static-website/
├── index.html
├── style.css
└── error.html
```

---

## 32.3 Cloud Resume Folder

```text
cloud-resume/
```

This folder will contain Project 2.

Expected files:

```text
cloud-resume/
├── index.html
├── style.css
└── README.md
```

This folder will later become its own Git repository.

---

## 32.4 EC2 Web Server Folder

```text
ec2-web-server/
```

This folder can contain:

* Project documentation
* Safe notes
* Architecture diagrams
* Troubleshooting records
* Non-sensitive configuration examples

Do not commit the downloaded private key to Git.

A possible structure is:

```text
ec2-web-server/
├── README.md
├── commands.md
└── screenshots/
```

---

## 32.5 Why Separate the Projects?

Separate folders prevent:

* Uploading the wrong files to S3.
* Mixing the resume with the first website.
* Creating Git history for unrelated files.
* Confusing project instructions.
* Accidentally publishing private project material.

Each project should have a clear boundary.

---

# 33. Create a Workspace Information File

Inside the main `aws-beginner-projects` folder, create:

```text
README.md
```

Add:

```markdown
# AWS Beginner Projects

This workspace contains the practical projects from VERIQTA AWS
Beginner Projects, Volume 1.

## Projects

1. Static Website on Amazon S3 and CloudFront
2. Cloud Resume Challenge
3. EC2 Web Server

## Security

Do not store AWS passwords, access keys, MFA codes, private SSH keys,
payment information, or sensitive personal documents in this workspace.
```

This main README is optional.

Do not initialize Git in the main parent folder unless the manual specifically instructs you to do so.

The Cloud Resume folder will receive its own Git repository later.

---

# 34. Test File Creation in Visual Studio Code

## Step 1: Select the Static Website Folder

In the Explorer, right-click:

```text
static-website
```

## Step 2: Create a Test File

Create:

```text
test.txt
```

## Step 3: Add Text

Enter:

```text
Workspace test successful.
```

Save the file.

## Step 4: Confirm from the Terminal

Open the integrated terminal:

```text
Terminal → New Terminal
```

Run:

### Windows PowerShell

```powershell
Get-ChildItem .\static-website
```

### macOS or Linux

```bash
ls static-website
```

You should see:

```text
test.txt
```

## Step 5: Delete the Test File

Delete `test.txt` after confirming that file creation works.

The project folder should be empty again.

---

# 35. Verify All Installed Tools Together

Open a new terminal.

Run each command separately:

```bash
code --version
```

```bash
git --version
```

```bash
aws --version
```

A successful setup returns version information for all three tools.

Next, display the working directory:

```bash
pwd
```

On PowerShell, you may use:

```powershell
Get-Location
```

Then list the project folders:

```bash
ls
```

or:

```powershell
Get-ChildItem
```

---

# 36. Screenshots to Capture

Screenshots are optional, but they can provide evidence that your setup works.

Capture only information that is safe to share.

## Screenshot 1: VS Code Workspace

Capture the Explorer showing:

```text
aws-beginner-projects
static-website
cloud-resume
ec2-web-server
```

## Screenshot 2: Git Version

Capture the terminal showing:

```bash
git --version
```

## Screenshot 3: AWS CLI Version

Capture:

```bash
aws --version
```

## Screenshot 4: VS Code Version

Capture:

```bash
code --version
```

## Screenshot 5: Folder Verification

Capture the command output listing the three project folders.

---

## Do Not Capture

Do not publish screenshots containing:

* Passwords
* AWS access keys
* Secret access keys
* MFA codes
* Payment information
* AWS account recovery details
* Private SSH key contents
* Personal file paths containing sensitive information
* Private email messages

Review every screenshot before adding it to GitHub or social media.

---

# 37. Troubleshooting Visual Studio Code

## Problem: `code` Is Not Recognized on Windows

Example error:

```text
code : The term 'code' is not recognized
```

### Fix 1: Restart the Terminal

Close all PowerShell or Command Prompt windows.

Open a new terminal and run:

```powershell
code --version
```

### Fix 2: Open VS Code Manually

Open VS Code from the Start menu.

Use:

```text
File → Open Folder
```

### Fix 3: Reinstall with PATH Enabled

Run the VS Code installer again.

Confirm that the option to add VS Code to PATH is enabled.

### Fix 4: Check the Command

Run:

```powershell
Get-Command code
```

If no command is found, PATH has not been configured correctly.

---

## Problem: `code` Is Not Found on macOS

Open VS Code.

Use the Command Palette:

```text
Command + Shift + P
```

Run:

```text
Shell Command: Install 'code' command in PATH
```

Close and reopen Terminal.

Test:

```bash
code --version
```

---

## Problem: VS Code Cannot Save a File

Possible causes:

* The folder is read-only.
* The workspace is inside a protected system location.
* Your user does not own the folder.
* Another application has locked the file.
* Storage is full.

Create the workspace inside your normal user Documents or home directory.

On Linux or macOS, inspect permissions with:

```bash
ls -ld .
```

Do not use `sudo` to run VS Code for normal project work.

---

## Problem: The Folder Does Not Appear in VS Code

Confirm that you opened the parent folder:

```text
aws-beginner-projects
```

Do not open only:

```text
static-website
```

unless you intentionally want to work on that project alone.

---

# 38. Troubleshooting Git

## Problem: `git` Is Not Recognized

### Windows

Close and reopen PowerShell.

Run:

```powershell
Get-Command git
```

If Git is still missing, reinstall Git and choose a PATH option that makes Git available from the command line.

### macOS or Linux

Run:

```bash
which git
```

If no location is returned, install Git again using the correct method for your operating system.

---

## Problem: Git Requests a Name and Email

Configure:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Verify:

```bash
git config --global --list
```

---

## Problem: Wrong Name or Email Was Configured

Replace it:

```bash
git config --global user.name "Correct Name"
git config --global user.email "correct-email@example.com"
```

---

## Problem: Git and GitHub Are Confused

Remember:

```text
Git
└── Installed version control software

GitHub
└── Online repository hosting platform
```

Installing Git does not automatically create a GitHub account.

Creating a GitHub account does not automatically install Git.

---

# 39. Troubleshooting AWS CLI

## Problem: `aws` Is Not Recognized

Close and reopen the terminal.

Run:

### Windows

```powershell
Get-Command aws
```

### macOS or Linux

```bash
which aws
```

If no path is returned, repeat the installation using the official AWS CLI version 2 method.

---

## Problem: AWS CLI Version 1 Is Installed

Run:

```bash
aws --version
```

Version 1 begins with:

```text
aws-cli/1
```

Version 2 begins with:

```text
aws-cli/2
```

Use AWS CLI version 2 for this manual. AWS recommends migration to version 2 where version 1 is still present.

---

## Problem: “Unable to Locate Credentials”

Example:

```text
Unable to locate credentials
```

This is expected before authentication is configured.

It confirms that:

* The command exists.
* AWS CLI started.
* No AWS credentials are available.

Do not solve this by creating root access keys.

Wait until the AWS identity setup lesson.

---

## Problem: Linux Installer Reports `unzip` Is Missing

Install it.

### Ubuntu or Debian

```bash
sudo apt update
sudo apt install unzip -y
```

### Fedora or Rocky Linux

```bash
sudo dnf install unzip -y
```

Then repeat:

```bash
unzip awscliv2.zip
```

---

## Problem: Wrong Linux Architecture

Check:

```bash
uname -m
```

Use:

* `x86_64` installer for x86-64
* `aarch64` installer for ARM64

Remove the incorrect downloaded archive before trying again.

---

# 40. Troubleshooting the Project Workspace

## Problem: “Directory Already Exists”

Example:

```text
mkdir: cannot create directory 'aws-beginner-projects': File exists
```

This means the folder already exists.

Do not immediately create another copy.

Check it:

```bash
ls
```

Enter it:

```bash
cd aws-beginner-projects
```

Then inspect its contents.

---

## Problem: You Created the Folder in the Wrong Location

Check the current location:

```bash
pwd
```

or:

```powershell
Get-Location
```

Move to the parent folder:

```bash
cd ..
```

You can move the folder through the graphical file manager or recreate it in the intended location.

Delete a mistaken folder only after confirming it contains nothing important.

---

## Problem: Folder Names Contain Spaces

Use the exact names from the manual:

```text
aws-beginner-projects
static-website
cloud-resume
ec2-web-server
```

Hyphens avoid the need to quote spaces in terminal commands.

---

## Problem: A Project Folder Was Created Inside Another Project

Incorrect structure:

```text
aws-beginner-projects/
└── static-website/
    └── cloud-resume/
        └── ec2-web-server/
```

Correct structure:

```text
aws-beginner-projects/
├── static-website/
├── cloud-resume/
└── ec2-web-server/
```

Return to the main folder before creating each project directory.

Check your location with:

```bash
pwd
```

---

## Problem: `code .` Opens the Wrong Folder

Close the VS Code window.

In the terminal, move into the correct folder:

```bash
cd path-to/aws-beginner-projects
```

Verify:

```bash
pwd
```

Then run:

```bash
code .
```

---

# 41. Common Beginner Mistakes

## Mistake 1: Downloading Software from Unofficial Sources

Use official download and documentation sources.

Unofficial installers may be:

* Outdated
* Modified
* Unsafe
* Bundled with unwanted software

---

## Mistake 2: Copying Commands Without Reading Them

Before pressing Enter, identify:

* The command
* The folder it affects
* The files it creates
* Whether it requires administrator privileges
* Whether it deletes anything

---

## Mistake 3: Running Every Command with Administrator Privileges

Do not use administrator or `sudo` access unless the installation step requires it.

Your normal project files should belong to your normal user account.

---

## Mistake 4: Ignoring the Current Directory

A correct command in the wrong directory can create a confusing folder structure.

Check the location regularly:

```bash
pwd
```

or:

```powershell
Get-Location
```

---

## Mistake 5: Creating One Folder for All Files

Keep the three projects separate.

Do not place every HTML, CSS, README, and server note in one directory.

---

## Mistake 6: Configuring AWS Credentials Too Early

Installing AWS CLI does not require you to create root access keys.

Wait until the secure identity setup is complete.

---

## Mistake 7: Publishing Sensitive Files

Never publish:

* `.pem` private keys
* AWS credential files
* Password files
* Environment files containing secrets
* MFA recovery information
* Payment information

---

## Mistake 8: Assuming Installation Worked

Always verify with:

```bash
code --version
git --version
aws --version
```

---

# 42. Final Verification Checklist

## Computer

* [ ] My computer uses a supported operating system.
* [ ] I have sufficient free storage.
* [ ] I can install software when required.
* [ ] My operating system is reasonably up to date.

## Internet and Accounts

* [ ] I have a stable internet connection.
* [ ] I have access to a permanent email address.
* [ ] I have or will create a GitHub account.
* [ ] I understand that the AWS account will be created in Part 1C.
* [ ] I use different strong passwords for important accounts.

## Browser

* [ ] My browser is current.
* [ ] I can download files.
* [ ] I can open local HTML files.
* [ ] I know how to open browser developer tools.

## Visual Studio Code

* [ ] Visual Studio Code is installed.
* [ ] Visual Studio Code opens.
* [ ] `code --version` works.
* [ ] I can create and save a file.
* [ ] I can open a folder in VS Code.
* [ ] I can open the integrated terminal.

## Git

* [ ] Git is installed.
* [ ] `git --version` works.
* [ ] My Git name is configured.
* [ ] My Git email is configured.
* [ ] I understand the difference between Git and GitHub.

## AWS CLI

* [ ] AWS CLI version 2 is installed.
* [ ] `aws --version` works.
* [ ] `aws help` works.
* [ ] I have not created root access keys.
* [ ] I understand that CLI authentication will be configured later.

## Workspace

* [ ] The `aws-beginner-projects` folder exists.
* [ ] The `static-website` folder exists.
* [ ] The `cloud-resume` folder exists.
* [ ] The `ec2-web-server` folder exists.
* [ ] All three project folders are at the same level.
* [ ] The main workspace opens in VS Code.
* [ ] I know the full location of the workspace.

---

# 43. Final Workspace Test

Open the terminal inside the main workspace.

## Windows PowerShell

Run:

```powershell
Get-Location
Get-ChildItem
code --version
git --version
aws --version
```

## macOS or Linux

Run:

```bash
pwd
ls
code --version
git --version
aws --version
```

Expected folder names:

```text
static-website
cloud-resume
ec2-web-server
```

Expected command results:

```text
Visual Studio Code version information
Git version information
AWS CLI version 2 information
```

Do not continue until the workspace and all required tools work.

---

# 44. Part 1B Knowledge Review

## Question 1

Why do you need Visual Studio Code?

A. To create AWS Regions
B. To write and manage project files
C. To replace the AWS account
D. To create physical servers

**Answer:** B

VS Code will be used to create and edit HTML, CSS, Markdown, and project documentation.

---

## Question 2

What is Git?

A. A web browser
B. A version control system
C. An AWS Region
D. An EC2 operating system

**Answer:** B

Git tracks changes to project files.

---

## Question 3

What is GitHub?

A. A local terminal
B. An S3 storage class
C. An online platform that hosts Git repositories
D. A Linux package manager

**Answer:** C

GitHub will host the Cloud Resume repository.

---

## Question 4

Which command verifies Git?

```bash
git --version
```

---

## Question 5

Which command verifies AWS CLI?

```bash
aws --version
```

---

## Question 6

Which AWS CLI major version should this manual use?

**Answer:** AWS CLI version 2.

---

## Question 7

What does the period mean in this command?

```bash
code .
```

**Answer:** It represents the current directory.

The command opens the current directory in Visual Studio Code.

---

## Question 8

Which command creates a directory?

```bash
mkdir
```

Example:

```bash
mkdir static-website
```

---

## Question 9

Which command changes the current directory?

```bash
cd
```

Example:

```bash
cd aws-beginner-projects
```

---

## Question 10

Which command displays the current directory on macOS or Linux?

```bash
pwd
```

---

## Question 11

Which PowerShell command displays the current location?

```powershell
Get-Location
```

---

## Question 12

What should you do when `aws sts get-caller-identity` reports that credentials cannot be located?

**Answer:** Do not create root access keys. Wait until the secure AWS identity and CLI authentication steps are covered.

---

## Question 13

Which folder will become a Git repository later?

**Answer:**

```text
cloud-resume
```

---

## Question 14

Where should the three project folders be placed?

**Answer:** They should be placed at the same level inside the `aws-beginner-projects` parent folder.

---

## Question 15

Should a private EC2 key be uploaded to GitHub?

**Answer:** No.

A private SSH key must remain secret.

---

# 45. Practical Exercise

Without copying the earlier commands, create this folder structure in a temporary practice location:

```text
practice-workspace/
├── project-a/
├── project-b/
└── project-c/
```

Possible commands:

```bash
mkdir practice-workspace
cd practice-workspace
mkdir project-a
mkdir project-b
mkdir project-c
```

Verify it:

```bash
ls
```

or:

```powershell
Get-ChildItem
```

After completing the exercise, remove the temporary folders only when you are certain they contain nothing important.

This exercise confirms that you understand:

* `mkdir`
* `cd`
* Current working directories
* Directory listing
* Parent and child folders

---

# Part 1B Summary

You have prepared the local computer that will be used for all three AWS projects.

You installed or verified:

* A modern web browser
* Visual Studio Code
* Git
* AWS CLI version 2
* A terminal environment

You also created the main project workspace:

```text
aws-beginner-projects/
├── static-website/
├── cloud-resume/
└── ec2-web-server/
```

You learned how to:

* Open PowerShell on Windows.
* Open Terminal on macOS.
* Open Terminal on Linux.
* Display the current working directory.
* Create directories.
* Move between directories.
* List files and folders.
* Open a workspace with `code .`.
* Verify installed software.
* Identify common installation errors.
* Protect sensitive project information.

Your local computer is now ready for the AWS account and security setup.

# Next Lesson

## Part 1C: Creating and Securing the AWS Account

In Part 1C, you will learn how to:

* Create an AWS account.
* Complete account verification.
* Understand the AWS Management Console.
* Protect the root user.
* Enable multi-factor authentication.
* Create an administrative identity for learning.
* Sign out of the root account.
* Test administrative access.
* Apply the first AWS security rules.
