# A1 – [Topic]

## Objective


## Analyze


## Decide


## Communicate

# A10 – Lead Screw Translating System

# Leadscrew Diameter: (Mohammad)

Part 1 (Leadscrew Diameter) using AISI 1018 Low-Carbon Steel (Sy = 370 MPa = 53,700 psi), formatted according to your assignment structure.

## 1.) Minimum Diameter (d) using Axial Stress

### a.) List all Knowns and Unknowns 

**Knowns:**
- Total required tensile load: F_total = 2 kN = 2000 N
- Number of parallel leadscrews: n = 2
- Safety factor: ns = 4
- Material: AISI 1018 Low-Carbon Steel (Yield strength Sy ≈ 370 MPa = 370 × 10^6 N/m²)

**Unknowns:**
- Force applied to each leadscrew: Fa
- Allowable axial stress: sigma_allow
- Minimum required root/minor diameter of each screw: dr

<img width="678" height="809" alt="image" src="https://github.com/user-attachments/assets/99e6f337-68e1-40e4-b13f-913b5e4ad59f" />
<img width="974" height="531" alt="image" src="https://github.com/user-attachments/assets/a1564001-76cc-46a8-9def-1def132790ff" />


## 2.) Range of Rotational Speed Given Linear Speed 

### a.) List Knowns and Unknowns 

**Knowns:**
- Minimum crosshead linear velocity: V_min = 1 mm/min
- Maximum crosshead linear velocity: V_max = 50 mm/min
- Standard chosen 1018 steel screw thread: 1/2"-10 Single-Start Acme Screw (McMaster-Carr Part 99030A005)
- Screw lead (travel distance per turn): L = 0.100 in/rev = 2.54 mm/rev

**Unknowns:**
- Minimum rotational speed: N_min (in RPM)
- Maximum rotational speed: N_max (in RPM)

<img width="777" height="1006" alt="image" src="https://github.com/user-attachments/assets/72e9a785-def2-4062-b0b1-b739a623e3fd" />


---

## 3.) Maximum Driving Torque per Screw for 2 kN Load 

### a.) List Knowns and Unknowns 

**Knowns:**
- Axial load per screw: Fa = 1000 N
- Nominal outside diameter: d = 0.500 in = 12.7 mm
- Pitch: p = 0.100 in ⇒ p = 2.54 mm
- Mean thread diameter: dm = d − p/2 = 12.7 − 1.27 = 11.43 mm = 0.01143 m
- Lead angle: tan lambda = L / (pi dm) = 2.54 / (pi × 11.43) ≈ 0.0707 ⇒ lambda ≈ 4.05°
- Acme thread flank angle: alpha = 14.5°
- Friction coefficient (steel screw on bronze nut, lubricated): mu ≈ 0.15
- Thrust collar friction radius (assuming collar mean diameter dc ≈ 15 mm = 0.015 m) & friction coefficient muc ≈ 0.12

**Unknowns:**
- Torque required to raise load (raise axial tension): TR

<img width="844" height="1093" alt="image" src="https://github.com/user-attachments/assets/2509760d-36f3-4eac-93ad-de800585c9f9" />


---

## 4.) Select the Leadscrew from Catalog Resources 

Based on the calculated minimum root diameter (dr ≥ 3.71 mm), structural rigidity requirements, and standard component availability from McMaster-Carr:

- **Selected Part:** 1/2"-10 Precision Right-Hand Acme Lead Screw
- **McMaster-Carr Part Number:** 99030A005 (3 ft length)
- **Material:** 1018 Low-Carbon Steel
- **Specifications:**
  - Major Diameter (d): 0.500 in (12.7 mm)
  - Minor/Root Diameter (dr): 0.387 in (9.83 mm) — Well above 3.71 mm minimum constraint
  - Lead / Travel per turn: 0.100 in (2.54 mm)
  - Thread Class: Acme Class 2C single-start

**Or; From LeadScrew**  
Acme Lead Screw, 1/2 – 10, RH, Steel  
Part Number: 59284

### Select a Nut and Flange: (Brayan)

