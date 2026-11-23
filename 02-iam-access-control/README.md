# AWS IAM Access Control and EC2 Permissions

Overview
I completed this NextWork project in independent mode to get a better understanding of how permissions work in AWS. The idea was to separate access between development and production resources, so someone working in development couldn't accidentally change the production environment.

I wanted to understand how IAM policies, users, groups and resource tags fit together, rather than just giving a user full access to everything.
What I did
- Set up two EC2 instances representing development and production environments.
- Used the Env tag to identify which environment each instance belonged to.
- Worked with an IAM policy that uses the ec2:ResourceTag/Env condition to control access to development resources.
- Created an IAM user and group to give a separate user the relevant permissions.
- Explored how an AWS account alias makes the console sign-in address easier to use.
- Followed the lab's permission-testing scenario: development access should be allowed while stopping the production instance should be denied.
How the access control works
The policy checks the EC2 instance's environment tag before allowing certain actions. A user in the development IAM group should be able to manage the permitted development instance, but not the production instance.

The project also covers allowing EC2 description actions so the user can view instances, while explicitly denying changes to resource tags. That matters because tags are being used to decide which resources the user can access.
What I learned
The key thing I took away was that authentication and authorisation are different. Signing into AWS doesn't automatically mean someone should be able to manage every resource. Permissions need to be set around what that person actually needs to do.

This lab uses a broad ec2:* action with a tag condition to teach the concept. In a production environment, I'd narrow this down to the specific EC2 actions required and test the resulting permissions carefully.
Project notes
This was a hands-on learning exercise completed independently using the NextWork IAM project. I haven't included AWS account details, user credentials, personal screenshots or an exported policy file. The steps above reflect the project's core exercise; I haven't documented any additional testing or troubleshooting beyond that.
