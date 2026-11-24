# MEGR 2156 L3D – Final Project, Part 1

# Desk Cable Management System

## 1. Research

### 1.1 Spiral Design Process

The Spiral Design Process develops a product through repeated cycles rather than a single build:

- **Planning:** Define the problem, cable capacities, target dimensions, and required manufacturing methods.
- **Risk Analysis:** Identify failure points early, such as weak FDM layer adhesion, loose sliding tolerances, or stripped printed threads.
- **Engineering:** Build the CAD model, select materials, and manufacture initial test pieces.
- **Evaluation:** Test physical prototypes for fit, clamping strength, and usability, then feed those results into the next design cycle.

### 1.2 FDM Anisotropic Behavior

Because FDM prints parts layer by layer, strength depends heavily on force direction. Parts are weakest perpendicular to the layer lines.

- **Design Impact:** The clamping frame and cable holders face bending and tightening stresses that could cause layers to split.
- **Mitigation:** I will orient parts so primary forces run parallel to the layers, use thicker perimeters with rounded corners, and test PETG alongside PLA for better flexibility and layer adhesion.

### 1.3 SLA Shrinkage and Dimensional Accuracy

SLA resin shrinks slightly during UV curing and post-curing, with typical Form 4 XY tolerances around ±0.15% to ±0.3%, depending on part size.

- **Design Impact:** Uncompensated shrinkage can make small sliding connectors too tight to assemble or too loose to hold.
- **Mitigation:** I will keep SLA prints under the 9.7 sq in (one-quarter build plate) limit, follow Formlabs curing guidelines, measure test coupons with calipers, and adjust CAD clearances (0.005 in to 0.012 in) before final printing.

### 1.4 Laser Cutting Kerf Compensation

Kerf is the width of material vaporized by the laser beam along the cut path, which shrinks external tabs and widens internal slots.

- **Application:** While my initial prototype uses FDM and SLA, accounting for kerf ensures tight press-fits if laser-cut panels are added in future iterations.

  `D_CAD = D_actual ± K`

---

## 2. Problem Definition

### Problem 1: Desk Cable Management System (FDM & SLA)

Workstations use multiple power and data cables that constantly tangle and slip behind the desk when unplugged. A modular, clamp-on organizer with sliding holders keeps cords accessible and off the floor.

### Problem 2: Adjustable Drawer Organizer (Laser Cutter & FDM)

Standard fixed drawer trays waste space and fail to fit varying drawer sizes. Combining laser-cut dividers with 3D-printed locking brackets allows users to customize compartment sizes.

### Problem 3: Adjustable Car Cup Holder (FDM & SLA)

Factory cup holders rarely fit both narrow cans and wide insulated bottles securely. A spring- or screw-actuated insert using FDM housing and precision SLA gears can adapt to different container diameters.

---

## 3. Problem Selection

**Selected Problem: Desk Cable Management System**

### Why and How

This solves an everyday workspace frustration while letting me test two critical mechanical interfaces:

1. **Sliding Slot Connection:** Needs an RC-style sliding clearance fit—loose enough to slide smoothly along the frame, yet tight enough to keep cable holders from falling out.
2. **Threaded Clamping Screw:** Uses a 3/8"-16 UNC thread to lock the frame onto a desk corner. I will test printed threads against a captured metal nut to prevent thread wear under clamping loads.

---

## 4. Concept Development

- **Main Mounting Frame:** Attaches to the desk corner and features a continuous sliding track.
- **Removable Cable Holders:** Snap or slide onto the frame to organize 6–8 cables (0.12 in–0.31 in diameter).
- **Clamping Mechanism:** A hand-turned 3/8"-16 UNC screw with a wide contact pad to secure the frame without damaging the desk.
- **Manufacturing Strategy:** Print all initial components in FDM to check ergonomics and fit, then transition high-precision sliding and locking pieces to SLA (Form 4).

---

## 5. Testing Critical Features