1. Acme Threaded Mount Nut, 1/2 - 10, RH, Bronze  
2. Mounting Flange, .938 - 16 UN, Steel

**Or; (Same Alternative Parts from McMaster)**  
1. Precision Acme Externally Threaded Nut: 673 Bronze, 1/2"-10 Thread Size  
2. Precision Acme Flange: Black-Oxide 1117 Carbon Steel, 15/16"-16 Thread

<img width="974" height="1261" alt="image" src="https://github.com/user-attachments/assets/d16d9d0b-42a1-4184-bcf8-bdf14a6c3d83" />


---
<img width="974" height="1010" alt="image" src="https://github.com/user-attachments/assets/c7d8eb66-1738-4162-87da-c8d630dac9fa" />

## Nut Analysis
<img width="974" height="904" alt="image" src="https://github.com/user-attachments/assets/86d2931f-ef2b-4880-9ab9-f62ad26107b3" />


---

## Design the Crosshead

### 1. Simple Beam Stress/Strength Analysis

**Knowns and Unknowns and FBD**

<img width="974" height="932" alt="image" src="https://github.com/user-attachments/assets/5aa46a87-314f-4ae0-b681-ab045af28c20" />
 
  **Symbolically and Numerical Solve the Unknown**
  
<img width="974" height="839" alt="image" src="https://github.com/user-attachments/assets/fc0b7a00-3259-4c7d-a31c-1b9c8985e4d3" />

---

### 2. Simple Beam Deflection Analysis 

**Crosshead Deflection Analysis**

<img width="853" height="640" alt="image" src="https://github.com/user-attachments/assets/032c3213-227a-4337-be46-4ef6d14f9ff0" />

<img width="844" height="548" alt="image" src="https://github.com/user-attachments/assets/31db75ba-855b-41a1-aa67-a3d0ca62a2a4" />

---

### 3. Multiview Paper Sketch of the Crosshead

*(Insert Multiview sketch image here)*

<img width="974" height="855" alt="image" src="https://github.com/user-attachments/assets/3881ebc4-9196-43fa-9a13-623c6aa8ec29" />


**Global Variables Setup:**

<img width="974" height="283" alt="image" src="https://github.com/user-attachments/assets/fb0ef6ba-700a-4a47-ae4c-8a9ea36549eb" />


- **Step 1 (Base Extrusion):** Sketch a 400 mm × 60 mm rectangle on the Front Plane and perform a Boss-Extrude to a depth of 35 mm to create the main solid crosshead body.

<img width="973" height="603" alt="image" src="https://github.com/user-attachments/assets/f57587a3-336f-4f9c-b7ee-3134189f1333" />


- **Step 2 (Leadscrew Clearance Holes):** Sketch two Ø14 mm circles spaced 300 mm apart (50 mm from each edge) and perform a Cut-Extrude through-all to create clearance holes for the leadscrews.

<img width="972" height="489" alt="image" src="https://github.com/user-attachments/assets/0f9c40be-6078-4aa4-a2bd-942f80609282" />


- **Step 3 (Flange Mounting Tapped Holes):** Use the Hole Wizard to add eight 1/4"-20 UNC tapped holes (4 around each leadscrew hole on a Ø53.086 mm bolt circle) to secure the bronze nut mounting flanges.

<img width="974" height="519" alt="image" src="https://github.com/user-attachments/assets/0a682e35-dc43-49c5-a589-c0744421168f" />


---

## Tabulating Costs: (Mohammad)

### McMaster-Carr Option

If your team prefers to order all components through McMaster-Carr using the integrated flange nut setup:

