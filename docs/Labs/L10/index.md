# Lab #10: Assignment – RC2 Sliding Fit Design and Verification

## 1. Research and Planning

### ASME RC 2 Sliding Fit Specification

An **RC 2** (Class 2 Precision Sliding Fit) is designed for accurate location where parts must slide or move relative to one another smoothly with minimal play, but without running freely under continuous high-speed rotation.

According to ANSI B4.1 and the *Machinery’s Handbook*:

- **Hole Limits (H6):** The tolerance is applied unilaterally positive (+IT6 / −0.0000 in).
- **Shaft Limits (g5):** The tolerance is negative relative to nominal (−Clearance / −Total Tolerance).

#### Standard Tolerance Table for Nominal Size Ranges

**1. Range 0.12 in – 0.40 in**  
*(Applied to Pin OD and Pin Hole Radius 0.15 in)*

| Feature              | Tolerance          |
|----------------------|--------------------|
| Hole Tolerance (H6)  | +0.0003 in / −0.0000 in |
| Shaft Tolerance (g5) | −0.00015 in / −0.00035 in |
| Theoretical Clearance Range | 0.00015 in (min) to 0.00065 in (max) |

**2. Range 1.19 in – 1.97 in**  
*(Applied to Slide Width 1.30 in and Slide Length 1.90 in)*

| Feature              | Tolerance          |
|----------------------|--------------------|
| Hole/Slot Tolerance (H6) | +0.0006 in / −0.0000 in |
| Shaft/Slide Tolerance (g5) | −0.00040 in / −0.00080 in |
| Theoretical Clearance Range | 0.00040 in (min) to 0.00140 in (max) |

### Real-World Application

RC 2 sliding fits are extensively utilized in manufacturing jigs, fixture locating pins, sliding cover mechanisms, and alignment tracks where high-repeatability positioning is required without binding or excessive wobbling.

### Hand Sketches

The mechanical dimensions, tolerances, and view callouts were documented prior to CAD modeling:

- **Box & Slide Sketch:** Shows the main box body (2.0 in × 1.5 in × 1.0 in), slot dimensions (1.30 in × 1.90 in × 0.15 in), and hole centerlines.
- **Shaft/Pin Sketch:** Shows the alignment pin head (0.25 in × 0.25 in × 0.10 in) and pin shaft diameter (R0.15 in / Ø0.30 in with RC 2 shaft tolerances).

---

## 2. CAD Design

### Component Modeling & Step-by-Step Design Workflow

The assembly comprises three parametric SolidWorks parts: the **Box** (Part A), the **Slide** (Part B), and the **Shaft/Pin** (Part C). Each model was constructed systematically using feature-based parametric operations tied to the global tolerance equations.

#### A. Box Modeling Workflow (`Box.SLDPRT`)

1. **Step 1:** Main Body Extrusion & Internal Pocket Cut (`Boss-Extrude1` & `Cut-Extrude1`)
2. **Step 2:** Internal Sliding Channel Cut (`Cut-Extrude2`)
3. **Step 3:** Vertical Pin Hole Cut (`Cut-Extrude3`)
4. **Step 4:** Lead-In Edge Chamfer (`Chamfer1`)
5. **Step 5:** Base Resin Drainage Holes (`Cut-Extrude4`)

#### B. Slide Modeling Workflow (`Slide.SLDPRT`)

1. **Step 1:** Base Plate Extrusion (`Boss-Extrude1`)
2. **Step 2:** Pass-Through Pin Hole Cut (`Cut-Extrude1`)
3. **Step 3:** Perimeter Chamfer (`Chamfer1`)

#### C. Shaft / Locking Pin Modeling Workflow (`Shaft.SLDPRT`)

1. **Step 1:** Cylindrical Pin Shaft Extrusion (`Boss-Extrude1`)
2. **Step 2:** Rectangular Alignment Head Extrusion (`Boss-Extrude2`)

### CAD Parametric Global Variables & Design Intent

To guarantee a functional RC 2 precision sliding fit on an SLA resin 3D printer (Formlabs Form 3+), a uniform clearance allowance offset of **0.006 in** was applied to all nominal dimensions across the three mating parts:

#### 1. Box Enclosure (`Box.SLDPRT`)

Applied a unilateral positive allowance (**+0.006 in**) to all internal slot feature dimensions and hole features to establish the upper hole boundary:

| Parameter                  | Equation                          | Value     |
|----------------------------|-----------------------------------|-----------|
| SW (Slide Width Gap)       | 1.3 + 0.006 in                    | **1.31 in** |
| SL (Slide Length Gap)      | 1.9 + 0.006 in                    | **1.91 in** |
| SH (Slide Height Gap)      | 0.15 + 0.006 in                   | **0.16 in** |
| Hole (Pin Hole Radius)     | 0.15 + 0.006 in                   | **0.16 in** |
| Hole Depth                 | —                                 | **0.40 in** |

#### 2. Slide Component (`Slide.SLDPRT`)

Applied a unilateral negative allowance (**−0.006 in**) to outer mating surfaces to establish the shaft/insert boundary:

| Parameter                  | Equation                          | Value     |
|----------------------------|-----------------------------------|-----------|
| SW (Slide Width)           | 1.3 − 0.006 in                    | **1.29 in** |
| SL (Slide Length)          | 1.9 − 0.006 in                    | **1.89 in** |
| SH (Slide Thickness)       | 0.15 − 0.006 in                   | **0.14 in** |
| Hole (Pass-Through Pin Hole) | 0.15 + 0.02 in                  | **0.17 in** |

#### 3. Shaft / Alignment Pin (`Shaft.SLDPRT`)

Applied a unilateral negative allowance (**−0.006 in**) to the cylindrical pin shaft:

| Parameter                  | Equation                          | Value          |
|----------------------------|-----------------------------------|----------------|
| OD (Shaft Radius)          | 0.15 − 0.006 in                   | **0.14 in** (Ø0.28 in) |
| Length                     | —                                 | **0.35 in**    |

### Theoretical Total Clearance

With the updated 0.006 in equations applied to both hole features (+0.006 in) and shaft features (−0.006 in), the resulting total diametral/bilateral operating clearance is:
