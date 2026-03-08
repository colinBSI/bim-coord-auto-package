# Coordination Panel

The Coordination panel supports active clash review workflows. Use these tools during weekly coordination sessions (Tuesday clash detection through Thursday ACC issue creation).

---

## Tools

### Create Clash Views

**Purpose:** Generates 15 standard 3D views, one per discipline pair, for clash review.

**When to use:** Once at project start, or when new discipline pairs are added to the project.

**How to use:**
1. Click **Create Clash Views**
2. Views appear in the Project Browser

**Views created (examples):**
- Clash - Arch vs Structure
- Clash - Structure vs Mechanical
- Clash - Mechanical vs Plumbing
- Clash - Arch vs Mechanical
- *(and 11 more discipline pairs)*

> Idempotent — if a view with that name already exists, it is skipped.

---

### Color By Workset

**Purpose:** Applies solid color overrides to all elements in the active view, grouped by workset.

**When to use:**
- To visually verify workset assignments
- To identify elements accidentally placed on the wrong workset

**How to use:**
1. Open a 3D view (e.g., 3D-Worksets)
2. Click **Color By Workset**
3. Each workset is assigned a unique solid fill color

> Overrides are applied to the active view only. Switch to a different view to remove them.

---

### Color By Discipline

**Purpose:** Applies solid color overrides to all elements in the active view, grouped by the Discipline parameter.

**When to use:**
- To visually verify discipline assignments on linked models
- During coordination meetings to distinguish disciplines quickly

**How to use:**
1. Open a 3D view
2. Click **Color By Discipline**
3. Up to 8 disciplines are assigned unique colors

---

### Clash Status Manager

**Purpose:** Updates the `Clash_Status` shared parameter on selected elements.

**When to use:** During clash review sessions to mark progress.

**How to use:**
1. Select the elements involved in a clash
2. Click **Clash Status Manager**
3. Choose a status from the dialog:
   - **Open** — newly identified, not yet assigned
   - **In Progress** — assigned and being resolved
   - **Resolved** — clash has been corrected

**Status values feed into:** Power BI Coordination Performance dashboard and weekly PDF report.

---

### Zone Checker

**Purpose:** Verifies that elements have a valid `Coordination_Zone` parameter value assigned.

**When to use:**
- After model setup to confirm zones are assigned
- Before running the Python pipeline (zones are used for clash grouping)

**How to use:**
1. Click **Zone Checker**
2. Results appear in the pyRevit console listing elements with missing or invalid zone values

---

### Interference Check

**Purpose:** Launches Revit's native Interference Check dialog.

**When to use:** For quick in-Revit clash detection without exporting to Navisworks.

**How to use:**
1. Click **Interference Check**
2. Revit's built-in Interference Check dialog opens
3. Select categories to check and run

> For full project coordination, use Navisworks for clash detection and the Python pipeline for processing results. Use this tool for quick spot checks only.

---

## Coordination Tolerances

| Type | Tolerance |
|---|---|
| Hard clash | 0 in |
| MEP clearance | 1–2 in |
| Equipment clearance | 24–36 in |

---

## Tips

- Use **Color By Workset** and **Color By Discipline** in the dedicated 3D views (3D-Worksets, 3D-Coordination) created by the Project Setup panel
- **Clash Status Manager** works on multi-selection — select all elements involved in a clash group before running
- The Zone Checker should pass before Tuesday's Navisworks export, so zones are valid in the clash report