To validate the mechanical joints and printed threads before scaling up to the full multi-cable organizer, I printed a single-slot test prototype in FDM to measure and dial in exact tolerances.

### 5.1 Iterative Testing and Findings

| Feature | Iteration 1 Result | Root Cause | Iteration 2 Adjustment and Result |
|---|---|---|---|
| Sliding Slot Fit | Failed (too tight): Parts would not assemble. | Caliper measurements showed the slide was 0.05 in larger than the slot opening due to print expansion. | Adjusted the mating clearance to −0.0025 in between the lock slide and slot, achieving a secure, snug press-fit. |
| 3/8"-16 UNC Screw Thread | Failed (did not fit): Screw could not thread into the frame. | The CAD hole was modeled at standard tap-drill size rather than accounting for FDM extrusion tolerances. | Enlarged the internal thread hole by 0.02 in over the screw shaft diameter. The screw threads smoothly, though tightening torque remains limited by plastic strength. |

### 5.2 Prototype Scope and Next Steps

- **Single-Slot Validation:** For this testing phase, I modeled and printed a simplified single-cable version of the organizer to isolate and verify the sliding lock and clamping screw without wasting material or print time.
- **SLA Transition:** With the FDM clearances now verified, I will evaluate moving the locking slide and high-precision mating features to SLA (Form 4) in the next phase to improve surface finish and dimensional consistency.

---

## 6. Video Presentation (30-Second Script)



https://github.com/user-attachments/assets/2b68f9a4-b7e8-46f6-a19d-79e1526075f0



---

## 7. Documentation (Design and Prototyping Log)

### Iteration 1: Initial Tolerance Check

- **Focus:** Baseline FDM print of the mounting frame, single-slot cable holder, and clamping screw.
- **Issues Found:**
  - The sliding connector measured 0.05 in wider than the mating slot and could not be inserted.
  - The 3/8"-16 UNC clamping screw bound up immediately because the female hole was sized for a metal tap rather than a 3D-printed thread.

### Iteration 2: Adjusted Clearances and Press-Fit Validation

- **Focus:** Updating CAD parameters to fix assembly interference.
- **Improvements Made:**
  - Resized the sliding joint with a −0.0025 in interference allowance, resulting in a firm press-fit that prevents the cable holder from sliding out unintentionally.
  - Increased the internal thread diameter by 0.02 in relative to the male screw shaft. The screw now rotates freely and clamps onto the desk edge, though over-torquing must be avoided to prevent stripping the printed threads.

### 7.1 CAD Modeling and Design Steps (3 Components)

1. **Part 1:** Main Mounting Frame
   <img width="975" height="620" alt="image" src="https://github.com/user-attachments/assets/9ca753b3-865f-436f-aa9b-d0877a673898" />

2. **Part 2:** Single-Slot Cable Holder and Lock Slide
   <img width="974" height="565" alt="image" src="https://github.com/user-attachments/assets/f1f284a7-e396-4a96-9302-9880c29e97b3" />

3. **Part 3:** 3/8"-16 UNC Clamping Screw
<img width="974" height="625" alt="image" src="https://github.com/user-attachments/assets/d94314b2-384b-41b1-a2e8-8a52ec7139f1" />

---

## 8. Presentation

- **Peer Feedback:** I will present the initial CAD model and FDM test prints to the class next week to gather feedback on clamp stability, cord insertion ease, and sliding fit tolerances before starting Part 2.

---

# MEGR 2156/7 L3D – Final Project, Part 2

# Desk Cable Management System: Prototype Refinement and Final Documentation

## 1. Peer Feedback and Individual Reflections

<img width="768" height="1024" alt="Brayan_Page 1" src="https://github.com/user-attachments/assets/ec38b286-6d9d-4b40-8068-e1636263df1d" />
<img width="768" height="1024" alt="Brayan_Page 2" src="https://github.com/user-attachments/assets/6a4c299c-07b6-48a7-af7a-ae66b8fddb82" />

