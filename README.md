[![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/maurooi/AtmosphericNN/blob/main/LICENSE)
[![arXiv](https://img.shields.io/badge/arXiv-2206.02610-b31b1b.svg)](https://arxiv.org/abs/2206.02610)

# Atmospheric Newtonian Noise data for third-generation underground gravitational-wave detectors
The data contained in this repository are freely available, but if you use them please cite:

> [1] Davide Brundu, Mariano Cadoni, Mauro Oi, Piero Olla, and Andrea Pierfrancesco Sanna, “Atmospheric Newtonian Noise modeling for third-generation gravitational wave detectors”, [_arXiv:2206.02610_](https://arxiv.org/abs/2206.02610)

## Definitions

r<sub>0</sub>: detector depth.

z<sub>0</sub>: roughness of the terrain.

U: wind speed (for the homogeneous and isotropic models).

U<sub>ref</sub>: wind speed at the reference height of 10 m (for the surface layer model).

&psi;: angle spanned by the detector arm and the wind speed directions.

f: frequency.

S<sub>h</sub>: Power spectrum.

## Data format
### [Homogeneous-isotropic turbulence model in the frozen regime](./HI_ft)
We present here a [Mathematica notebook](./HI_ft/Sg.nb) containing the exact solution of the integral (15) in [1].

### [Homogeneous-isotropic turbulence model with finite correlation time](./HI_with_finite_correlation_time)
We present five data files:
1. [`noise_vs_f.dat`](./HI_finite_corr_time/noise_vs_f.dat): contains noise spectra as a function of the frequency, written in the format

   | Detector depth | Energy loss rate per unit mass | Wind speed | Frequency | Noise |
   | :-: | :-: | :-: | :-: | :-: |
   | r<sub>0</sub> (m) | &Escr; (m<sup>2</sup>/s<sup>3</sup>) | U (m/s) | f (Hz) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   For this dataset, the wind speed is taken parallel to the detector arm, so &psi; = 0.
   
2. [`noise_vs_r0.dat`](./HI_finite_corr_time/noise_vs_r0.dat): contains noise spectra as a function of the detector depth, written in the format

   | Energy loss rate per unit mass | Wind speed | Detector depth | Noise |
   | :-: | :-: | :-: | :-: |
   | &Escr; (m<sup>2</sup>/s<sup>3</sup>) | U (m/s) | r<sub>0</sub> (m) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: f = 2 Hz, &psi; = 0.
   
3. [`noise_vs_psi.dat`](./HI_finite_corr_time/noise_vs_r0.dat): contains noise spectra as a function of the angle between the detector arm and the wind speed, written in the format

   | Wind speed | Angle | Noise |
   | :-: | :-: | :-: |
   | U (m/s) | &psi; (rad) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: f = 2 Hz, r<sub>0</sub> = 5 m, &Escr; = 0.1 m<sup>2</sup>/s<sup>3</sup>.
   
4. [`2D_Noise_vs_f_energyloss.dat`](./HI_finite_corr_time/2D_Noise_vs_f_energyloss.dat): contains noise spectra as a function of the frequencies for several values of the energy-loss rate, written in the format

   | Energy loss rate per unit mass | Frequency | Noise |
   | :-: | :-: | :-: |
   | &Escr; (m<sup>2</sup>/s<sup>3</sup>) | f (Hz) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: U = 10 m/s, &psi; = 0.
   
5. [`2D_Noise_vs_f_U.dat`](./HI_finite_corr_time/2D_Noise_vs_f_U.dat): contains noise spectra as a function of the frequencies for several values of the wind speed, written in the format

   | Wind speed | Frequency | Noise |
   | :-: | :-: | :-: |
   | U (m/s) | f (Hz) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: &Escr; = 0.1 m<sup>2</sup>/s<sup>3</sup>, &psi; = 0.

### [Surface layer model](./Surface_layer/)
We present nine data files:
1. [`noise_vs_f.dat`](./Surface_layer/noise_vs_f.dat): contains noise spectra as a function of the frequency, written in the format

   | Detector depth | Roughness | Wind speed at 10 m from terrain | Frequency | Noise |
   | :-: | :-: | :-: | :-: | :-: |
   | r<sub>0</sub> | z<sub>0</sub> (m) | U<sub>ref</sub> (m/s) | f (Hz) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   For this dataset, the wind speed is taken parallel to the detector arm, so &psi; = 0.

2. [`varying_kmax.dat`](./Surface_layer/varying_kmax.dat): contains noise spectra as a function of the frequency computed at different values of the upper cutoff in the integral over the wavenumber k. The data files are written in the format

   | Cutoff | Frequency | Noise |
   | :-: | :-: | :-: |
   | k<sub>max</sub> (m<sup>-1</sup>) | f (Hz) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: r<sub>0</sub> = 5 m, z<sub>0</sub> = 0.1 m, &psi; = 0.

3. [`varying_x3min.dat`](./Surface_layer/varying_x3min.dat): contains noise spectra as a function of the frequency computed at different values of the lower cutoff of the integral over the height x<sub>3</sub>. the data files are written in the format

   | Cutoff | Frequency | Noise |
   | :-: | :-: | :-: |
   | x<sub>3,min</sub> (m) | f (Hz) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: r<sub>0</sub> = 5 m, z<sub>0</sub> = 0.1 m, &psi; = 0.

3. [`noise_vs_r0.dat`](./Surface_layer/noise_vs_r0.dat): contains noise spectra as a function of the detector depth, written in the format

   | Roughness | Wind speed at 10 m from terrain | r0 | Noise |
   | :-: | :-: | :-: | :-: |
   | z<sub>0</sub> | U<sub>ref</sub> (m/s) | r0 (m) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: f = 2 Hz, &psi; = 0.

5. [`noise_vs_psi.dat`](./Surface_layer/noise_vs_psi.dat): contains noise spectra as a function of the angle between the detector arm and the wind speed, written in the format
   | Wind speed at 10 m from terrain | Angle | Noise |
   | :-: | :-: | :-: |
   | U<sub>ref</sub> (m/s) | &psi; (rad) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: r<sub>0</sub> = 5 m, z<sub>0</sub> = 0.1 m, &psi; = 0.
   
6. [`noise_vs_uref.dat`](./Surface_layer/noise_vs_uref.dat): contains noise spectra as a function of the reference wind speed, written in the format
   | Detector depth | Roughness parameter | Wind speed at 10 m from terrain | Noise |
   | :-: | :-: | :-: | :-: |
   | r<sub>0</sub> (m) | z<sub>0</sub> (m) | U<sub>ref</sub> (m/s) | &radic;S<sub>h</sub> (Hz<sup>-1/2</sup>) |
   
   The other parameters are fixed at the values: &psi; = 0.
