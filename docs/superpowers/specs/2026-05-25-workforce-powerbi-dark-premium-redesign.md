## Workforce Intelligence Power BI Redesign

### Goal

Redesign the current `Workforce & Labor Market Intelligence` Power BI report so it feels like a polished, publish-ready analytical product rather than a default desktop report.

The redesign should solve four problems visible in the current version:

1. weak visual identity
2. broken or cramped card typography
3. charts that look visually loose instead of encapsulated
4. inconsistent page composition across the three report tabs

The intended outcome is a `dark premium` report with a clear dashboard shell, strong card hierarchy, and chart areas that feel self-contained and aligned.

### Visual Direction

The report should follow a `report shell premium` language.

Core traits:

- dark graphite page background
- slightly lighter chart and card surfaces
- soft borders instead of heavy outlines
- restrained glow or highlight only when useful
- strong KPI typography
- short, clean titles
- consistent spacing rhythm

This direction should feel closer to a premium analytical dashboard than to a default Power BI canvas.

### Design Principles

#### 1. One shell per page

Each page should read as one coherent dashboard shell, not as isolated visuals dropped onto a blank page.

That means:

- shared page background
- repeated card treatment
- consistent spacing grid
- repeated header rhythm

#### 2. Charts must live inside chart cards

Every major chart must appear inside its own visual container conceptually and visually.

A chart card should include:

- short title
- optional one-line subtitle
- chart itself
- aligned internal padding

The chart should never look like bars floating directly on the canvas.

#### 3. KPI cards need breathing room

The KPI cards should be large enough to avoid cut-off or wrapped labels.

They should prioritize:

- large number
- small label
- clear contrast
- equal heights

#### 4. Slicers must look deliberate

The slicers should live inside a styled filter rail, not as default control blocks.

They should read as part of the report shell:

- same surface treatment
- same spacing
- same heading logic
- consistent control sizing

### Color System

#### Base palette

- page background: near-black graphite
- panel background: dark slate or deep blue-charcoal
- border: muted blue-gray
- primary text: warm white
- secondary text: soft gray

#### Analytical accents

- primary signal: cyan / blue-teal
- medium attention: amber
- critical risk: coral-red
- external pressure / market context: lime-green only where it helps distinguish a metric family

The palette should avoid looking neon-heavy. The report should feel premium first, vibrant second.

### Typography

The current report shows broken labels and cramped text. The redesign should use a stricter hierarchy.

#### KPI cards

- number: large, bold, highly readable
- label: smaller, lighter, never wrapping awkwardly

#### Chart titles

- concise
- 1 line when possible
- title case or sentence case consistently

#### Subtitles

- one short sentence only
- muted color
- never paragraph-length

### Page Architecture

The report has three pages and each page should share the same structural language.

#### Page 1: Executive Overview

Purpose:

Give a business-facing summary of workforce size, attrition, replacement cost, modeled risk, and external labor pressure.

Structure:

1. page header / title strip
2. filter rail
3. KPI strip
4. main analysis grid

Content:

- `Headcount`
- `Attrition Rate`
- `High Risk Employees`
- `High Risk Rate`
- `Average Tenure`
- `Estimated Replacement Cost Total`
- `External Pressure Score`

Visual grid:

- `Attrition by Department`
- `Risk Band Distribution`
- `Retention Priority by Department`
- `External Pressure by Occupation Group`
- `Risk vs Cost Exposure by Department`

Recommended composition:

- filter rail on the left or as a vertical anchored block
- KPI band across the top-right content area
- charts in a balanced `2x2` grid
- one diagnostic visual below the main grid or in a second analytical row

#### Page 2: Attrition Risk

Purpose:

Show where modeled attrition risk is concentrated and what operational signals explain it.

Content:

- `High Risk Employees`
- `Average Monthly Base Pay`
- `Average Risk Score`
- `Overtime Rate`
- `Training Participation Rate`
- `Stalled Progression Rate`

Visual grid:

