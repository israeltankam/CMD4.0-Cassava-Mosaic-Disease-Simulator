# CMD4.0 — Cassava Mosaic Disease (CMD) NetLogo model

**Short description**
CMD4.0 is an agent-based NetLogo model (spatial) that simulates the epidemiology and management of Cassava Mosaic Disease (CMD) in a field. The model represents cassava plants as patches and whitefly vectors as agents. It allows testing of mixed-variety plantings, roguing strategies, replanting strategies, vector dynamics, and economic outcomes (yield and profit).

**Provenance**
- **Created:** June 2022 (original model file: `CMD4.0.nlogo`)
- **Author / Owner:** Israel Tankam
- **Note on provenance:** This model was developed in June 2022 and predates any repository upload. If you use or fork the project, please preserve this creation date in the repository to avoid confusion about authorship or recency.

---

## Model overview
- Spatial, discrete-time model with ticks.
- Patches = cassava plants. Each patch stores:
  - `symptom-severity` (index for CMD symptoms; -1 = empty/susceptible, 0 = latent/healthy, 1–5 symptomatic, -5 = removed/rogued).
  - `variety` (four classes used in the original model: HS, S, R, HR).
  - `symptom-evolution-rate` and `attractivity-to-vectors`.
- Vectors = whiteflies (`breed [ vector a-vector ]`) with attributes `infection` and `ticks-since-here`.
- Processes included:
  - Initialization (`setup`) with variety distribution and initial infected plants/vectors.
  - Vector movement and infection dynamics (`move`, `infect-plant`, `get-infected`).
  - Disease progression on plants (`symptoms-evolve`).
  - Roguing of infected plants (`rogue-infected`).
  - Replanting strategy handling (`replant`) and economic accounting.
  - Plot updates and summary statistics.

---

## Key model parameters (sliders and defaults extracted from the `.nlogo` file)
These match the GUI defaults encoded in the included file:

- `initial-number-of-vectors`: **400**
- `initial-latent-proportion`: **0.10**
- `initial-infected-proportion`: **0.05**
- `initial-infected-vectors`: **0.10**
- `vector-life-expectancy`: **90**
- `probability-of-inoculation`: **0.04**
- `latency-evolution-rate`: **0.02**
- `roguing-rate-1`: **0.0**
- `roguing-rate-2`: **0.0**
- `roguing-rate-3`: **0.005**
- `roguing-rate-4`: **0.005**
- `roguing-rate-5`: **0.10**
- `vector-death-rate`: **0.0**
- `vector-birth-rate`: **0.0**
- `max-vectors-per-plant`: **20**
- `probability-of-acquisition`: **0.22**
- Variety mix (defaults):
  - `percentage-of-HS`: **0.05**
  - `percentage-of-S`: **0.50**
  - `percentage-of-R`: **0.30**
  - `percentage-of-HR`: **0.15**
- Disease progression rates by variety:
  - `disease-progress-rate-HS`: **0.01**
  - `disease-progress-rate-S`: **0.00745**
  - `disease-progress-rate-R`: **0.00278**
  - `disease-progress-rate-HR`: **0.0008**
- Variety costs (per-plant or seedling cost in the model):
  - `cost-HS`: **50**
  - `cost-S`: **75**
  - `cost-R`: **100**
  - `cost-HR`: **150**
- Economic & simulation parameters:
  - `maintenance-cost`: **300000.0**
  - `selling-price`: **380000.0**
  - `seasonal-ticks`: (set in code, default **300**)

> Note: This is a condensed list of the most relevant GUI-controlled parameters. The model includes additional internal values and helper variables.

---

## What the model outputs / plots
- Time-series of vector populations (susceptible vs viruliferous)
- Disease incidence (%) over time
- Number of plants by variety over time
- Mean index of symptom severity (1–5)
- Distribution of plants by symptom severity classes
- Cumulative yield and profit computations (computed per season)

---

## How to run
1. Install NetLogo (model saved as a NetLogo `.nlogo` file). NetLogo 6.x is recommended.
2. Open `CMD4.0.nlogo` in NetLogo.
3. Click **Setup** to initialize the field, then **Go** (toggle) to run the simulation.
4. Adjust sliders in the GUI to explore scenarios (vector pressure, variety mixes, roguing rates, planting strategies).
5. Use NetLogo’s BehaviorSpace if you want to run batches of parameter sweeps.

---

## Suggested citation (if you use this model)
Please cite the repository or contact the author. Example informal citation:

> Tankam, I. (2022). *CMD4.0 — Cassava Mosaic Disease NetLogo model* (June 2022). Repository: `CMD4.0.nlogo`.

(If you publish results based on this model, please include a link to this GitHub repository and the creation date.)

---

## Provenance / authorship / AI disclaimer
- **Created:** June 2022 by Israel Tankam.
- **Authorship:** This model is an original implementation created in June 2022. The repository intentionally includes the creation date and the author's name to make provenance explicit for reviewers and users.

