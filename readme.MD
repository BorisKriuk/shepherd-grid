<div align="center">

# 🐺 Shepherd Grid Strategy

### *Towards Reliable SWARM Interception*

[![arXiv](https://img.shields.io/badge/arXiv-2508.09536-b31b1b.svg)](https://arxiv.org/abs/2508.09536)
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Python 3.7+](https://img.shields.io/badge/Python-3.7%2B-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)]()

---

🎯 **A multi-phase coordination framework employing pack-based behavioral coordination for deterministic UAV target interception through systematic containment and coordinated strike execution.**

---

**Boris Kriuk** · **Fedor Kriuk**

*Hong Kong University of Science and Technology 🇭🇰 · University of Technology Sydney 🇦🇺*

</div>

---

## 🌟 Highlights

> 🏆 **>95% interception success rate** vs. 65% for traditional approaches
>
> ⚡ **~45s median time-to-intercept** vs. ~85s for traditional methods
>
> 📡 **Robust under 60% communication loss** while maintaining >80% success
>
> 📈 **Scales to 20+ simultaneous targets** with 70% success rate

---

## 📄 Abstract

Modern unmanned aerial vehicle threats require sophisticated interception strategies that can overcome advanced evasion capabilities and operate effectively in contested environments. Traditional single-interceptor and uncoordinated multi-interceptor approaches suffer from fundamental limitations including inadequate coverage, predictable pursuit patterns, and vulnerability to intelligent evasion maneuvers.

This paper introduces the **Shepherd Grid Strategy**, a new multi-phase coordination framework that employs **pack-based behavioral coordination** to achieve **deterministic target interception** through systematic containment and coordinated strike execution. The strategy implements a **four-phase operational model** consisting of *chase*, *follow*, *formation*, and *engagement* phases, with dynamic role assignment and adaptive formation geometry.

### 🔑 Three Key Innovations

> **1. Adaptive Phase Transition Mechanisms** — Optimize pursuit behavior based on proximity and mission objectives
>
> **2. Dynamic Role Assignment Systems** — Designate specialized interceptor functions including formation maintenance and strike execution
>
> **3. Predictive Formation Geometry Algorithms** — Create mobile containment grids adapting to target movement patterns

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│                  SHEPHERD GRID STRATEGY                  │
│                                                         │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────┐│
│  │  PHASE 1 │──▶│  PHASE 2 │──▶│  PHASE 3 │──▶│PHASE4││
│  │  CHASE   │   │  FOLLOW  │   │FORMATION │   │ENGAGE││
│  │          │   │          │   │          │   │      ││
│  │ Adaptive │   │ Sustained│   │ Dynamic  │   │Strike││
│  │ Pursuit  │   │ Contact  │   │ Ring     │   │Exec. ││
│  └──────────┘   └──────────┘   └──────────┘   └──────┘│
│                                                         │
│  ┌─────────────────────────────────────────────────────┐│
│  │           DYNAMIC ROLE ASSIGNMENT LAYER             ││
│  │  🔴 Active Interceptor (Striker)                    ││
│  │  🟢 Shepherd Units (Formation Keepers)              ││
│  └─────────────────────────────────────────────────────┘│
│                                                         │
│  ┌─────────────────────────────────────────────────────┐│
│  │        PREDICTIVE FORMATION GEOMETRY ENGINE         ││
│  │  Ring Radius: 40m  ·  Orbit Speed: 30 m/s          ││
│  │  Coverage Radius: 25m  ·  4-Interceptor Grid       ││
│  └─────────────────────────────────────────────────────┘│
└─────────────────────────────────────────────────────────┘
```

---

## ⚙️ Methodology

### 3.1 — Multi-Phase State Transition System

The core mechanism operates through a **deterministic finite state automaton** with four sequential phases governed by temporal and spatial constraints:

```
S(t+1) = f( S(t), Δt, d_avg(t), φ_formation(t) )

where S(t) ∈ { chase, follow, form, engage }
```

Formation readiness requires **≥3 of 4** interceptors within **ε = 15m** of designated slots.

### 3.2 — Dynamic Ring Formation Geometry

A **containment ring** at radius **r = 40m** adapts to target movement with omnidirectional coverage using target-relative coordinates and coordinated circular orbit dynamics at **v_orbit = 30 m/s**.

### 3.3 — Active Interceptor Selection

The primary striker role is dynamically assigned to the interceptor with **optimal engagement geometry** via distance minimization. Predictive pursuit is used at **d > 100m** with a **3.0s time horizon** and **4.5× strike acceleration multiplier**.

### 3.4 — Escape Probability Analysis

The mathematical framework guarantees **zero escape probability** through complete geometric coverage:

```
⋃ B(fᵢ(t), r_intercept) ⊇ B(p_target(t), v_max · Δt)
```

---

## 📊 Experimental Results

### Simulation Parameters

| Parameter | Interceptor | Target |
|:----------|:---:|:---:|
| **Max Velocity** | 50 m/s | 35 m/s |
| **Max Acceleration** | 15 m/s² | 10 m/s² |
| **Operational Space** | 2000 × 2000 × 500 m | — |
| **Interception Radius** | 5 m | — |
| **Trials per Condition** | 100 | — |

### Performance Comparison

| Metric | 🐺 Shepherd Grid | 🔴 Traditional | Δ Improvement |
|:-------|:---:|:---:|:---:|
| **Interception Success** | **>95%** | ~65% | +30 pp |
| **Median Time-to-Intercept** | **~45s** | ~85s | −47% |
| **75th Percentile Intercept** | <60s | >100s | −40% |
| **Energy Efficiency** | Comparable | Baseline | Optimized trajectories |

### Communication Robustness

| Packet Loss | 🐺 Pack-Based | 🔴 Traditional |
|:---:|:---:|:---:|
| **0%** | ~98% | ~65% |
| **20–40%** | 85–90% | 45–50% |
| **60%** | >80% | ~30% |
| **80%** | Degraded | ~10% |

### Scalability (Simultaneous Targets)

| Complexity | Targets | 🐺 Pack-Based | 🔴 Traditional |
|:-----------|:---:|:---:|:---:|
| **Simple** | 1–4 | >85% | ~55% |
| **Complex** | 8–12 | ~75% | <25% |
| **Extreme** | 16–20+ | ~70% | <10% |

---

## 🚀 Getting Started

### Prerequisites

```bash
Python >= 3.7
# Simulation dependencies
numpy
matplotlib
scipy
```

### Quick Start

```bash
# Clone the repository
git clone https://github.com/<your-repo>/ShepherdGrid.git
cd ShepherdGrid

# Install dependencies
pip install -r requirements.txt

# Run the Shepherd Grid Strategy simulation
python shepherd_grid_simulation.py

# Run traditional pursuit baseline
python traditional_pursuit_baseline.py

# Run comparative analysis
python run_experiments.py --trials 100 --method all
```

---

## 📁 Repository Structure

```
ShepherdGrid/
├── 📄 README.md
├── 📄 requirements.txt
├── 📂 src/
│   ├── 🐺 shepherd_grid.py          # Core SGS implementation
│   ├── 🎯 pursuit_traditional.py     # Traditional baseline
│   ├── 🔄 state_machine.py           # Phase transition logic
│   ├── 💫 formation_geometry.py       # Ring formation algorithms
│   ├── 🎖️ role_assignment.py          # Dynamic role allocation
│   └── 📡 communication_model.py     # Degradation simulation
├── 📂 experiments/
│   ├── 📊 comparative_analysis.py     # Pack vs. Traditional
│   ├── 📉 comm_degradation.py         # Communication robustness
│   ├── 📈 scalability_test.py         # Multi-target scaling
│   └── ⏱️ phase_timeline.py           # Behavioral transition analysis
├── 📂 visualization/
│   ├── 🗺️ 3d_trajectory_plot.py       # 3D interception visualization
│   ├── 📊 performance_charts.py       # Result plotting
│   └── 🎬 animation_generator.py      # Mission replay animations
└── 📂 results/
    ├── 📋 tables/
    └── 📈 figures/
```

---

## 🐺 The Four Phases — Visualized

```
    ╔══════════════╗        ╔══════════════╗
    ║   🔍 CHASE   ║───────▶║  👁️ FOLLOW   ║
    ║  τ ≥ 5.0s    ║        ║  Sustained   ║
    ║  Convergence ║        ║  Contact     ║
    ╚══════════════╝        ╚══════╤═══════╝
                                   │
                                   ▼
    ╔══════════════╗        ╔══════════════╗
    ║  💥 ENGAGE   ║◀───────║  🔷 FORM     ║
    ║  Strike!     ║        ║  Ring r=40m  ║
    ║  k* = argmin ║        ║  ≥3/4 ready  ║
    ╚══════════════╝        ╚══════════════╝
```

---

## 📚 Citation

```bibtex
@article{kriuk2025shepherd,
  title     = {Shepherd Grid Strategy: Towards Reliable SWARM Interception},
  author    = {Kriuk, Boris and Kriuk, Fedor},
  journal   = {arXiv preprint arXiv:2508.09536},
  year      = {2025}
}
```

---

## 👥 Contributors

| Name | Affiliation | Role |
|:-----|:------------|:-----|
| **Boris Kriuk** | Hong Kong University of Science and Technology 🇭🇰 | Lead Researcher |
| **Fedor Kriuk** | University of Technology Sydney 🇦🇺 | Co-Researcher |

---

<div align="center">

📬 **Preprint:** [arXiv:2508.09536](https://arxiv.org/abs/2508.09536) &nbsp;|&nbsp; 🔄 **Actively Maintained** &nbsp;|&nbsp; ⭐ **Star if useful!**

---

*"By combining pack-based behavioral coordination with systematic phase progression, the Shepherd Grid Strategy achieves deterministic target capture — setting a new benchmark for autonomous swarm interception."*

</div>