<img width="768" height="1024" alt="Derek_Page 1" src="https://github.com/user-attachments/assets/34e3c703-7cfe-4ae6-8b7d-d3deba7fe685" />
<img width="768" height="1024" alt="Derek_Page 2" src="https://github.com/user-attachments/assets/9059f46c-93f5-4b93-a7bb-9d1e2378c476" />

<img width="768" height="1024" alt="Noah_Page 1" src="https://github.com/user-attachments/assets/e32cc7a8-43db-420b-b6b1-92b1ff2ed2b3" />
<img width="768" height="1024" alt="Noah_Page 2" src="https://github.com/user-attachments/assets/ff0f664d-a9fa-4e30-8906-a775f73600d4" />



### 1.1 Individual Reflections on Peer Feedback

- **Slide-Fit vs. Press-Fit Tolerances:** All three reviewers (Brayan, Derek, and Noah) noted that the sliding piece holding the cables might come loose when pulling larger cords. In practice, cables are rarely pulled straight out at a 180-degree angle; angled tension creates friction between the slot wall and the lock slide wall that naturally prevents the slide from backing out. However, to ensure maximum security, I chose to tighten the tolerance into a firm press-fit rather than leaving it as a loose slide fit.

- **Easier Cord Installation:** Noah suggested finding a way to insert cables without removing parts. Because my primary design goal is to lock cables down securely so they cannot fall off the desk, changing to an open snap-in gap would compromise retention. Keeping the enclosed lock-slide mechanism prioritizes cord security over tool-free drop-in loading.

- **Design Size and Modularity:** Brayan suggested making the organizer longer to hold more cables without needing multiple pieces. While the initial single-slot print was only a proof of concept, I expanded the refined model to hold 3 cable slots per base. By printing two modular bases, the system holds 6 cables, and users can easily print additional modules to expand capacity as needed.

- **Manufacturing Process Split (SLA vs. FDM):** Everyone liked the threaded bolt clamp for attaching the organizer to the desk. To optimize performance, I split the manufacturing methods: the cable-holding base and clamping screw are printed using SLA (Form 4) to achieve tight, durable thread tolerances, while the lock slides are printed using FDM to dial in the exact interference tolerance needed for a reliable press-fit.

---

## 2. Prototype Refinement and Tolerance Testing

### 2.1 Design Modifications

1. **Increased Desk Clamp Capacity:** The initial prototype only fit desks thinner than 1.0 in. I increased the clamp jaw gap to 1.5 in so the organizer fits a wider variety of standard desks and tabletops.

2. **Thread Durability Upgrade (FDM to SLA):** Although the FDM-printed 3/8"-16 UNC threads functioned during initial tests, applying higher clamping torque risked stripping the plastic layers. Transitioning the base and screw to SLA resin provides smoother thread engagement and higher strength under tightening loads.

3. **Multi-Slot Expansion:** Scaled the base from a single test slot to a 3-slot module, allowing 6 cables across two printed units.

### 2.2 Lock Slide Tolerance Testing (FDM)

To find the ideal press-fit between the FDM lock slide and the SLA base slot, I printed and measured multiple tolerance test pieces.

- **Nominal CAD slot width:** 0.5400 in
- **Actual SLA measured slot:** 0.5160 in

| Test Iteration | CAD Tolerance Offset | CAD Lock Width | Actual Measured Width | Fit Result |
|---|---:|---:|---:|---|
| Test 1 | 0.000 in (0k) | 0.5400 in | 0.5130 in | Too small; did not provide enough friction to lock. |
| Test 2 | +0.020 in (20k) | 0.5200 in | 0.5100 in | Slide fit. |
| Test 3 | +0.030 in (30k) | 0.5100 in | 0.4955 in | Still slightly loose inside the 0.5160 in slot. |
| Final Fit | −0.010 in (−10k) | 0.5400 in | 0.5235 in | Optimal press-fit. |

**Optimal Press-Fit:** Creates a 0.0075 in interference fit against the 0.5160 in SLA base slot, locking securely in place.
<img width="976" height="731" alt="image" src="https://github.com/user-attachments/assets/9d2042e2-c040-4d92-91b3-f3e2632d4711" />

