# Occurity Project Notes & Feature Roadmap 🎯

A living notebook for learning, ideas, and future features for our customized Occurity edition.

---

## 🚀 Completed Milestones

- [x] **Local Build Environment**: Set up WSL2 (Ubuntu) with C++, CMake, and Qt6 (Widgets, SVG, Multimedia, OpenGL).
- [x] **One-Click Shortcuts**: Created `build.bat` and `run.bat` for compiling and running seamlessly on Windows.
- [x] **Git Workflow Architecture**:
  - `master`: Pure upstream reference mirror.
  - `more-sloan-options`: Isolated feature branch pushed to GitHub for Pull Request to original author.
  - `my-build`: Personal "All-in-One" branch combining all custom features for daily use.
- [x] **Sloan 3 & Sloan 4 Charts**: Added two new 17-row clinical charts to `charts.xml.example` following strict ETDRS standards.

---

## 💡 Feature Ideas & Backlog

### 1. 🔴🟢 Split Red/Green Duochrome Background
- **Clinical Purpose**: The **Duochrome (Bichrome) Test**. It uses the chromatic aberration of the human eye (red wavelengths focus behind the retina, green focus in front) to check if an eye prescription is over-minused or over-plussed.
- **Feature Requirements**:
  - Split the screen background vertically 50/50: Red on one side, Green on the other.
  - A keyboard shortcut (e.g. `D` for Duochrome) to toggle the split background on/off.
  - A shortcut (e.g. `Shift+D`) to swap the colors (Red on left / Green on right $\leftrightarrow$ Green on left / Red on right).
  - Available across **any** active chart (Sloan, Numbers, Tumbling E, Landolt C, etc.).
- **Implementation Clue**: Occurity's `src/mainsettings.h` already has `hexRed` (`#d20000`) and `hexGreen` (`#00d200`) defined! We can render a two-color background rectangle in `AbstractChart` or `MainWindow`.

---

### 2. 🔀 True Dynamic Sloan Randomization
- **Concept**: Currently, pressing `R` shuffles the positions of the 5 letters already on screen.
- **Improvement**: Generate 5 brand new random letters from the 10 Sloan letters (`C, D, H, K, N, O, R, S, V, Z`) with no repeating letters in the row.
- **Benefit**: Completely eliminates patient memorization during repeated tests.

---

### 3. 🏷️ Explicit ETDRS Group & Branding
- **Concept**: Create an explicit chart group named "ETDRS" in `charts.xml` alongside the Sloan charts.
- **Benefit**: Clearer clinical naming for medical practitioners who look specifically for ETDRS 1, 2, 3, and R.

---

### 4. 👁️ Classic Snellen Pyramid Chart
- **Concept**: The traditional 1862 pyramid layout (`E`, `F P`, `T O Z`, `L P E D`, etc.).
- **Benefit**: Gives the nostalgic doctor's office experience alongside the modern logarithmic charts.

---

## 🛠️ Quick Git Reference for this Project

```powershell
# See your visual branch family tree:
git log --graph --oneline --all --decorate

# Switch to your working all-in-one edition:
git checkout my-build

# Start a brand new, clean feature for the author:
git checkout master
git checkout -b new-feature-name

# Compile your code after edits:
.\build.bat

# Launch Occurity:
.\run.bat
```
