---
Created: 2026-07-06
Source: [[va27]]
Tags: #parameters
Target: increase Cp in dynamic stall
Outcome: significant positive effect
---

## Airfoil Maximum-Thickness Position

This `va27` study varies the chordwise position of maximum thickness `xt/c` to understand how moving the airfoil thickness peak fore or aft changes VAWT dynamic-stall performance. (source: sources/va27.md)

- The tested `xt/c` values are `20%`, `22.5%`, `25%`, `27.5%`, `30%`, `35%`, and `40%`. (source: sources/va27.md)
- For thin airfoils (`t/c = 10%` and `12%`) at `lambda = 2.5`, the best performance occurs near `xt/c = 20%`, and shifting the thickness peak downstream monotonically reduces `CP`. (source: sources/va27.md)
- For thicker airfoils (`t/c >= 15%`), the paper reports a polynomial trend with an interior optimum, and that optimum moves downstream as the airfoil becomes thicker. (source: sources/va27.md)
- At `lambda = 2.5`, the reported `xtopt/c` values include `25%` for `t/c = 15%`, `27.5%` for `18%`, `30%` for `21%`, and `35%` for `24%`. (source: sources/va27.md)
- The source explains this as a stall-management effect: for thicker airfoils, moving the thickness peak aft can shorten the adverse-pressure-gradient region and soften trailing-edge stall. (source: sources/va27.md)
- The optimum `xt/c` remains important at `lambda = 3.0`, but the paper says the performance becomes even more sensitive to this parameter because the blade spends less of the cycle in fully separated post-stall conditions. (source: sources/va27.md)

#parameters
