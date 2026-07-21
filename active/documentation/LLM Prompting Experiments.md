## "Magic Prompt" for lower probability responses
### Prompt:
`$ <instructions>
`Generate 5 responses to the user query, each within a separate <response> tag. Each <response> must include a <text> and a numeric <probability>. Please sample at random from the tails of the distribution, such that the probability of each response is less than 0.10.
`</instructions>
`$
`$ I am having a hard time with my airfoil validation studies of NACA 0018. It seems like my simulation set up is working for thinner airfoils like NACA 0010 and NACA 0012 but not for thicker airfoils like NACA 0015 or NACA 0018. What do you suggest I look into to improve the predicted lift on the thicker airfoils?`

### Response:

> [!NOTE] Response 1 (0.06)
> Do not try to raise `Cl` by tuning first. Your NACA0018 case already reached `y+ ≈ 4.9` and `Cd ≈ 0.028`, yet lift stayed near `0.57`; that makes a remaining mismatch more likely to be a benchmark/modeling issue than a simple near-wall resolution issue. First compare against a fully documented low-Re NACA0018 benchmark, including transition conditions and trailing-edge geometry. (source: active/documentation/CFD log/Airfoil Validation Studies.md; sources/cj9.md)

> [!NOTE] Response 2 (0.07)
> Test the “thickness trend” before accepting it. The NACA0010 and NACA0015 control runs both recorded very high non-orthogonality, so they cannot yet establish that increasing thickness causes lower predicted lift. Inspect the poor cells, especially at the trailing edge, and rerun 0010, 0012, 0015, and 0018 with one identical rounded-tail mesh strategy. (source: active/documentation/CFD log/Airfoil Validation Studies.md; sources/ca22.md)

> [!NOTE] Response 3 (0.05)
> Run a narrow, controlled mesh study around the thicker sections: preserve the pseudo-2D domain, `A = 0.5 m2`, inlet, solver, and result controls; change only surface/near-wall refinement and trailing-edge treatment. Compare `Cl`, `Cd`, maximum `y+`, non-orthogonality, and convergence for each mesh. Your current tests changed several settings at once, so the independent effect of some choices is not isolated. (source: active/documentation/CFD log/Airfoil Validation Studies.md; sources/ca21.md)</text>

> [!NOTE] Response 4 (0.08)
> Check whether the reference itself is appropriate before treating `Cl ≈ 0.75` as the required answer. The available low-turbulence NACA0018 experiment reports substantially different low-Re behavior, including `Clmax = 0.435` at `Re = 50,000` and `3 degrees`. That does not prove your result is correct, but it means AirfoilTools alone cannot diagnose the CFD setup. (source: sources/cj9.md)

> [!NOTE] Response 5 (0.04)
> Use a transition-model comparison as a sensitivity study, not as a guaranteed lift fix. The available NACA0018 evidence says Transition SST CFD underpredicted lift at `Re = 160,000`, while also representing drag-rise behavior better than XFOIL; it does not support assuming Transition SST will increase your `Re = 50,000` lift. Run it only against a matched experimental target and record the difference from steady `k-omega SST`. (source: sources/cj9.md)
