# Maintainer: Project setup

The Project has not been created: the available GitHub connector has no organization Project management tools. These steps use GitHub's built-in UI; no Actions or application dependencies are required.

## Create and scope

1. Open the **McGill-Baja-Racing** organization → **Projects** → **New project**. Create a blank Board named **Strain Gauge Installations**. Keep it separate from ProjectBoard.
2. In Project **Settings**, set visibility and team access as appropriate: subsystem leads need read access; Electronics coordinators need write access. Repository access and Project access are separate.
3. Link only **McGill-Baja-Racing/Strain-Gauge-Requests** using the Project's linked repository settings. In that repository's **Projects** tab, link this Project if needed. Do not link other repositories.
4. Use the view filter `repo:McGill-Baja-Racing/Strain-Gauge-Requests is:issue` in all views. This limits displayed items, not permissions: maintainers must also avoid manually adding unrelated items.

## Fields and workflow

In **Settings → Fields**, edit the existing Status field (do not create a duplicate). Add remaining fields with **New field**. Use these names and types:

| Field | Type | Options / meaning |
| --- | --- | --- |
| Status | Single select | Options in the status table below; default Submitted |
| Subsystem | Single select | Suspension, Steering, Drivetrain, Chassis, Other; extend as needed |
| Priority | Single select | High, Medium, Low, Not Reviewed; default Not Reviewed |
| Ideal Completion | Date | Preferred ready-for-data date |
| Latest Completion | Date | Last acceptable ready-for-data date |
| Component Available | Date | Component handover or confirmed delivery |
| Calibration Setup Ready | Date | Fixture and reference equipment readiness |
| Test Date | Date | Planned data collection |
| Gauge Quantity | Number | Total individual gauges across all components, assigned by Electronics |
| DAQ Channels | Number | Total measurement channels, assigned by Electronics |
| Schedule Feasibility | Single select | Feasible, Tight, Not Feasible, Not Reviewed; default Not Reviewed |

Set default single-select values in each field's settings. Leave unreviewed quantities blank, rather than entering zero. Issue text does not automatically populate custom Project fields; Electronics maintains them during review.

| Status (in order) | Entry condition |
| --- | --- |
| Submitted | New request, awaiting review |
| Under Review | Electronics is assessing objective, loads, feasibility, equipment, effort, and schedule |
| Needs Information | Lead must resolve specified questions |
| Awaiting Readiness | Initial review complete; final component, fixtures, references, owner, or schedule still pending |
| Ready for Installation | Electronics explicitly approved all installation prerequisites in the issue |
| Installing | Installation, curing, wiring, and electrical verification underway |
| Calibrating / Validating | Electrical verification complete; physical calibration or suitable strain validation underway |
| Ready for Testing | Calibration/validation successfully completed and documented; usable data ready |
| Blocked | Work cannot proceed; comment with blocker, owner, and next action |

Initial technical review approval does not authorize installation. Approval of a calibration plan does not mean calibration is complete. Moving cards is manual coordination, not an enforced approval gate; use the issue checklist as the record. When unblocked, return to the appropriate stage.

## Views and built-in workflows

Create each view with **New view**, rename it, configure through **View**, then save changes. Apply the repository/issue filter above to each.

| View | Layout | Configuration |
| --- | --- | --- |
| Board | Board | Column field: Status; show all nine options. Display Subsystem, Priority, Latest Completion, Schedule Feasibility. |
| Schedule | Table | Sort Latest Completion ascending, then Ideal Completion ascending. Show Status, Priority, all five date fields, Schedule Feasibility. Review blank dates explicitly. |
| Equipment Planning | Table | Group by Subsystem. Show Status, Gauge Quantity, DAQ Channels, Component Available, Calibration Setup Ready. Use Field sum for Gauge Quantity and DAQ Channels. Assigned equipment details remain in the issue. |

In the Project menu → **Workflows → Auto-add to project → Edit**, select **Strain-Gauge-Requests** as the repository and enter `is:issue is:open` as the filter; **Save and turn on workflow**. Add any existing open requests manually through **Add item** with the repository search. Auto-add applies to matching new/updated items, not a backfill of all existing items. If auto-add is unavailable, Electronics adds each request manually from its issue sidebar.

Set the built-in **Item added to project** workflow to **Submitted** if available. Disable generic status-changing workflows (such as setting a closed issue to Done) that could bypass review or readiness. Close completed issues after documenting Ready for Testing; handle cancelled requests with an explanatory comment and close as not planned.

Finally, copy the actual Project URL into README.md, replacing the pending-setup sentence. Check team access and confirm the first real request appears in Submitted with blank gauge/channel counts. Keep request history in repository issues so a later move to a shared Project remains straightforward.

GitHub references: [Creating a project](https://docs.github.com/en/issues/planning-and-tracking-with-projects/creating-projects/creating-a-project), [single select fields and defaults](https://docs.github.com/en/issues/planning-and-tracking-with-projects/understanding-fields/about-single-select-fields), [board views and field sums](https://docs.github.com/en/issues/planning-and-tracking-with-projects/customizing-views-in-your-project/customizing-the-board-layout), [automatic addition](https://docs.github.com/en/issues/planning-and-tracking-with-projects/automating-your-project/adding-items-automatically).