---

## 3. Final Prototype Documentation

### 3.1 Design Steps: Cable Holding Base (SolidWorks)

1. **Base Block Extrusion (Boss-Extrude1):** Sketch a 1.50 in × 1.75 in rectangle and extrude it 2.00 in blind to form the main block.
<img width="975" height="680" alt="image" src="https://github.com/user-attachments/assets/ba83dd27-c3fb-401d-90dd-91caf98561c5" />

2. **Desk Clamp Jaw Cutout (Cut-Extrude1):** Sketch a 0.50 in wide pocket offset 0.25 in from the top and 0.25 in from the bottom, then cut Up To Next to create the C-clamp opening for the desk edge.
<img width="975" height="599" alt="image" src="https://github.com/user-attachments/assets/5ca774ec-155a-425e-857c-5c68bdad6c1b" />

3. **Cable Channel Opening (Cut-Extrude2):** Sketch a Ø0.33 in profile and cut Up To Next to form the vertical cable pass-through channel.
<img width="975" height="655" alt="image" src="https://github.com/user-attachments/assets/7d26d206-1426-43ae-9007-58540bffd0e8" />

4. **Parametric Slot and Gap Control ("G" and Cut-Extrude3):** Create global variable "G" = 0.08 (0.08 in) in Equations to control the maximum slot gap, link sketch dimensions (D1@Sketch4 through D5@Sketch4) to "G", and extrude-cut 1.25 in blind to shape the lock-slide slot.
<img width="975" height="566" alt="image" src="https://github.com/user-attachments/assets/e9aeef08-a4f8-4483-ba4d-7974fb9b315e" />

5. **Clamp Screw Holes (Cut-Extrude4):** On the bottom clamp jaw (offset 1.00 in), sketch two Ø0.43 in holes spaced 0.50 in from the top and bottom edges and cut Up To Next.
<img width="975" height="566" alt="image" src="https://github.com/user-attachments/assets/2911bfbf-0b41-4b77-9bca-66d572d6689c" />

6. **Thread Feature (Thread1 / Thread2):** Add threads to the clamping screw holes (configured in SolidWorks using Extrude thread, Up To Selection with a 0.03 in offset) for the desk clamping screws.
<img width="975" height="631" alt="image" src="https://github.com/user-attachments/assets/2541c8de-48c1-4c0c-a865-ae4b0c3d4ba5" />

7. **Linear Pattern Expansion (LPattern2 and LPattern3):** Pattern the slot, cable channel, and clamp features linearly to expand the single-slot test base into a 3-slot Cable Holding Base for the final assembly.
<img width="975" height="574" alt="image" src="https://github.com/user-attachments/assets/76161ee7-5d6b-4370-a882-5632c664813e" />

### 3.2 CAD Assembly
<img width="975" height="567" alt="image" src="https://github.com/user-attachments/assets/fefc8f94-c3f0-46de-b69a-738f3012a258" />

#### Component Overview

- **3-Slot Mounting Base (SLA):** Clamps onto desk edges up to 1.5 in thick and houses three cable channels with precision mating slots.
- **3/8"-16 UNC Clamping Screw (SLA):** Threads smoothly into the mounting base to lock the frame securely onto the desk corner without stripping.
- **Lock Slides (FDM):** Custom-toleranced inserts (0.5235 in actual width) that press-fit into the base slots to trap and organize individual cables.
<img width="975" height="732" alt="image" src="https://github.com/user-attachments/assets/79df76d9-ff59-404e-b630-21aecc41aff9" />

### 3.3 SLA Printing Process (Formlabs PreForm and Form 4)

To ensure high dimensional accuracy and smooth, durable threads, the **two 3-slot Cable Holding Bases** and **four Clamping Screws** were prepared in **Formlabs PreForm** for the **Form 4** printer.

#### 1. Build Plate Layout and Orientation

