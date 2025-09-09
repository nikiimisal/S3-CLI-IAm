
<h1>What Is an IAM User?</h1>

An IAM (Identity and Access Management) user is a digital identity you create within an AWS account. It represents either a person or an application that needs to interact with AWS resources. Each IAM user has:

• A username

• Credentials—such as a console password or access keys

Unlike the AWS root user, which has full account access, IAM users start with no permissions and must be granted explicit access.

![image alt](https://github.com/nikiimisal/S3-CLI-IAm/blob/main/iam.jpg?raw=true)

<h1>Uses & Benefits of IAM Users</h1>

<h2>1. Granular Access Control</h2>

Assign fine-tuned permissions to each user using IAM policies.

<h2>2. Human or Application Use</h2>

IAM users can represent employees, admins, or automated services/tools needing AWS access.

<h2>3. Secure Access Management</h2>

• Use console passwords for web-based access.

• Use access keys for CLI or SDK (programmatic) access.

• Best practice: enforce multi-factor authentication (MFA).

<h2>4. Organization with Groups</h2>

You can group users and apply policies at the group level, simplifying management.

<h2>5. Service Accounts for Workloads</h2>

IAM users can act as service accounts—but avoid embedding access keys directly in code. Prefer roles with temporary credentials when possible.

<h2>6. Adhering to Least Privilege Principle</h2>

Grant only necessary permissions based on job roles or tasks to enhance security.


<h1>Quick Setup Steps: Creating an IAM User</h1>

<h2>Step 1: Create the User</h2>

• Navigate to the IAM Console → Users → Add User.

• Provide a user name and choose the Access Type:

   -- Programmatic access (generates Access Key ID & Secret Access Key)

   -- AWS Management Console access (requires a password)

  <h2>Step 2: Assign Permissions</h2>

 • Attach managed policies or create custom policies.

 • Or add the user to a group with predefined permissions.

 • Optionally set up a permissions boundary to limit all permissions.

 <h2>Step 3: (Optional) Add Tags</h2>

Tags provide metadata about the user (e.g., department, project).

<h2>Step 4: Enable MFA</h2>

Add a virtual or hardware MFA device to enhance security.

<h2>Step 5: Provide Credentials</h2>

Share the sign-in URL (or console URL) and credentials with the user.