| Part No.   | Description                                                                 | Req. Qty. | Order Qty. | Unit of Measure | Price   | Total    |
|------------|-----------------------------------------------------------------------------|-----------|------------|-----------------|---------|----------|
| 1329K102   | Precision Acme Flange Black-Oxide 1117 Carbon Steel, 15/16"-16 Thread Size | 2         | 2          | Each            | $67.13  | $134.26  |
| 99030A005  | 1018 Carbon Steel Precision Acme Lead Screw Right Hand, 1/2"-10 Thread Size, 3 Feet Long | 2 | 2 | Each | $18.72 | $37.44 |
| 95072A209  | Precision Acme Externally Threaded Nut Left Hand, 673 Bronze, 1/2"-10 Thread Size | 2 | 2 | Each | $37.61 | $75.22 |
| 5537T038   | T-Slotted Framing 6-Slot Rail, Silver, 80mm High, 40mm Wide, Solid, 1.5' Long | 2 | 2 | Each | $39.52 | $79.04 |
| 5537T46    | T-Slotted Framing Double 6-Slot Rail, Silver, 80mm High, 40mm Wide, Solid 4' Long | 2 | 2 | Each | $98.37 | $196.74 |
| **Total**  |                                                                             |           |            |                 |         | **$522.70** |

### Roton Part Option

| Item Number | Qnt | Name                                                                 | Cost/Item | Total Cost | Purchase Link              |
|-------------|-----|----------------------------------------------------------------------|-----------|------------|----------------------------|
| 1           | 2   | Acme Lead Screw, 1/2 - 10, RH, Steel                                 | $9.10     | $18.20     | Roton Part #59284          |
| 2           | 2   | Acme Threaded Mount Nut, 1/2 - 10, RH, Bronze                        | $23.57    | $47.14     | Roton Part #90222          |
| 3           | 2   | Mounting Flange, .938 - 16 UN, Steel                                 | $49.63    | $99.26     | Roton Part #89838          |
| 4           | 1   | 80/20 T-Slot Framing System Profile: Rectangle, 40 Series, Smooth, Double, 3 m Lg, 80mm x 40mm | $270.09 | $270.09 | Grainger Model 40-4080-1M |
| **Total**   |     |                                                                      |           | **$434.69** |                            |

---

## Parametric Modeling & CAD Assembly (Brayan and Mohammad)

- **Crosshead (Designed):** Parametrically modeled in SOLIDWORKS using global variables (Crosshead Length, Crosshead Width, Height, Screw Spacing) so all dimensions automatically update together.
- **Leadscrews (Downloaded):** Downloaded standard 3D CAD models for two 1/2"-10 RH precision carbon steel Acme leadscrews from McMaster-Carr.
- **Nuts & Flanges (Downloaded):** Sourced CAD models for two precision bronze Acme nuts and steel mounting flanges directly from McMaster-Carr.
- **Frame (Downloaded):** Downloaded 40 Series 80/20 double t-slot aluminum framing CAD files to construct the rigid outer test frame.
- **Assembly Mates:** Mated the aluminum frame using rigid mates, fixed the leadscrews in place, and applied concentric and screw mates between the nuts, flanges, and crosshead to allow realistic vertical crosshead motion.

<img width="974" height="495" alt="image" src="https://github.com/user-attachments/assets/bef42e91-0abf-4a01-81f6-d618c17c893b" />


---

## Lessons Learned

**Engineering Lessons Learned:**

- **Power Screw Drivetrain:** Applied Shigley's power screw torque equations to relate rotational driving torque (T_max = 2.023 N·m) directly to the required 2 kN axial pulling load, accounting for thread and collar friction.
- **Deflection vs. Strength Sizing:** Learned that elastic deflection (delta ≤ 0.1 mm) drives the crosshead design rather than yield strength, requiring an increased height of 35 mm (up from the 14.74 mm strength minimum).
- **Component Sourcing & Interfaces:** Selected standard 1/2"-10 Acme leadscrews from catalog resources, ensuring the 9.83 mm minor diameter comfortably exceeded the calculated 3.71 mm stress limit.
- **Parametric Assembly Modeling:** Configured global variables in SOLIDWORKS (Crosshead Length, Crosshead Width, Height, Screw Spacing) to establish robust parametric links between the custom crosshead, leadscrews, nuts, and aluminum frame.

**Total Time Spent:**

- Calculations & Theoretical Sizing: 4 hours
- Catalog Research & Part Selection: 2 hours
- SOLIDWORKS Modeling & Assembly: 5 hours
- Documentation & Portfolio Write-Up: 3 hours
- **Total Time: 14.0 Hours**

