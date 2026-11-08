# Orbit Integration

This repository contains orbital parameters for 72 dwarf galaxies in the vicinity of the Milky Way (MW), derived from accurate phase-space coordinates from the literature and six time-evolving gravitational potentials accounting for the mutual interaction of the MW and the Large Magellanic Cloud (LMC). Full details are provided in [Martínez-García et al. (2026)](https://ui.adsabs.harvard.edu/abs/2026A%26A...714A.206M/abstract).

## Repository Structure

Each folder is named after the corresponding potential (e.g. `V23`, `L2M10`) and contains the following files:

- `[potential]_orbital_parameters_MW.csv`: orbital parameters with respect to the MW
- `[potential]_orbital_parameters_LMC.csv`: orbital parameters with respect to the LMC, for its potential satellites
- `[potential]_orbit_MW_1.png`, `[potential]_orbit_MW_2.png`, `[potential]_orbit_MW_3.png`: plots of the orbits of the dwarfs with respect to the MW
- `[potential]_orbit_LMC.png`: plots of the orbits with respect to the LMC for potential LMC satellites
- `[potential]_capture_LMC.png`: plots showing the orbits, trajectory reorientation, and velocity of Grus II and Tucana IV, the possible MW satellites captured by the LMC

  
## Table Structure

Orbital parameters are derived from the set of MC realizations of each galaxy. The central value of each parameter corresponds to the median value, while uncertainties are defined by the 16th and 84th percentiles, respectively. For simplicity, only the column names of the central values are listed below (e.g. `r_peri`); each is accompanied by two additional columns for the lower and upper uncertainties, labeled `_error_down` and `_error_up` (e.g. `r_peri_error_down` and `r_peri_error_up`).

### `[potential]_orbital_parameters_MW.csv`

| Column | Units | Description |
|---|---|---|
| `galaxy` | — | Galaxy name |
| `r_peri` | kpc | Galactocentric distance at the most recent pericentre |
| `t_peri` | Gyr | Time of the most recent pericentre |
| `f_peri` | — | Fraction of MC realizations for which the pericentre is detected |
| `r_apo` | kpc | Galactocentric distance at the most recent apocentre |
| `t_apo` | Gyr | Time of the most recent apocentre |
| `f_apo` | — | Fraction of MC realizations for which the apocentre is detected |
| `E` | km² s⁻² | Specific orbital energy at $t = 0$ |
| `f_bound` | — | Fraction of MC realizations with $E < 0$ at $t = 0$ |
| `t_infall` | Gyr | Infall time, derived from the nominal orbit. Galaxies whose nominal orbit was already within the virial radius at the earliest integration time are assigned a value of `-5.0` (or `-4.0` for `L2M10first`), indicating that their infall occurred before the time span explored in this work 
| `f_vir` | — | Fraction of MC realizations within the MW virial radius at the earliest integration time |

### `[potential]_orbital_parameters_LMC.csv`

| Column | Units | Description |
|---|---|---|
| `galaxy` | — | Galaxy name |
| `r_peri` | kpc | Most recent pericentre with respect to the LMC |
| `t_peri` | Gyr | Time of the most recent pericentre |
| `r_apo` | kpc | Most recent apocentre with respect to the LMC |
| `t_apo` | Gyr | Time of the most recent apocentre |
| `p_LMC` | — | Probability of LMC association |
