# EdaNewIssues

**This Phase 1 Repo is deprecated**

A skeletal repo that contains new EDA issues that are not yet initially reviewed by the dev team and an SOP to triage/distribute them

[EDA Project Kanban Board](https://github.com/orgs/VEuPathDB/projects/2) - Manage the lifecycle of an issue

## SOP

- Outreach creates new issues in EdaNewIssues (this repo)
- Do not add project or milestone tags when creating new issues (otherwise it is automatically moved to the **Needs triage** list without costing)
- Developers assess the issue, then use the right-side panel to:
  - Transfer to the appropriate code repository (if necessary)
  - Assign it a milestone
  - Assign it a project (i.e. to a kanban board)
  - In that project place it in either **Needs Triage**, or, if urgent, **This Cycle**
  - Assign a cost label (low cost = one day or less, medium cost = one week or less, high cost = more than one week)
- ClinEpi staff (Danica) triage the issue
  - They can use columns of their own creation to help organize issues that are not yet scheduled
  - They move tickets out of **Needs Triage** into those columns
  - When they feel it is ready to be worked on, the issue is moved to **Next cycle**
- Developers and ClinEpi staff meet weekly to discuss what issues should move from **Next cycle** to **This cycle**. Issues are assigned to individual developers at this time.
- When a developer merges code that addresses an issue, the issue is closed
- Closed issues are automatically moved to **To be deployed**
- A developer will update the ClinEpiDB qa website and EDA qa services on a nightly basis. At this point, cards in **To be deployed** are moved to **Ready for testing**
- ClinEpi staff will QA issues that are in **Ready for testing**. Ideally they will do so promptly, to give developers early feedback. These issues should remain closed, unless the issue fails QA.
- If an issue fails QA, it will be re-opened and moved to **Failed QA**. The issue should be addressed ASAP.
- Once an issue has passed QA, it is moved to **Complete**.

## Deployment notes

By “deployment”, we mean updating the code used by qa sites. There are two pieces that get deployed: the web-eda code, and the eda services code.

### Front end deployment

In EbrcWebsiteCommon/Client, run the command yarn upgrade @veupathdb/eda@latest

### Back end deployment

Update versions.yml in the feat and qa branch in https://github.com/veupathdb/tagger 
