---
description: >-
  Working notes on supporting competency (outcome) score calculations in Shift
  iQ for competency-based education
---

# Competency (outcome) score calculations

## Objective

**Full support of CBE in Shift iQ requires the ability to calculate scores for competencies.**

_This page is still being developed and will require team collaboration. This page was developed (partially) from conversations in this issue:_ [DEV-1656](https://insite.atlassian.net/browse/DEV-1656) - Investigate the method of Outcome score calculations that Canvas uses (Closed)

## Success metrics

Project goals and metrics to determine success.

| **Goal** | **Metric** |
| --- | --- |
| An existing customer will use Shift iQ to calculate competency scores (USU, _other_?). | Customer feedback will demonstrate ease of use when configuring outcome scores. _Qualitative_. |
| Post-Secondary institution(s) will use Shift iQ to calculate competency scores. | Increased revenue through acquisition of new customer(s) in 2023. _Quantitative._ |

## Assumptions

- While this feature has not been requested _directly_ from our customers, there is an assumption through conversations with customers (USU, CBExchange etc.) that this is a core feature for a true Competency-based LMS.
  - _We are assuming that having this functionality in place will make the core product more valuable to our prospective (and some of our existing) customers._
  - _Waiting for customers to completely drive requirements and a solution to this problem has not proven successful. We should have an MVP in place to prove that this is possible in Shift._
- We _**do not**_ need to be tightly aligned to Canvas. Rather, we can use Canvas to understand how an LMS has implemented outcome / competency calculations, ensuring it works for Shift / our customers at all times.
- Note: we documented a related issue with Logbooks where it was hypothesised that we should display the most recent status of validated competencies instead of the "highest". However, as noted during investigation in the comments of this task - we should heed caution with changing the logic here and ensure alignment with assessments:
  - [https://insite.atlassian.net/browse/DEV-10528](https://insite.atlassian.net/browse/DEV-10528)
    - _**Some analysis competed via the above issue that should be incorporated into this document.**_

## Requirements

General requirements / child-issues can be created here: [CANCELLED-1016](https://insite.atlassian.net/browse/CANCELLED-1016) - Implement Outcome (Competency) score calculations (To Do)

| **Requirement** | **User Story** | **Importance** | **Jira Issue** | **Notes** |
| --- | --- | --- | --- | --- |
| Calculation of competency scores must not impact how existing customers use Shift iQ (those that _do not_ require this functionality). | As an existing Admin using Shift iQ, I should be able to continue to use the product without interruption so that my processes are not negatively interrupted. | HIGH | | |
| Determine how outcomes will be organized in Shift iQ and what entities (gradebook scores, attempts and etc) will be used to calculate the outcome score. | | | | |
| Determine what types of calculation will be implemented for purposes of competency calculation | | | | [https://community.canvaslms.com/t5/Canvas-Basics-Guide/What-are-Outcomes/ta-p/75#calculation\_methods](https://community.canvaslms.com/t5/Canvas-Basics-Guide/What-are-Outcomes/ta-p/75#calculation_methods) This link provides example calculations and definitions to support implementation of different calculation types. |

## Supporting Resources

Add links, documents etc. that support development or help the team more deeply understand the context of this feature.

**Canvas outcome score calculations:** [https://community.canvaslms.com/t5/Canvas-Basics-Guide/What-are-Outcomes/ta-p/75#calculation\_methods](https://community.canvaslms.com/t5/Canvas-Basics-Guide/What-are-Outcomes/ta-p/75#calculation_methods)

**Files provided by Neal from USU:**

From the email sent on "Fri 10/8/2021 1:25 PM"

- _Canvas Outcomes 2019-2020:_ Example of the report that MPH has been receiving after much data manipulation.
- _Outcome\_results\_csv_: The Canvas account-level CSV "Outcome results" report.
- _Outcomes-Fall\_2020\_HEP-6550…_: The Mastery Gradebook CSV export, from Canvas at the course level.
- _Outcome\_export_: All outcomes from the KHS subaccount
- _Student\_assignment_: The Canvas account-level "Student Compentency" report.

Attached files:

- Canvas Outcomes - 2019-2020.xlsx
- student_assignment_outcome_map_csv_08_Oct_2021_420220211008-104587-xr30si.csv
- Outcomes-Fall_2020_HEP-6550-LO1_XL.csv
- outcome_results_csv_07_Feb_2020_396320200207-9660-vo4qya.csv
- outcome_export_csv_08_Oct_2021_420120211008-106631-1dlzsuu.csv

From the email sent on "Mon 10/18/2021 5:20 PM":

> Amy Carpenter tracked down the outcomes reporting that our Biology department is doing using Canvas outcomes data. They have put a lot more time and effort into massaging their reports than MPH, so I felt it would be good to add them to the list of examples to refer to for current institutional outcomes reporting needs.
>
> Their outcomes data website is a beauty to behold: [https://biology.usu.edu/assessment\_files/undergrad\_assessment/outcomes\_data](https://can01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fbiology.usu.edu%2Fassessment_files%2Fundergrad_assessment%2Foutcomes_data&data=04%7C01%7Caleksey%40insite.com%7C231f4dd25b8e4822cb0d08d9928dc548%7C926e6a06be7e47539a3f50d1842137ca%7C0%7C0%7C637701960153920373%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=AembdjVPgMYXeRuaEe%2FTXqKXmsKCe9V1S64aZ6WNyi4%3D&reserved=0)
>
> - It's worth noting that this was spearheaded by one of the faculty we worked with for the original CBE project that brought us all together. She would probably be a great collaborator to bring into our conversations.
>
> Also attached is a spreadsheet that our data specialist, Meghan Lewis, helped put together, which helped lead to the reports on the site above.

Attached file:

- Biology Outcomes - 202040.xlsx

## User interaction and design

## Open Questions

| **Question** | **Answer** | **Date Answered** |
| --- | --- | --- |
| How will we ensure that the calculation methods implemented meet the needs of prospective customers? | | |
| What calculation methods are easiest to implement from a development perspective? | Number of times, Most recent score, and Highest score are simplest and should likely be implemented together first. _(While the above 3 are easiest to implement, it is likely that "Decaying Average" has the most value to our customers)._ | December 14, 22' |
| We can store competency scores within gradebooks, for example, but I don't know exactly how (or if) this relates to outcome score calculations (Dan). | **KYLE FU** | |
| …if we **did** support outcome score calculations, then where would this be visible to a learner or to an administrator within Shift iQ? And what would you expect it to look like? (Dan) | **KYLE DEVELOP MOCKUP(S)\*\*** | |

## Out of Scope

- Occasionally there is discussion about **whether or not a question should evaluate multiple competencies**, and in the past the **decision has always been "no"** for the sake of simplicity.
