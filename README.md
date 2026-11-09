# Orbit Integration

<p align="center">
  <a href="https://arxiv.org/abs/2606.13787"><img alt="arXiv" src="https://img.shields.io/badge/arXiv-2606.13787-b31b1b.svg"></a>
</p>

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

## Citing

If you use the orbital parameters reported in this repository, please cite [Martínez-García et al. (2026)](https://ui.adsabs.harvard.edu/abs/2026A%26A...714A.206M/abstract).

```bibtex
@ARTICLE{MartinezGarcia2026,
       author = {{Mart{\'\i}nez-Garc{\'\i}a}, Alberto Manuel and {del Pino}, Andr{\'e}s and {van der Marel}, Roeland P. and {Battaglia}, Giuseppina and {{\L}okas}, Ewa L. and {Vitral}, Eduardo and {McKinnon}, Kevin A. and {Watkins}, Laura L. and {Kallivayalil}, Nitya and {Tony Sohn}, Sangmo and {Thomas}, Guillaume F. and {Cardona-Barrero}, Salvador and {Anguiano}, Borja and {Alzate-Trujillo}, Jairo A. and {Nogueras-Lara}, Francisco and {Bennet}, Paul and {Hidalgo-Pinilla}, Adri{\'a}n},
        title = "{Reconstructing the orbits of Milky Way dwarf galaxies: A Large Magellanic Cloud perspective}",
      journal = {\aap},
     keywords = {galaxies: dwarf, galaxies: kinematics and dynamics, Local Group, Magellanic Clouds, Astrophysics of Galaxies},
         year = 2026,
        month = oct,
       volume = {714},
          eid = {A206},
        pages = {A206},
          doi = {10.1051/0004-6361/202661398},
archivePrefix = {arXiv},
       eprint = {2606.13787},
 primaryClass = {astro-ph.GA},
       adsurl = {https://ui.adsabs.harvard.edu/abs/2026A&A...714A.206M},
}
```
