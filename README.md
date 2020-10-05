# orchard

![Orchard logo](https://github.com/IQcollaboratory/orchard/blob/master/assets/orchard_logo.png)

A major goal of the IQ Collaboratory is the apples to apples comparison of isolated & quiescent galaxies across observations and simulations. To do so, we have developed `Orchard`, a framework for creating mock surveys from simulated volumes.

`Orchard` is currently set up to create SDSS-like surveys from large volume, hydrodynamical simulations. However, the framework is flexible and can be adjusted based on the desired input (semi-analytic models, zoom-in simulations) and output (other surveys such LSST or DESI).

This package is currently intended for IQ internal use. If you are interested in adapting `Orchard` for your own work, please get in touch with Claire Dickey (http://clairedickey.com).

## input

| Required Inputs           | Units | Definition      |
|---------------------------|-------|-----------------|
| ``posvel``          | Mpc,  km/s   | Positions (X, Y, Z) and velocities (Vx, Vy, Vz) for each galaxy in the simulation box |
| ``mass``            | M⊙    | Total stellar mass for each galaxy |
| ``spectra``         |       | Synthetic spectra generated for each galaxy |
| ``wavelength``      | Å     | Corresponding wavelength array for synthetic spectra |
| ``boxsize``         | Mpc   | Simulation box size |
| ``h``               |       | Value of little h assumed for the simulation |
| ``rmag, gmag``      | SDSS g,r bands | Apparent magnitudes derived from the synthetic spectra | 
| ``d4000``           |       | Dn4000 index measured from the synthetic spectra |
| ``haew``            | Å     | Ha equivalent width measured from the synthetic spectra |
| ``ngals``           |       | Number of resolved galaxies in the simulation box |

| Orchard parameters        | Units |
|---------------------------|-------|
| Host mass threshold       | M⊙    |
| Limiting r magnitude      | apparent mag   |
| Limiting surface brightness | mag / arcsec^2 |
| Noise model      | rmag or g-r + rmag  |

## output

| Outputs          | Units |
|------------------|-------|
| Noise-added spectra | |
| Noise-added Dn4000   |       |
| Noise-added Ha EW    | Å     |
| D_host (projected) | Mpc |
| Quiescent fraction | |
