# 4-Stroke-Single-Cylinder-Engine-Design-and-Analysis
Complete CAD design & FEA simulation of a single-cylinder 4-stroke petrol engine (254cc) in Autodesk Fusion 360 — 8 components modelled, connecting rod FEA: Safety Factor 2.426 on 42,012-node mesh | IIT Madras | ME24B137

> Designed and simulated a complete single-cylinder 4-stroke petrol engine from scratch using Autodesk Fusion 360. Includes full parametric CAD models of all 8 engine components, static stress FEA on the connecting rod, photorealistic renders, and a motion simulation of the complete 4-stroke cycle.

**Made by:** Harshwardhan Uday Patil (ME24B137) | IIT Madras — Mechanical Engineering (2nd Year)

---

## 📸 Project Preview

<!-- Add your best render image here -->
<!-- Drag and drop your Fusion 360 render image into this repo and replace the path below -->

![Engine Assembly Render](images/engine_render.png)

| FEA Result | Section View | Motion Study |
|:---:|:---:|:---:|
| ![FEA](images/fea_result.png) | ![Section](images/section_view.png) | ![Motion](images/motion_study.png) |

---

## 📋 Project Overview

This is a self-initiated portfolio project completed during my 2nd year at IIT Madras. The goal was to design a complete working engine from first principles — starting with engineering calculations, building every part in CAD, assembling them, and finally validating the connecting rod design using Finite Element Analysis (FEA).

### Engine Specifications

| Parameter | Value |
|---|---|
| Engine Type | Single-cylinder, 4-stroke, petrol |
| Bore (cylinder inner diameter) | 70 mm |
| Stroke (piston travel distance) | 66 mm |
| Displacement | 254 cc |
| Compression Ratio | 9:1 |
| Design Speed | 3500 RPM |
| Peak Combustion Pressure | 50 bar |
| Connecting Rod Length | 120 mm |
| Crank Throw (offset) | 33 mm |

---

## ⚙️ Parts Modelled (8 Components)

Every part was built as a separate parametric component in Fusion 360 with real material assignments.

| # | Part | Material | Key Dimensions |
|---|---|---|---|
| 1 | Cylinder Block | Cast Iron | 70mm bore, 110mm OD, 120mm height |
| 2 | Piston | Polished Aluminium | ⌀69.5mm, 60mm tall, 3 ring grooves |
| 3 | Gudgeon Pin | Steel Polished | ⌀20mm OD, ⌀12mm ID, 60mm long |
| 4 | Connecting Rod | Steel Satin (Forged) | 120mm centre-to-centre, I-beam shank |
| 5 | Crankshaft | Steel Polished | 33mm crank throw, counterweights |
| 6 | Cylinder Head | Cast Aluminium | 130×130×45mm, hemispherical chamber |
| 7 | Valves (Intake + Exhaust) | Steel Polished | ⌀30mm intake, ⌀26mm exhaust |
| 8 | Valve Springs | Steel Satin | ⌀24mm, 8 turns, 40mm free length |

---

## 🔬 FEA Results — Connecting Rod

Static stress analysis was performed on the connecting rod to verify it would not fail under peak engine load.

### Setup

| Parameter | Value |
|---|---|
| Software | Autodesk Fusion 360 Simulate |
| Study Type | Static Stress |
| Material | Structural Steel |
| Young's Modulus (E) | 200 GPa |
| Yield Strength (Sy) | 250 MPa |
| Applied Force | 19,242 N (peak gas force) |
| Force Location | Inner bore of small end |
| Constraint | Fixed — inner bore of big end |
| Mesh Element Size | 3 mm |
| Total Nodes | 42,012 |
| Total Elements | 26,176 |

### How the 19,242 N force was calculated

```
Peak pressure (P)  = 50 bar = 5,000,000 Pa
Piston area (A)    = π/4 × (0.070)² = 0.003848 m²
Peak force (F)     = P × A = 5,000,000 × 0.003848 = 19,242 N
```