- **Parts Printed:** 2× Cable Holding Bases (3-slot) and 4× Threaded Clamping Screws arranged compactly within the allowed ≤ 1/4 build plate footprint.
- **Part Orientation:** All components were angled slightly off vertical on rafts so overhangs self-support and resin drains cleanly without trapping cups.
- <img width="1226" height="812" alt="Isometric view" src="https://github.com/user-attachments/assets/cb8722b0-a0d6-4027-8af0-19fbaa3d861c" />


#### 2. Support Strategy and Critical Feature Protection

Using PreForm's support tools (`0.60 mm` touchpoint size, `1.00` overhang density at `18.00°` angle, `1.39` stabilization density, and internal supports disabled on critical mating zones), supports were placed strictly on non-functional exterior surfaces:

- **No Supports on Slide Slots:** The three cable-locking slots were oriented upward and kept completely free of support touchpoints to preserve the exact **0.5160 in** slot width needed for the FDM lock-slide press-fit.
- **No Supports on Male Screw Threads:** The clamping screws were supported exclusively beneath their hex heads, leaving the external threads clean and smooth.
- **No Supports Inside Base Threads:** Internal threads inside the base clamp jaw were kept clear of support pillars to prevent thread damage or binding.
- <img width="1355" height="947" alt="Supports Settings" src="https://github.com/user-attachments/assets/d3cb7c2d-7fc1-4638-b454-a25eb564f7ac" />

- <img width="692" height="815" alt="No Support On Slide slots" src="https://github.com/user-attachments/assets/3f2e00b4-b9a2-44a5-844f-07e8f776ad7d" />

- <img width="709" height="477" alt="No Supports on Screw Thread " src="https://github.com/user-attachments/assets/c32745a5-8aec-41c7-9884-ca3bb0ff1c26" />

- <img width="934" height="794" alt="No supports on Thread at the house " src="https://github.com/user-attachments/assets/df3f389b-ec0e-456b-a3ec-2447ed0bb732" />


#### 3. Print Validation and Summary

PreForm print validation passed with zero **Undersupported Models**, **Minima**, or **Cups**.

| Print Parameter | Value |
|---|---|
| Estimated Print Time | Approximately 3 h 35 m |
| Total Resin Volume | 108.93 mL |
| Model Resin Volume | 78.73 mL |
| Support Resin Volume | 15.41 mL |
| Raft Resin Volume | 14.79 mL |
| Total Touchpoints | 556 |
| Total Layers | 1,180 |

-<img width="221" height="368" alt="Printing Summary" src="https://github.com/user-attachments/assets/c19a6862-a554-439b-b4e2-c73d6a18a940" />


#### 4. Post-Processing

After printing on the Form 4, parts were washed in isopropyl alcohol (IPA) to remove uncured resin, air-dried, UV post-cured according to Formlabs resin specifications, and carefully removed from their rafts before testing thread engagement and press-fit tolerances.


### 3.4 Assembly and Use Instructions

1. **Mount the Base:** Slide the C-clamp frame onto the edge or corner of your desk (up to 1.5 in thick) and hand-tighten the 3/8"-16 UNC clamping screw until secure.
<img width="975" height="1299" alt="image" src="https://github.com/user-attachments/assets/6fa83f39-fadf-405e-951b-f911e72b0a6f" />

2. **Thread the Cable:** Insert the cable through the opening inside the Lock Slide.
  <img width="975" height="732" alt="image" src="https://github.com/user-attachments/assets/a044449f-187f-4d79-baa2-cbc59ecc36f2" />

3. **Position in Base:** Place the cable and lock slide down into an open slot on the Cable Holding Base.
  <img width="426" height="567" alt="image" src="https://github.com/user-attachments/assets/5d27db60-b39a-4a16-b2fe-556e6b9fd660" />

4. **Lock in Place:** Align the lock slide rails with the base slot grooves and press firmly downward until the press-fit seats flush.
<img width="518" height="691" alt="image" src="https://github.com/user-attachments/assets/ebfac129-7ade-4921-8b44-feae791c071a" />

