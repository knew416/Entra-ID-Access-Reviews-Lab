# Microsoft Entra ID Access Reviews Lab

## Project Overview

This project demonstrates how Microsoft Entra ID Access Reviews can be used to periodically validate user access to sensitive resources.

I created a security group representing access to sensitive Finance resources and configured a recurring Access Review to ensure users continue to have a legitimate business need for their access.

The lab demonstrates practical Identity Governance concepts including access certification, least privilege, recurring access reviews, reviewer assignments, and access remediation.

## Technologies Used

* Microsoft Entra ID
* Microsoft Entra ID Governance
* Entra Access Reviews
* Security Groups
* Role-Based Access Control (RBAC)
* Microsoft My Access

## Scenario

An organization has a security group named:

`Finance-Sensitive-Access`

Membership in this group represents access to sensitive Finance resources.

To reduce unnecessary or outdated access, the organization requires resource owners to periodically review group membership and determine whether each user should retain access.

The Access Review process allows reviewers to:

* Approve users who still require access
* Deny users who no longer require access
* Document review decisions
* Periodically recertify access
* Remove unnecessary access based on review results

## Step 1 — Create the Security Group

I created the following Microsoft Entra ID security group:

**Group:** `Finance-Sensitive-Access`

**Group Type:** Security

**Membership Type:** Assigned

The group was configured with one resource owner and three test users to simulate employees with access to sensitive Finance resources.

### IAM Concepts Demonstrated

* Group-based access management
* Resource ownership
* Identity lifecycle management
* Least privilege

### Screenshot

<img width="477" height="705" alt="#1 Finanace Security Group" src="https://github.com/user-attachments/assets/a4b68d20-4bed-41de-9a72-05ce04001003" />

---

## Step 2 — Configure the Access Review

Using Microsoft Entra ID Governance, I created a Resource Access Review for the `Finance-Sensitive-Access` group.

The review was configured to evaluate all users currently assigned to the group.

**Review Name:** `Quarterly Finance Sensitive Access Review`

**Resource:** `Finance-Sensitive-Access`

**Review Scope:** Everyone

**Reviewer:** Resource owners

**Recurrence:** Quarterly

This simulates an organization's quarterly access certification process.

### Screenshot

<img width="673" height="671" alt="#2 Access Review Configuration" src="https://github.com/user-attachments/assets/ca72dbbf-3b51-4239-81b7-d107655ceb92" />


---

## Step 3 — Configure Governance Settings

The Access Review was configured so that the resource owner is responsible for determining whether each user continues to require Finance access.

This establishes a governance process where access is periodically reevaluated rather than remaining assigned indefinitely.

### Governance Flow

`User Access → Periodic Review → Approve/Deny Decision → Remediation → Audit Evidence`

### Screenshot

<img width="726" height="683" alt="Access Review Create" src="https://github.com/user-attachments/assets/358049e0-76fc-4bf3-87c1-767e4131815d" />

<img width="746" height="710" alt="#3 Access Review Settings" src="https://github.com/user-attachments/assets/f09102d3-5bd2-4222-b6e5-6130aedbd38b" />



---

## Step 4 — Initialize the Access Review

After creating the review, Microsoft Entra ID began initializing the review and identifying the identities within its scope.

The Access Review overview confirmed:

* Finance security group selected
* Everyone included in the review scope
* Resource owners assigned as reviewers
* Quarterly recurrence configured

### Screenshot

<img width="992" height="675" alt="#4 Active Access Review" src="https://github.com/user-attachments/assets/6f88492a-2c6d-44f5-9033-02b3f9201c84" />


---

## Step 5 — Perform Access Certification

Once the Access Review becomes active, the resource owner reviews each user's access.

For testing purposes, different decisions are made to demonstrate the certification process.

**Example decision 1 — Approve**

> User still requires Finance access for current responsibilities.

**Example decision 2 — Deny**

> User no longer requires access based on current responsibilities.

This demonstrates how resource owners can validate business need before users retain access to sensitive resources.

### Screenshot

<img width="1187" height="468" alt="#5 Reviewer Decisions" src="https://github.com/user-attachments/assets/ad0a7978-539a-4796-bd06-99b19f24ad0e" />


---

## Step 6 — Validate Access Remediation

After the review is completed and the results are applied, group membership is reviewed again to verify that users denied continued access are removed according to the configured Access Review settings.

This demonstrates the complete access governance lifecycle:

`Provision → Review → Certify → Remediate → Audit`

### Screenshot

<img width="729" height="664" alt="#6 Remediation Results" src="https://github.com/user-attachments/assets/1bb6fd8f-d59b-4185-9e83-8f100fc51df2" />

---

## Security and Governance Concepts Demonstrated

This project demonstrates practical experience with:

* Identity Governance
* Microsoft Entra Access Reviews
* Access Certification
* Least Privilege
* Group-Based Access Management
* Resource Ownership
* Periodic Access Recertification
* Access Remediation
* Identity Lifecycle Management
* Audit Readiness

## Connection to My Professional Experience

This lab directly connects to access governance responsibilities I performed
in a previous Help Desk/IT support role.

As part of monthly access reviews, I audited employee accounts to verify that
assigned skills and access aligned with the jobs employees were authorized to
perform. I also reviewed effective/start dates and validated access
requirements.

When access or skill assignments did not align with approved requirements,
I worked with trainers, team leads, and managers to validate the appropriate
access.

Working with Microsoft Entra Access Reviews allowed me to apply those same
access governance concepts within a modern IAM platform, including periodic
access certification, reviewer decisions, least privilege, remediation, and
audit evidence.

## What I Learned

This lab helped me understand how organizations can move beyond simply granting access and implement continuous identity governance.

Access Reviews provide a structured process for resource owners to periodically verify that users still require access. This helps organizations reduce excessive permissions, enforce least privilege, and maintain evidence that access is being actively governed.

The project also demonstrated how IAM controls can support audit and compliance requirements by documenting who reviewed access, what decision was made, and how unnecessary access was addressed.

## Real-World Application

In an enterprise IAM environment, Access Reviews can be used for sensitive security groups, application access, privileged access, guest users, and other resources requiring periodic certification.

The same process can support Joiner-Mover-Leaver programs by identifying access that is no longer appropriate after an employee changes responsibilities or no longer requires a resource.

---

**Project Focus:** Identity & Access Management (IAM) | Identity Governance | Microsoft Entra ID
