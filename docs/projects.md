---
title: Projects
description: Industrial energy assessments and engineering research by Nick Bailey, with methods and measured outcomes.
hide:
  - toc
---
# Projects

A selection of assessments and research, chosen to show the same arc each time:
a real problem, a quantified recommendation, a projected saving, and a method that
holds up when someone checks it.

<div class="grid cards" markdown>

-   __Compressed-air leak quantification__

    ---

    Field detection and queueing-based modeling of leak load across a manufacturing
    facility, turned into a ranked set of fixes with payback.

    *SNE-ITAC · ultrasonic imaging · M/M/∞ queueing model*

-   __Drone-based PV panel inspection__

    ---

    Context-adaptive instance segmentation for locating and inspecting photovoltaic
    panels from UAV imagery, built on a foundation-model backbone.

    *PhD research · presented at IEEE MIT URTC 2025*

-   __Economics of PV degradation__

    ---

    Modeled the energy value at risk from warranty-eligible defects across
    Connecticut's distributed solar fleet to inform inspection policy.

    *Clean Energy & Sustainability Innovation Program*

-   __Assessment workflow tooling__

    ---

    Rebuilt the center's assessment process around a structured data system, cutting
    manual handoffs between field data and reporting.

    *SNE-ITAC · presented to the ITAC Advisory Board*

</div>

---

## Compressed-air leak quantification

!!! info "At a glance"

    **Context:** Southern New England ITAC (DOE program), [facility type] manufacturer.
    **My role:** Lead student, end to end (field data, modeling, reporting).

**Problem.** Compressed air is one of the most expensive utilities on a plant floor,
and leaks bleed it continuously, often unmetered. The facility had no quantified
picture of how much air (and electricity) was being lost, or where.

**Approach.** I designed a standardized procedure for locating and sizing leaks with
ultrasonic imaging, then modeled the aggregate leak load as an M/M/∞ queueing system
to estimate steady-state air loss and the compressor energy required to make it up.
Field measurements (pressure and current transducers) anchored the model to the
plant's actual operating conditions.

**Recommendation and projected savings.** I translated the result into a ranked set of
repairs with the numbers a decision-maker needs:

- Estimated air loss recovered: [projected CFM / kWh per year]
- Projected annual savings: [estimated $ per year]
- Simple payback: [estimated payback]

!!! abstract "Validated methodology"

    The estimate isn't a single back-of-envelope figure. Leak sizing was instrument-based,
    the queueing model's assumptions are stated and bounded, and the projected savings
    were tied to measured compressor behavior rather than nameplate values. The method
    is built to be re-run and re-checked.

---

## Drone-based photovoltaic panel inspection

!!! info "At a glance"

    **Context:** PhD research, UConn (thesis topic).
    **Output:** *Context-Adaptive Instance Segmentation for Photovoltaic Panel
    Inspections*, presented at the 2025 IEEE MIT Undergraduate Research Technology
    Conference.

**Problem.** Photovoltaic systems degrade and develop defects, but most residential and
small-commercial installations have little monitoring infrastructure to catch problems
within warranty coverage. Manual inspection does not scale to a fleet.

**Approach.** I built a zero-shot instance segmentation pipeline on Meta's Segment
Anything Model (SAM) to localize panels automatically in UAV imagery, then validated it
across varied altitude, contrast, and panel orientation to establish detection-accuracy
benchmarks for operational deployment. The thesis extends this into a foundation-model
approach for drone-assisted inspection.

**Why it matters.** Reliable automated localization is the step that makes thermal and
multi-modal defect detection usable at fleet scale, which in turn makes warranty
enforcement and proactive maintenance feasible where they currently are not.

---

## Economics of photovoltaic degradation

!!! info "At a glance"

    **Context:** Clean Energy & Sustainability Innovation Program (fellowship).

**Problem.** Connecticut's distributed solar fleet is large and largely unmonitored,
so warranty-eligible defects can go undetected until after coverage lapses, shifting
avoidable cost onto system owners.

**Approach and finding.** Across the state's distributed fleet (1,091 MW over 91,290
installations), I estimated roughly **$1.8M in annual energy value at risk** from
warranty-eligible defects, and evaluated UAV-based thermal inspection protocols as a
way to surface those defects in time to act. The analysis was framed to support
warranty-enforcement policy, not just to produce a number.

---

## Supply-chain resilience modeling

!!! info "At a glance"

    **Context:** Supply Chain Engineering Intern, Lockheed Martin (Sikorsky).

**Problem.** Critical parts carried single-source supply risk, and proposed resilience
projects competed for limited budget without a clear financial case.

**Approach and outcome.** I combined assembly-impact metrics with supplier analytics to
prioritize which parts to re-source, then modeled the financial and logistical
feasibility of specific resilience projects (including a new shipping provider),
identifying **over $500K in projected annual savings**.

---

!!! info "Want the technical detail?"

    Methods, instrumentation, and publications are on
    [LinkedIn](https://www.linkedin.com/in/ndbailey). Happy to walk through any of the
    work above, including the parts that didn't make the highlight reel.
