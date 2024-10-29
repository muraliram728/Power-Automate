# Approval Process Automation with Power Automate

## Overview

This project demonstrates an automated approval process using Microsoft Power Automate. The flow is designed to manage multiple approval levels and dynamically notify approvers via Outlook email. It integrates with SharePoint to manage approval workflows efficiently.

## Key Features

- Multi-level approval process with dynamic assignment of approvers.
- Email notifications to the next approver with personalized messages.
- Integration with three SharePoint lists to manage approvers, workflow history, and email content.

## SharePoint Lists

### 1. Approval Matrix
This list contains the details of approvers and the approval hierarchy.

| Column Name  | Type          | Description                                    |
|--------------|---------------|------------------------------------------------|
| Title        | Single line   | Title of the approval process                  |
| Category     | Single line   | Category of the approval                        |
| Approver1    | Person or Group | First-level approver                          |
| Approver2    | Person or Group | Second-level approver                         |
| Approver3    | Person or Group | Third-level approver                          |
| ...          | ...           | Additional approvers can be added              |

### 2. Workflow History Details
This list tracks the approval requests and their statuses.

| Column Name         | Type                | Description                                 |
|---------------------|---------------------|---------------------------------------------|
| Title                | Single line of text | Title of the request                        |
| Current Approver     | Person or Group     | Current approver assigned                   |
| Approval Status      | Choice              | Status of the approval (Pending/Approved/Rejected) |
| RequestId            | Multiple lines of text | Unique identifier for the request        |
| Approver Level       | Number              | Level of the approver                       |
| Outcome              | Choice              | Final outcome of the request (Approved/Rejected/Clarification) |
| AssignedBy           | Person or Group     | Person who assigned the request             |
| AssignedTo           | Person or Group     | Person the request is assigned to           |
| AssignedOn           | Date and Time       | Date the request was assigned               |
| ActionTakenOn        | Date and Time       | Date the action was taken                   |
| Comments             | Multiple lines of text | Any additional comments                   |
| Category             | Single line of text | Category of the approval                    |

### 3. Approval Mail Content
This list manages the email content for different statuses.

| Column Name         | Type                | Description                                 |
|---------------------|---------------------|---------------------------------------------|
| Title                | Single line of text | Status of the request (Pending/Approved/Rejected) |
| Mail Content         | Multiple lines of text | The content of the email notification       |
| ...                  | ...                 | Additional content fields as required       |

## How It Works

1. When a request is submitted, the initial approver is notified via email.
2. Upon approval, the flow checks the `Approval Matrix` list to determine the next approver.
3. The next approver receives a personalized email notification informing them of their pending review.
4. The process continues until all approvers have taken action or the request is rejected.

## Prerequisites

- Microsoft Power Automate
- SharePoint Online
- Access to create and manage SharePoint lists

![PA-1](https://github.com/user-attachments/assets/696fafb9-70dc-4f27-b3fc-6376ac8e2b6b)
![Pa-2](https://github.com/user-attachments/assets/0d70015d-0a9d-460f-8801-0a8764dfefb6)
![PA-3](https://github.com/user-attachments/assets/25bbb830-994a-4191-917d-1dac08a6a0e3)
![PA-4](https://github.com/user-attachments/assets/11fa7c4e-311b-4170-8a86-db2cf58cbbd3)
![PA-5](https://github.com/user-attachments/assets/6c6a9bfd-af22-4404-8115-c82ddc539dc6)