---

## 4. Presentation Preparation (One-Slide and 1-Minute Pitch)

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/3e42901c-11e0-47f7-a2e7-9aefde0f8c94" />



---

## 5. Parametric Design

To make the slot clearance easy to adjust across design iterations without manually editing individual sketch dimensions, I implemented a parametric control in SolidWorks:

- **Global Variable ("G"):** Defined "G" = 0.08 (0.08 in) in the SolidWorks Equations Manager to govern the maximum internal gap inside the lock-slide slot.
- **Linked Sketch Dimensions:** Linked five critical slot dimensions (D1@Sketch4 through D5@Sketch4) directly to "G". Updating "G" automatically updates the entire slot profile symmetrically across all three patterned slots.

<img width="975" height="262" alt="image" src="https://github.com/user-attachments/assets/335a7d6a-aaae-4598-9724-275b91a256b1" />


---

## 6. Final Video (1–2 Minute Script and Shot List)


https://github.com/user-attachments/assets/842dcf27-3987-401c-8454-8d575cda9f1b

## Project Downloads & Resources

### CAD Models & Assembly Files (SolidWorks)
* [Cable Holding Base (3 Slots) (.SLDPRT)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Cable%20Holding%20Base%203%20slots.SLDPRT)
* [Cable Holding Base Prototype (.SLDPRT)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Cable%20Holding%20Base%20Prototype.SLDPRT)
* [Lock Slide (.SLDPRT)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Lock%20Slide.SLDPRT)
* [Clamping Screw (.SLDPRT)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Screw.SLDPRT)
* [Complete Cable Organizer Assembly (.SLDASM)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Cable%20organizer%20Assembly.SLDASM)

### 3D Printing & Slicing Files
* [Formlabs PreForm SLA Print File — Base & Screws (.form)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/SLA%20Lab%20Final%20Project%20House%20and%20Screw.form)

### Presentation & Videos
* [One-Slide Project Summary (.pptx)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Desk_Cable_Management_Detailed_One_Slide.pptx)
* [Part 1 Video — Problem & Initial Concept (.mp4)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Part%201.mp4)
* [Part 2 Video — Prototype Refinement & Demo (.mp4)](https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/finalproject/Part%202.mp4)

---

### References & Resources
1. **NASA Software Engineering Handbook.** *Standard Spiral Life Cycle.*  
   https://swehb.nasa.gov/spaces/7150/pages/16449735/SWE-019+-+Software+Life+Cycle
2. **Wiley (2026).** *Optimization of Process Parameters and Materials Selection in FDM: A Review.*  
   https://onlinelibrary.wiley.com/doi/10.1002/app.70695
3. **Formlabs.** *Form 4 Design Guide.*  
   https://formlabs.com/white-papers/form-4-design-guide/
4. **Formlabs.** *Introduction to Post-Curing Prints.*  
   https://formlabs.com/support/Introduction-to-Post-Curing-Prints/
5. **Formlabs.** *Fit Tuning for Form 4 and Form 4L Generation.*  
   https://formlabs.com/support/Fit-Tuning-Form-4-and-Form-4L-generation/
6. **BRM Lasers.** *Kerf and Kerf Compensation.*  
   https://support.brmlasers.com/en/materials-and-parameters/materials/kerf-and-kerf-compensation
7. **Xometry.** *Design Guidelines for Cut Features.*  
   https://xometry.eu/wp-content/uploads/2023/07/EN-Sheet-Cutting-Design-Guide.pdf
8. **ASME.** *ANSI/ASME B1.1 — Unified Inch Screw Threads (UN and UNR Thread Form).*
9. **ASME.** *ANSI/ASME B4.1 — Preferred Limits and Fits for Cylindrical Parts.*
10. **GitHub Project Repository.** *Full Project Folder (`MHasan-27/Mohammad-Hasan`).*  
    https://github.com/MHasan-27/Mohammad-Hasan/tree/main/docs/finalproject