### Result

```
Minimum Safety Factor  = 2.426
Safety Factor Target   = 2.00
Result                 = PASS ✅ — "Strong enough, design will not bend or break"
```

The Safety Factor of **2.426** means the connecting rod can handle **2.4 times** the peak engine load before it would start to permanently deform. This exceeds the standard engineering design target of 2.0.

---

## 🎬 What Was Produced

- ✅ Complete parametric 3D CAD assembly of all 8 components
- ✅ Photorealistic rendered images (full assembly + section view)
- ✅ Motion simulation of complete 4-stroke cycle (720° crank rotation)
- ✅ Static stress FEA on connecting rod with verified Safety Factor
- ✅ Real material appearances applied to every part
- ✅ Section view showing internal mechanism

---

## 🧮 Key Engineering Calculations

All dimensions were derived from first-principle calculations before modelling began.

```
Displacement Volume     = π/4 × D² × L = π/4 × 70² × 66 = 254 cc

Clearance Volume        = Vd / (r-1) = 254 / (9-1) = 31.75 cc

Mean Piston Speed       = 2 × L × N / 60 = 2 × 0.066 × 3500 / 60 = 7.7 m/s
                          (healthy range: 6–12 m/s ✓)

Con-rod ratio (λ)       = r_crank / L_conrod = 33 / 120 = 0.275
                          (target: 0.25–0.33 ✓)

Gudgeon pin diameter    = 0.3 × Bore = 0.3 × 70 = 21mm → used 20mm (standard)

Crank pin diameter      = 0.6 × Bore = 0.6 × 70 = 42mm → used 40mm
```

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Autodesk Fusion 360 | CAD modelling, FEA simulation, rendering, motion animation |
| Fusion 360 Simulate | Static stress FEA |
| Fusion 360 Render | Photorealistic image output |
| Fusion 360 Animation | 4-stroke cycle motion study |

---

## 📁 Repository Structure

```
engine-cad-fea/
│
├── README.md                    ← you are here
│
├── images/
│   ├── engine_render.png        ← add your full engine render here
│   ├── fea_result.png           ← add your FEA safety factor screenshot
│   ├── section_view.png         ← add your section view render
│   └── motion_study.png         ← add a frame from your motion animation
│
├── CAD_Files/
│   ├── cylinder_block.f3d       ← individual part files (export from Fusion)
│   ├── piston.f3d
│   ├── gudgeon_pin.f3d
│   ├── connecting_rod.f3d
│   ├── crankshaft.f3d
│   ├── cylinder_head.f3d
│   ├── valves.f3d
│   ├── valve_spring.f3d
│   └── engine_assembly.f3d      ← complete assembly
│
└── Report/
    └── Engine_Project_Report.docx
```

---

## 📖 How to Open the Files

1. Download and install **Autodesk Fusion 360** (free for students at autodesk.com/education)
2. Sign in with your Autodesk student account
3. In Fusion 360 → File → Open → Upload → select the `.f3d` file
4. The part or assembly opens with full edit capability

---

## 📊 About This Project

This project was done independently (not assigned by a professor) during the 2nd year of the B.Tech Mechanical Engineering program at IIT Madras. It was built as a portfolio project for core mechanical engineering internship applications.

**What makes this different from typical student projects:**
- All 8 engine components modelled (not just one part)
- Every dimension derived from engineering calculations first
- FEA simulation with real boundary conditions and quantified result (SF = 2.426)
- Complete assembly with motion simulation
- Done solo in 2nd year

---

## 👤 Author

**Harshwardhan Uday Patil**
B.Tech Mechanical Engineering — IIT Madras (2nd Year)
Roll No: ME24B137

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/your-profile)

---

## 📄 License

This project is shared for educational and portfolio purposes.
Feel free to use it as a reference for your own learning.

---

*If this project helped you or you found it interesting, consider giving it a ⭐*
