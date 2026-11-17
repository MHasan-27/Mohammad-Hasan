# MEGR 2157 L3D – Final Project, Part 1  
## Desk Cable Management System  
### Week 1: Problem Selection & Initial Prototype Design

---

## 1. Project Introduction

### 1.1 Project Overview

For my final project, I selected a **Desk Cable Management System**. The purpose of this project is to design and manufacture a practical solution for organizing cables around a workstation.

Modern workstations contain multiple electronic devices, including computers, monitors, chargers, keyboards, and mobile phones. These devices require different power cables, charging cables, and data connections. When these cables are not properly organized, they can become tangled, fall behind the desk, and create unnecessary clutter.

My proposed solution is a modular desk cable management system that can be attached to the corner or edge of a desk. The system will include a mounting frame, removable cable holders, sliding connections, and an adjustable clamping screw.

The design will initially be manufactured using Fused Deposition Modeling (FDM). After evaluating the dimensional accuracy, surface finish, and mechanical performance of the printed components, I will determine which parts would benefit from SLA printing using the Form 4 printer.

The main goal is to create an affordable, adjustable, durable, and easy-to-use cable management system.

### 1.2 Project Objectives

The primary objectives are:

- Organize multiple cables in one location.
- Prevent cables from falling behind or underneath the desk.
- Provide removable and adjustable cable holders.
- Design a sliding connection that securely holds the cable management components in position.
- Develop a threaded clamping mechanism to secure the entire frame to the corner of the desk.
- Investigate dimensional tolerances between different printed components.
- Evaluate FDM and SLA manufacturing technologies.
- Improve the design through multiple prototype iterations.

### 1.3 Preliminary Design Requirements

| Design Parameter              | Initial Target                          |
|-------------------------------|-----------------------------------------|
| Cable capacity                | 6–8 cables                              |
| Cable diameter                | Approximately 0.12–0.31 in              |
| Mounting location             | Corner or edge of desk                  |
| Mounting method               | Adjustable screw clamp                  |
| Frame connection              | Sliding slot connection                 |
| Screw thread                  | 3/8"-16 UNC                             |
| Screw major diameter          | 0.375 in                                |
| Thread pitch                  | 0.0625 in                               |
| Main manufacturing process    | FDM                                     |
| Precision manufacturing process | SLA Form 4                            |
| Main material                 | PLA or PETG                             |
| Precision components          | Appropriate SLA resin                   |

These dimensions are preliminary design targets and will be modified based on CAD development and physical testing.

---

## 2. Research

### 2.1 Spiral Design Process

The Spiral Design Process is an iterative engineering design method that develops a product through repeated cycles of planning, risk analysis, engineering, and evaluation.

Instead of designing and manufacturing a complete product in one attempt, the engineer develops an initial concept, builds a prototype, tests its performance, identifies problems, and improves the design.

The process consists of four major categories.

#### A. Planning

Planning involves identifying the problem, defining objectives, establishing design requirements, and determining available resources.

For my project, planning includes:

- Identifying the cable organization problem.
- Determining the number and sizes of cables.
- Selecting the mounting location.
- Establishing the overall dimensions.
- Selecting suitable manufacturing technologies.
- Defining the mechanical requirements for the sliding connection and clamping screw.

#### B. Risk Analysis

Risk analysis identifies potential problems that could affect the performance, manufacturing, or reliability of the prototype.

Potential risks for my project include:

- FDM components breaking because of weak layer adhesion.
- Sliding connections becoming too tight or too loose.
- Cable holders failing to retain cables.
- SLA components having dimensional inaccuracies.
- Printed threads wearing out after repeated tightening.
- The clamping screw damaging the desk surface.
- The mounting frame becoming loose under cable tension.

I will address these risks by manufacturing test specimens, evaluating different clearances, and improving the design before producing the final prototype.

#### C. Engineering

Engineering involves developing the CAD model, selecting materials, performing calculations, and manufacturing prototype components.

For this project, engineering activities will include:

- Creating a three-dimensional CAD model.
- Designing the mounting frame and cable holders.
- Developing a sliding slot connection.
- Designing the adjustable clamping screw.
- Selecting suitable thread dimensions.
- Evaluating manufacturing tolerances.
- Producing initial FDM prototypes.
- Determining which components require SLA printing.

#### D. Evaluation

Evaluation determines whether the manufactured prototype meets the established design requirements.

The prototype will be evaluated based on:

- Cable retention.
- Sliding connection fit.
- Thread engagement.
- Clamping performance.
- Dimensional accuracy.
- Ease of assembly and adjustment.
- Overall structural performance.

The results will be documented and used to improve the next design iteration.

#### Application of the Spiral Design Process

I will apply the Spiral Design Process through the following iterations:

| Iteration | Activities                                      | Expected Outcome                        |
|-----------|-------------------------------------------------|-----------------------------------------|
| 1         | Initial concept and CAD model                   | Establish overall geometry              |
| 2         | FDM manufacturing                               | Identify critical components            |
| 3         | Dimensional and mechanical testing              | Identify tolerance problems             |
| 4         | Design modifications                            | Improve fit and functionality           |
| 5         | Select FDM or SLA for each component            | Improve manufacturing quality           |
| 6         | Final manufacturing and evaluation              | Complete functional prototype           |

The Spiral Design Process will allow me to identify problems early, evaluate different solutions, and improve the overall design through repeated testing.

