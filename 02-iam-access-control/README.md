
# AWS IAM Access Control and EC2 Permissions

## Overview

I completed this project through NextWork's independent challenge mode to get a better understanding of how permissions work in AWS.

The aim was to separate development and production environments so that a user working on development resources wouldn't have permission to make changes to production.

I wanted to understand how IAM users, groups, policies and resource tags work together instead of simply giving users full access to everything.

## What I Did

- Created two EC2 instances to represent development and production environments.
- Used the `Env` tag to identify which environment each instance belonged to.
- Worked with an IAM policy that uses resource tags to control which EC2 instances a user can manage.
- Created an IAM user and group to assign the relevant permissions.
- Explored how AWS account aliases make signing into the AWS console easier.
- Worked through the permission-testing scenario to understand how access should differ between development and production resources.

## How the Access Control Works

The IAM policy uses the `ec2:ResourceTag/Env` condition to restrict certain actions based on an EC2 instance's environment tag.

The intention is to allow the development user to manage permitted development resources without giving them the same permissions over production resources.

The policy also allows EC2 description actions so users can view resources, while explicitly denying the ability to create or delete tags.

This is important because changing the environment tag could otherwise affect which permissions apply to a resource.

## IAM Policy

I've included the IAM policy used for this exercise in [policy.json](./policy.json).

The policy contains three main statements:

1. **Allow EC2 actions** when the resource has the `Env=development` tag.
2. **Allow EC2 Describe actions** so users can view EC2 resources.
3. **Deny tag modifications** to prevent users from creating or deleting resource tags.

The policy uses a broad `ec2:*` permission with a resource-tag condition to demonstrate how IAM access controls work.

For a production environment, I'd restrict this to the specific actions required and test the effective permissions carefully.

## What I Learned

The main thing I took away from this project was the difference between authentication and authorisation.

Just because someone can sign into AWS doesn't mean they should automatically have permission to manage every resource.

It also helped me understand how resource tags can be used alongside IAM policies to separate environments and reduce the risk of someone making changes where they shouldn't.

## Project Status

**Completed — IAM policy documented**

I completed the NextWork IAM exercise independently and have uploaded the policy JSON to this repository.

The policy demonstrates the intended separation between development and production EC2 permissions.

I haven't included screenshots or recorded test results showing the exact allowed and denied actions, so those results aren't presented here as independently verified evidence.

## Project Notes

This was a hands-on learning exercise completed independently through NextWork.

I've included the IAM policy so the configuration can be reviewed without needing access to my AWS account.

No AWS credentials or account-specific details have been included.

This was designed to demonstrate IAM fundamentals rather than represent a production-ready access control configuration.
