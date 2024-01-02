# Identity and Access Management

IAM is a **Global Service** where we set permissions for what resources of AWS we can use.

## IAM Basics

### Roles

**Root account** can access everything. *It is not best practice to use root accounts.*

**Users** are people within the organization. User can be assigned **groups**. The groups cannot be nested, but an user can belong to multiple groups.

### Permissions

**Users or Groups** can be assigned JSON **policies** where they can see what access they are allowed to do, aka their permissions (e.g. AdministratorAccess).

**The Least Privilege Principle** states that don't give more permission than a user needs.

### Policies

Policies can be applied at the **Group Level**. A policy can also be **inline**, where it is applied to only one user.

The policy consists of: 
* version
* optional id
* statements
    * Sid: statement id
    * **Effect**: Allow or Deny to Action
    * **Principal**: account to which the policy is applied to
    * **Action**: List of API calls
    * **Resource**: list of resources to which the actions applies on
    * Optional condition to when the statement should be applied

Some common policies used are:
* **AdministratorAccess**: allows full access

![Alt text](aa-policy.png)

* **IAMReadOnlyAccess**: allows read only access

![Alt text](roa-policy.png)

Note: You can also create your own policies

## AWS Security

### Password Policy

You can customize password policy to get higher security.

You can set things such as:
* Minimum password length
* Specific character types 
* Password change
* Password Expiration
* Password re-use

### Multi Factor Authentication (MFA)

Users can configure / delete resources in AWS account, so the **root** and all **IAM** users should be protected by MFA.

*MFA is password + physical device*.

Some MFA Device options are:
* **Virtual MFA Device** such as Duo Mobile or Google Authenticator (Support for multiple tokens)
* **Universal 2nd Factor (U2F) Security Key** support multiple root and IAM users with single key
* **Hardware Key Fob MFA Device**

## User Access

There are three ways to access AWS:
* **AWS Management Console**: protected by passwords and MFA
* **AWS Command Line Interface (CLI)**: protected by access keys
* **AWS Software Developer Kit (SDL)**: for code access, protected by access keys (embedded within your application)

Access keys are secret passwords that can be generated through AWS Console, each user must manage their own access keys. *DO NOT SHARE*.