**Reference:** NASA Software Engineering Handbook, Standard Spiral Life Cycle.  
https://swehb.nasa.gov/spaces/7150/pages/16449735/SWE-019+-+Software+Life+Cycle

---

### 2.2 FDM Anisotropic Behavior

#### What Is Anisotropy?

Anisotropy refers to a material having different mechanical properties depending on the direction in which a force is applied.

Fused Deposition Modeling (FDM) is an additive manufacturing process that produces components by depositing melted thermoplastic filament layer by layer.

Because the material is deposited in separate layers and extrusion paths, the mechanical properties of an FDM component are direction-dependent.

Generally, FDM components can have different strengths along the printed filament direction, across the extrusion paths, and perpendicular to the printed layers.

#### How FDM Anisotropy Affects My Design

My cable management system will contain several mechanical features, including sliding connections, cable holders, mounting brackets, and a threaded clamping mechanism.

Anisotropy may affect these components in the following ways:

- **Layer Separation:** The sliding connection or cable holder may crack if forces act perpendicular to the printed layers.
- **Reduced Mechanical Strength:** The clamping mechanism may experience significant forces during tightening. Poor layer orientation could cause the printed housing to separate.
- **Repeated Loading:** Cable holders may experience repeated bending during cable installation and removal.
- **Dimensional Accuracy:** Printing orientation and process settings may affect the dimensions of mating components.

#### Strategies to Reduce Anisotropy

I will consider the following strategies:

- Select an appropriate print orientation based on the direction of the applied load.
- Increase wall thickness in highly stressed areas.
- Use rounded corners to reduce stress concentrations.
- Increase the number of perimeter walls.
- Optimize printing temperature and layer adhesion.
- Select suitable materials based on strength and flexibility.
- Avoid designs that place the primary bending force across weak layer interfaces.

#### Material Selection

I will initially evaluate PLA and PETG.

| Material | Advantages                                      | Limitations                              |
|----------|-------------------------------------------------|------------------------------------------|
| PLA      | Easy to print, inexpensive, and rigid           | Can be brittle                           |
| PETG     | Better ductility and impact resistance          | May require more print-setting adjustments |

PETG is a promising option for cable holders because they may experience repeated bending.  
For the mounting frame, I will evaluate the material based on its stiffness and ability to withstand clamping loads.

#### Proposed FDM Testing

I will print different test specimens to evaluate the effect of wall thickness and print orientation.

| Specimen | Wall Thickness | Purpose                     |
|----------|----------------|-----------------------------|
| A        | 0.047 in       | Evaluate thinner walls      |
| B        | 0.071 in       | Evaluate intermediate walls |
| C        | 0.094 in       | Evaluate thicker walls      |

I will compare flexibility, layer separation, cracking, and overall performance.

**Research reference:** Optimization of Process Parameters and Materials Selection in FDM: A Review, Wiley, 2026.  
https://onlinelibrary.wiley.com/doi/10.1002/app.70695

---

### 2.3 SLA Shrinkage and Dimensional Accuracy

#### What Is SLA Printing?

Stereolithography (SLA) is a resin-based additive manufacturing process that uses light to cure liquid photopolymer resin into solid layers.

The Form 4 printer used in this project uses Masked Stereolithography (MSLA), a related resin-printing technology.

SLA printing is useful for manufacturing small components that require fine details, smooth surfaces, and good dimensional accuracy.

#### Understanding Resin Shrinkage

Shrinkage occurs when liquid photopolymer resin becomes solid through a chemical curing process.

Additional shrinkage can occur during post-curing because the polymer network continues forming additional chemical bonds.

The amount of dimensional change depends on:

- Resin composition.
- Printing orientation.
- Exposure conditions.
- Part geometry.
- Washing procedures.
- Post-curing time and temperature.

There is no single shrinkage percentage that applies to every Form 4 resin. Formlabs designs its material-specific print settings to compensate for expected dimensional changes.

According to Formlabs, typical Form 4 dimensional tolerances in the XY plane include:

| Feature Size   | Typical Dimensional Tolerance          |
|----------------|----------------------------------------|
| 1–30 mm        | ±0.15%, minimum ±0.02 mm               |
| 31–80 mm       | ±0.2%, minimum ±0.06 mm                |
| 81–150 mm      | ±0.3%, minimum ±0.15 mm                |

These are manufacturer-published reference values, not guaranteed tolerances for every resin, orientation, and geometry.

#### How SLA Dimensional Accuracy Affects My Project

The SLA components may include precision locking features and small sliding connectors.

Dimensional inaccuracies could cause:

- Sliding connections to become too tight.
- Locking components to become too loose.
- Difficulty assembling different components.
- Misalignment between mating surfaces.
- Reduced mechanical reliability.

#### Strategies to Improve SLA Accuracy

I will use the following methods:

- Follow the recommended Form 4 resin settings.
- Use the recommended washing and post-curing procedures.
- Measure manufactured components using digital calipers.
- Avoid unnecessarily thin and delicate features.
- Print test specimens before manufacturing final components.
- Adjust the CAD dimensions based on measured results.
- Use Formlabs Fit Tuning when additional dimensional adjustment is needed.

#### Form 4 Build Plate Limitation

The assignment requires the SLA print to occupy no more than approximately one-quarter of the Form 4 build plate.

The Form 4 build area is approximately 38.8 square inches.

Therefore:

