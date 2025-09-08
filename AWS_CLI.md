<h1>1. Command‑Line Interface (CLI)</h1>

What it is CLI..?

A Command‑Line Interface is a text-based user interface where you type commands into a terminal or shell to interact with your operating system or applications. It’s one of the oldest types of interfaces, dating back to the 1960s

<h2>Uses</h2>

• System administration (e.g., managing files, users, services).

• Software development (e.g., building projects, version control with tools like git) 

• Cloud infrastructure (e.g., AWS CLI for interacting with cloud services) 

• Automation and scripting using shell scripts, piping commands together, environment variables 

• Accessibility: Works well with screen readers and Braille displays..

<h2>Advantages:</h2>

• Fast and powerful—can perform complex tasks in fewer steps than a GUI .

• Lightweight—uses minimal system resources .

• Scriptable—great for automating repetitive tasks.

<h2>Challenges:</h2>

• Steep learning curve due to unfamiliar syntax 

• No "undo": Mistyped commands can lead to serious consequences 

• OS‑specific commands—you can’t always copy-paste between Windows, Linux, or macOS and expect them to work identically

<h1>Setting Up & Getting Started</h1>

<h2>1. Check if AWS CLI is installed if not download it.</h2>

Run a basic AWS CLI command (e.g., aws configure) in your terminal. If no output appears or the command isn’t recognized, install AWS CLI using the official guide.

<h2>2. Install AWS CLI</h2>

• i have provided the link visid the official site download and setup the ClI depends on your systems.

    https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

  and then run agin this command 

    aws configure

  Something like this will be displayed

      Windows PowerShell
      Copyright (C) Microsoft Corporation. All rights reserved.
      
      Try the new cross-platform PowerShell https://aka.ms/pscore6
      
      PS C:\Users\user> aws configure
      AWS Access Key ID [****************AVPB]: access key id here
      AWS Secret Access Key [****************k3Qj]: aws secreat key here
      Default region name [ap-south-1]: ap-south-1
      Default output format [json]: json
      PS C:\Users\user>

or another way<br>
      Visit the AWS documentation and follow the steps for your operating system to install or update AWS CLI. After installation, confirm by running:

      aws --version

<h3>3. Configure AWS Credentials</h3>
If AWS CLI is installed but not configured, run:

      aws configure
Enter your Access Key ID, Secret Access Key, default region, and output format when prompted.

<h2>3. Run Basic AWS CLI Commands</h2>
Once configured, test with commands like:

       aws s3 ls
       aws s3 ls s3://your-bucket-name
<br>
        
        aws ec2 describe-instances
        aws ec2 run-instances --image-id <ami-id> --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids <sg-id> --subnet-id <subnet-id>
<h3>4. Create Access Keys (If Needed)</h3>
If you don’t have an Access Key ID and Secret Access Key yet:

• Log into the AWS Management Console.

• Click on your account name (top right corner) → Security Credentials.

• Under the “Access Keys” section, create a new access key.

• Use these credentials when running



