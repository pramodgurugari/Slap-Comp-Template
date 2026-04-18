<img width="1540" height="1900" alt="full_flow" src="https://github.com/user-attachments/assets/54f62ac4-6fb8-45fa-b746-ab09b5c1e413" />






# 🧩 Template Structure – Lighting Slap Comp (Nuke)

This template is organized into **layered, modular sections**, allowing artists to work per-element (FG, MG, BG, FX, etc.) and quickly toggle between **raw render vs slap comp output**.

---

## 🔁 1. Global Flow Control

### **LGT SWITCH SYSTEM (Core of Template)**

* Central controller: `LGT SWITCH NODE`
* Drives all `LGT_SWITCH##` nodes across the script

**Modes:**

* **NON_Edited** → Direct render pass-through
* **Edited** → Full slap comp enabled

👉 This lets artists:

* Compare **raw render vs comp**
* Debug lighting quickly
* Avoid breaking node trees

---

## 📥 2. Input Layer

### A. CG Inputs

  * Character
  * Props
  * Environment
  * FX
  *etc.....

### B. Live Action Plate

* Dedicated **Live Plate section**
* Plate roto support (`Plate Rotos`)

### C. Camera Inputs

* Shot camera
* Matchmove camera
* Reference camera setup

---

## 🧱 3. Scene Breakdown (Per-Layer System)

Each major category is split into consistent blocks:

### 🌍 ENV (Environment)

### 🧍 Character

### 🧱 PROP

### ✨ FX

### 🌫️ ATMOS

### 🖼️ DMP / Sky

Each section contains:

* A / B / C sublayers
* Independent processing chains
* Individual `LGT_SWITCH` nodes
* Deep + Image workflows

👉 This allows:

* Per-element control
* Easy isolation
* Flexible for Lighting comp

---

## 🌑 5. Shadow System

### CG Shadow Build

* Custom `shadow_mask` layer
* Built using:

* Ground shadows
* Contact shadows
* Hand shadow blocks

👉 Designed for:

* Fast shadow integration into plate
* Non-physically accurate but visually effective slap comp

---

## 🌊 6. Deep Workflow Integration

Heavy use of:

* `DeepRead`
* `DeepReformat`
* `DeepRecolor`
* `DeepMerge`

### Purpose:

* Maintain depth accuracy
* Allow proper layering without holdout issues

### Final Conversion:

* `DeepToImage` → converts to 2D comp

---

## 🔄 7. Per-Layer Switching System

Each asset/layer includes:

* `LGT_SWITCH##` node

**Function:**

* Toggle between:

  * Raw render
  * Processed slap comp

👉 This is repeated across:

* ENV
* Character
* Props
* FX
* Atmos

---

## 🎨 8. Lighting & AOV Handling

### AOV Contact Sheet System

Custom node:

* `rm_AOV_Contactsheet`

Supports:

* Diffuse / Specular / SSS
* MultiLight AOVs
* Cryptomatte
* Normals / Depth / Position

👉 Helps artists:

* Debug lighting
* Validate render passes quickly

---

## 🌫️ 9. Atmosphere & Depth Effects

* Depth-based blending
* Defocus node
* Atmos layer integration

Also includes:

* Sphere + ScanlineRender setup
  → Used for **HDRI / environment preview**

---

## 🧾 11. Shot Info Panel

Backdrop includes fields for:

* Artist
* Shot Name
* Sequence
* Frame Range
* Status
* Notes

👉 Designed for:

* Dailies submission
* Team communication

---

## 📤 12. Output System

### Outputs:

* Final slap comp → `Write1`
* AOV Contact Sheet → `Write2`
* MultiLight breakdown → `Write3`

### Settings:

* ACES workflow
* sRGB preview
* Scene linear output

---

## 💡 Key Strengths of This Template

* Fully **modular per Render Layer**
* Strong **deep compositing pipeline**
* Centralized **switch system**
* Built-in **AOV debugging**
* Works for:

  * Live action integration
  * Full CG shots

---

## ⚠️ Important Notes for Artists

* Do **not delete LGT_SWITCH nodes**
* Ensure:

  * Proper AOV exports
  * Deep data is available (if used)
* This is a **slap comp**, not final comp

---

✅ Best Use Cases
 * Lighting lookdev
 * Shot setup
 * Dailies preview
 * Fast iterations
