# E-ScooterFall

**Helmet Protection in E-Scooter Falls: A Finite Element Parametric Study**

Finite element study of how impact velocity and helmet liner stiffness affect head and brain loading in oblique e-scooter head impacts. Group project for HL2035 (KTH), October 2026.

## Overview

LS-DYNA simulations of a Hybrid III head and upper body, with a helmet (shell + foam liner), a 224-element brain model and an elastic ground. The dummy is given the impact velocity directly, so only the head–ground impact is simulated.

**Study design: 45 cases**

| Parameter | Values |
|---|---|
| Normal velocity (vn) | 4.2, 5.7, 7.2 m/s |
| Tangential velocity (vt) | 1.7, 3.7, 5.7 m/s |
| Liner stiffness (SFO) | 2.5×10⁵, 5×10⁵, 1×10⁶ (baseline), 2×10⁶ |
| Reference | No helmet at each velocity pair |

SFO scales the stress axis of the liner's compression curve, so liner stiffness changes without changing the crush distance.

**Metrics:** HIC15, BrIC, brain MPS and MPS95 (Green–Lagrange strain).

## Main findings

- The helmet reduces HIC15 by about 80% but brain strain (MPS) by only about 10%.
- Normal velocity sets the severity of the impact; friction (μ = 0.3) limits the effect of tangential velocity.
- No single liner stiffness is best: soft liners bottom out, stiff liners rebound, and the best choice depends on impact speed.
- Even with a helmet, injury thresholds are exceeded at e-scooter speeds.

Results are comparisons between cases within one model (single posture, coarse brain mesh, no experimental validation), not absolute injury risk predictions.

## Repository contents

- `simulations/` – LS-DYNA input files and output data (e.g. `nodout`, `glstat`) for the simulated cases
- `reports/` – half-time report

## Running the simulations

The cases are run from `Main_File.k` with LS-DYNA (a licensed solver is required).

## Authors

Giovanni Michele Miranda, Li Wenxuan, Valeria Sabas Ortega

## Reference

Wei et al. (2023), *Head impact kinematics and injury risks during E-scooter collisions against a curb*, Heliyon.
