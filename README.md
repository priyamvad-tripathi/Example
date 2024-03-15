This is a sample script that I made to estimate ellipticities from simulated radio galaxies (true images without any noise or PSF artefacts). 
The galaxy properties: size, flux nad ellipticity are taken from the TRECS catalog and are saved in the pickle file catalog.pkl.


I used three differenr methods to calculate ellipticities: 
a. Galsim.HSM module (https://galsim-developers.github.io/GalSim/_build/html/hsm.html) 
b. Sf_tools package (https://github.com/sfarrens/sf_tools/blob/master/sf_tools/image/shape.py)
c. ngmix (https://github.com/esheldon/ngmix/blob/master/examples/fitting/fitting.py)
However all the three methods have very high biases.


GalSim is unable to calulate the ellipticities for around 4-5% objects and even if I filter out such objects
the residual bias is at 10^-2 level.

Sf_tools always returns a positive ellipticty value somehow and I derive the correct sign using GalSim measurements.

ngmix always returns a circular ellipticity (10^-)


