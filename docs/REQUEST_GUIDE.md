# Request guide

Submit early. Estimates, assumptions, and TBD answers are useful for planning; identify what still needs verification. The template should take about 5–10 minutes with component information available. One issue covers one measurement setup, which may include several identical components with the same measurement and calibration requirements. State the quantity; split unrelated setups.

## What do you want to measure?

Strain is local deformation relative to original length, often reported in microstrain (µε). Force (N), bending moment (N·m), and torque (N·m) describe loading and require a relationship between loading and the measured strain signal. Explain the engineering decision the data will support: “Measure axial tie-rod tension/compression to validate steering load assumptions,” for example. If you need several independent quantities, list each; one signal may not distinguish them.

Describe expected operating load types, directions, minimum and maximum, and units. State whether estimates come from calculations, FEA, previous testing, or assumptions, and link evidence. CAD, photos, material, coatings, and access constraints help Electronics choose practical gauge locations.

## Who chooses the gauges?

Electronics selects gauge locations, orientations, quantities, bridge configurations, wiring, amplifiers, and DAQ channels after reviewing the loading. You only need to specify the components and measurement goals.

Possibilities include one active gauge in a quarter bridge, a two-active-gauge half bridge, a four-active-gauge full bridge, or a strain rosette with grids at different angles to assess local strain directions. Placement, orientation, and bridge connections determine which strain effects contribute to the signal and which can cancel. Four gauges do not automatically separate arbitrary combinations of axial load, bending, and torque. Electronics calculates gauges per component and total quantities from the setup and component count.

## What is a calibration setup?

Strain gauges measure strain. Force or torque output requires a validated relationship between the strain signal and applied loading. A calibration setup holds the component in defined constraints, applies loads in known directions, and provides an independent reference for those loads. A sketch of supports, attachment points, loading direction, and reference equipment is often sufficient for initial review.

Examples:

- **Steering tie rod:** Apply known axial tension and compression through suitable end attachments, using a reference load cell. Check alignment to limit unintended bending.
- **Suspension arm:** Use an appropriate fixture and reference load cell to apply known forces at specified points with representative mounting constraints. Different directions or attachment points may need separate load cases.
- **Shaft:** Apply measured force through a known perpendicular lever arm; torque is force multiplied by that perpendicular distance. Account for fixture reactions and unintended bending.

“Known” means supported by a suitable reference, such as verified weights, a reference load cell, or measured force and lever-arm geometry. A predicted actuator setting or an unverified equipment rating alone is not a measured applied load. Mounting constraints and load directions affect the strain distribution, so describe them explicitly.

**Operating loads** are what you expect on the vehicle. **Calibration loads** are what your setup can safely and realistically reproduce. Report both ranges and units so any gap is visible. For force or torque measurements, subsystem leads are responsible for planning calibration across the full intended measurement range in the selected calibration direction.

With our current Mantracourt setup, calibration is performed in one load direction. State the selected direction (for example, tension or compression) and identify any expected operating loads in the opposite direction. Calibration in one direction does not establish accuracy in the opposite direction; using the same conversion there assumes a symmetric response that has not been validated. Document this limitation when interpreting the data.

If you expect to measure up to 5 kN but your fixture can apply only 2 kN, adapt the plan: obtain suitable reference equipment, redesign the fixture, or arrange access to a capable test setup. Calibrating to 2 kN does not establish accuracy at 5 kN; extending the conversion beyond that range assumes behavior that has not been verified. This is an accuracy and uncertainty concern, even if readings remain repeatable. Resolve the range shortfall within the subsystem's calibration plan before installation rather than relying on Electronics to approve extrapolation. Loading above the expected maximum is not automatically required; any chosen margin must remain within safe component, fixture, and equipment capacities.

Additional load cases may be needed to check sensitivity to unwanted loading, such as bending during axial-force measurement. Electronics will help select final calibration levels, configurations, repeats, and acceptance checks.

For **local strain without force/torque conversion**, propose suitable validation instead of forcing a physical force calibration. This might include comparison with an independent strain reference under repeatable deformation, plus zero, repeatability, and signal checks appropriate to the goal. An electrical check alone does not demonstrate that the installed measurement meets the engineering objective.

## Verify equipment and ownership

Mark equipment “Confirmed available” only after checking that the actual equipment exists, is accessible for the required dates, and has suitable capacity. Record a location, photo, inventory link, or owner confirmation. Include fixtures and reference equipment; mixed availability can be explained item by item.

The submission checkbox helps planning. Before installation, the final review must confirm suitability and availability of the equipment and fixtures and identify a calibration/validation owner. A promising plan is not a completed calibration.

## Dates and responsibilities

- **Component available from:** When the final component can be handed over, or confirmed delivery.
- **Calibration setup ready by:** When fixtures and reference equipment will be usable.
- **Ideal completion:** Preferred date for installed, electrically checked, calibrated/validated instrumentation.
- **Latest acceptable completion:** Last date that still supports the engineering goal; explain the consequence of missing it.
- **Planned testing:** Actual data collection date. Allow time beforehand for installation, adhesive curing, wiring, verification, calibration/validation, and possible rework.

Subsystem leads define objectives and expected loads, provide component information, prepare components, develop realistic mounting/loading or validation setups, verify reference equipment and fixtures, and identify the person responsible for calibration/validation. Electronics reviews feasibility, selects instrumentation and DAQ equipment, plans and performs installations, and verifies electrical function. The named calibration owner coordinates execution and documentation with Electronics and the subsystem.

Initial technical review needs enough information to estimate quantities, DAQ needs, feasibility, calibration complexity, effort, and priority; preliminary calculations are acceptable. Approval to begin installation requires final component/locations, instrumentation selection, component availability or confirmed delivery, a reviewed feasible calibration/validation method, confirmed references and fixtures, an owner, and sufficient scheduled time. Incomplete requests wait for readiness. Only after installation, electrical checks, and documented successful calibration/validation can the setup be marked Ready for Testing.