- `Main Risk Drivers`
- `Risk by Salary Band`
- `Recommended Actions`
- `Risk by Job Role`
- `Department x Risk Band Heatmap`

Recommended composition:

- KPI strip at top
- two medium charts in the upper grid
- one table, one larger chart, and one compact diagnostic matrix below

The table should feel like a report panel, not a spreadsheet block.

#### Page 3: Labor Market Context

Purpose:

Show the external labor market layer and how it connects to workforce exposure.

Content:

- `Unemployment Rate`
- `Wage Index`
- `Labor Demand Index`
- `External Pressure Score`
- `Average Monthly Base Pay by Department`
- `Replacement Cost Exposure by Department`

Visual grid:

- `External Pressure by Occupation Group`
- `Departments Exposed to External Pressure`
- `Market Context Table`

Recommended composition:

- KPI strip at top
- two horizontally balanced charts below
- one wide context table at the bottom

### Layout System

The current report feels uneven because it mixes default visual sizes and uneven spacing.

The redesign should use a tighter layout system:

- page width treated as one grid
- consistent horizontal gutters
- consistent vertical rhythm
- repeated panel heights within the same row

Recommended spacing logic:

- large gap between page sections
- medium gap between panel rows
- smaller internal padding inside chart cards

### Additional Analytical Layer

The current report should not stop at simple ranking bars. To increase analytical depth without overwhelming the dashboard, the redesign should add a small number of diagnostic elements that support executive interpretation.

#### New measures to support the redesign

- `High Risk Rate = High Risk Employees / Headcount`
- `Medium Risk Rate = Medium Risk Employees / Headcount`
- `Training Participation Rate`
- `Stalled Progression Rate`
- `Replacement Cost Exposure by Department`
- `Average Monthly Base Pay by Department`

These measures should only be added if they are directly used in a visual, card, or supporting calculation. The goal is not to inflate the model with unused metrics.

#### New diagnostic visuals

##### 1. Risk vs Cost Exposure by Department

Recommended for `Executive Overview`.

Visual type:

- scatter chart

Encoding:

- X axis: `Average Risk Score`
- Y axis: `Replacement Cost Exposure by Department`
- bubble size: `Headcount`
- bubble color: `External Pressure Score` or `Retention Priority Tier`

Purpose:

This helps separate departments that are:

- low risk and low consequence
- high risk but low scale
- high cost and high urgency
- high pressure and retention-critical

##### 2. Department x Risk Band Heatmap

Recommended for `Attrition Risk`.

Visual type:

- matrix or heatmap-style table with conditional formatting

Encoding:

- rows: `department_name`
- columns: `risk_band`
- values: `employee count` or `% of department`

Purpose:

This makes concentration patterns visible without relying only on ordered bars. It should help show whether a department’s issue is broad, concentrated, or skewed toward a specific band.

### Power BI-Specific Implementation Notes

The report should be improved in two layers:

#### 1. Structural layout

- reposition visuals
- normalize card sizes
- normalize chart sizes
- give each page a stable grid

#### 2. Visual styling

- page background color
- card fill colors
- border colors
- title text styling
- label sizing
- data colors

The goal is to avoid overengineering the model. Most value now is in report composition and styling.

### What Will Change First

Implementation should proceed in this order:

1. fix page-level shells and spacing
2. fix KPI cards so labels no longer break
3. group visuals into real chart cards
4. style filter rail
5. add the new executive and diagnostic measures actually used by the pages
6. introduce the scatter and heatmap as the two analytical extras
7. apply consistent palette across the three pages
8. refine titles, labels, and subtitles

### Success Criteria

The redesign is successful if:

- the report feels intentionally designed rather than auto-laid-out
- KPI labels stop breaking visually
- each chart reads as a closed panel
- the three pages clearly belong to the same analytical product
- the report looks strong enough to publish as a portfolio dashboard

### Non-Goals

This redesign is not trying to:

- rebuild the semantic model
- add new data sources
- change the analytical scope of the project
- turn the report into a flashy novelty dashboard

The focus is presentation quality, dashboard composition, and report polish.
