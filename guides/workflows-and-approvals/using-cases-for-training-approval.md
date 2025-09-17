---
description: >-
  This guide explains how you can use the Cases module to manage training
  approval workflow
---

# Using cases for training approval

### About Cases

A **Case** is a workflow management tool designed to track and manage items as they progress through defined processes. Cases are particularly useful for managing training program approvals, certification requests, and other multi-step approval workflows.

### Key Concepts

#### Person-Centric Design

Each Case is associated with a specific individual (employee or member) and can be assigned to departments or managers for review and approval.

#### Document Management

* Documents can be attached to Cases with customizable types and subtypes
* Documents follow their own review and approval workflows
* All attached documents are visible in both the Case and the associated person's profile

#### Comments & Actions

* Comments can be added to Cases for communication and record-keeping
* Comments support categorization, tagging, flagging, and assignment as action items
* Automatic comments are generated for key events (like case creation)

#### Custom Workflows

Dropdowns, statuses, and workflows can be fully customized based on your organization's Case types and approval processes.

### Working with Cases

#### Creating Cases

> Refer to the [help center](https://docs.shiftiq.com/help/cases/creating-cases) for full instructions on creating Cases.

Cases can be created in two ways:

1. **Manual Creation**: Created directly by administrators or supervisors
2. **Automated Creation**: Triggered by integrated processes such as:
   * Training request submissions
   * Survey responses
   * Employee portal actions

**Example Implementation**

Set up a program catalog where employees can:

1. Browse available learning programs
2. Select desired training
3. Click "Submit Request" to automatically create a Case
4. Have the Case automatically assigned to their supervisor for approval

> **💡 Tip**: Many organizations start with manual Case creation during setup, then transition to automated creation once workflows are established.

For detailed instructions on creating Cases, refer to the online help documentation.

#### Editing Cases

> Refer to the [help center](https://docs.shiftiq.com/help/cases/edit-cases) for steps to edit an existing case.

Cases can be modified after creation to update information, change assignments, or adjust status. Refer to the online help documentation for step-by-step editing instructions.

### Case Documents

> Refer to the [help center](https://docs.shiftiq.com/help/cases/case-documents) for details on how to use documents associated with a case

Documents provide supporting evidence and documentation for training approvals.

#### Key Features

* **Dual Visibility**: Documents appear in both the Case view and the associated person's profile
* **Type Classification**: Assign Types and Subtypes to documents for better organization and reporting
* **Status Tracking**: Documents progress through statuses like:
  * Uploaded
  * Under Review
  * Accepted
  * Rejected

#### Document Requests

You can request specific documents from employees through the system:

* Requests appear on the employee's portal
* Clear instructions guide employees on what to upload
* Automatic notifications ensure timely submission

#### Review and Approval

Optional review mechanisms allow managers to:

* Validate document authenticity
* Approve or reject submissions
* Add comments explaining decisions
* Track approval history

### Case Comments

Comments serve as the communication hub for each Case.

#### Automatic Comments

The system automatically creates comments when:

* A Case is initially created
* Status changes occur
* Documents are uploaded or approved

#### Manual Comments

Supervisors and reviewers can add comments to:

* Communicate with other team members
* Record approval decisions
* Document additional requirements
* Provide feedback to employees

> **⚠️ Important**: Always categorize and tag comments for better organization and future searchability.

### Searching for Cases

Use the robust search functionality to filter Cases by:

* Assignment (person, department, manager)
* Case type and status
* Date ranges
* Document types
* Comment categories
* Custom attributes

This makes it easy to generate reports, track progress, and manage workloads effectively.

### Workflow Configuration

When setting up your training approval workflow, consider these key configuration areas:

#### Case Assignment Options

Choose the assignment strategy that best fits your organization:

1. **Direct Supervisor Assignment**
   * Cases go directly to the employee's supervisor
   * Supervisor handles all documentation collection and approval
   * Best for simple, single-level approvals
2. **Administrative Pre-Processing**
   * Cases first go to an administrator for initial review
   * Administrator validates completeness and routes to appropriate supervisor
   * Best for complex approvals requiring multiple validation steps

#### Dropdown Configuration

Configure these dropdown values to match your approval process:

**Case Types**

Keep categories meaningful and limited. Examples:

* External Training Request
* Internal Training Request
* Certification Program
* Conference Attendance

**Case Status**

Design statuses with reporting needs in mind:

* **Submitted**: Initial request received
* **Under Review**: Being evaluated by supervisor
* **Pending Approval Level 2**: Requires additional authorization
* **Approved**: Ready to proceed
* **Denied - Missing Prerequisites**: Specific rejection reason
* **Denied - Budget Constraints**: Specific rejection reason
* **Completed**: Training finished and documented

**Comment Categories**

* Training Request
* Decision
* Documentation Request
* Follow-up Required
* External Communication

**Comment Sub-Categories**

Provide additional specificity:

* **Decision** → Approved
* **Decision** → Denied
* **Decision** → Needs Additional Training
* **Training Request** → Initial Request
* **Training Request** → Modification Request

**Document Status Options**

* Requested
* Uploaded
* Under Review
* Approved
* Rejected - Resubmission Required

**Document Types**

* External Certificate
* Internal Training Verification
* Course Completion Certificate
* Skills Assessment
* Supervisor Evaluation

**Document Sub-Types**

Optional additional classification based on your needs:

* **External Certificate** → Professional Certification
* **External Certificate** → Vendor Training
* **Internal Training** → Safety Training
* **Internal Training** → Leadership Development

### Best Practices

* **Start Simple**: Begin with basic workflows and add complexity as users become familiar with the system
* **Clear Communication**: Use descriptive status names and comment categories that all users understand
* **Regular Review**: Periodically assess your workflows and adjust configurations based on usage patterns
* **Training**: Ensure all users understand their role in the approval process and how to use the system effectively

***

_For additional support and detailed step-by-step instructions, please visit the_ [_help center_](https://docs.shiftiq.com/help)_._
