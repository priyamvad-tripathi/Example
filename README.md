This is a sample script that I made to estimate ellipticities from simulated radio galaxies (true images without any noise or PSF artefacts). <br/>
The galaxy properties: size, flux nad ellipticity are taken from the TRECS catalog and are saved in the pickle file catalog.pkl. <br/>
The scale is chosen based on the antenna array configuaration. <br/> 


I used three different methods to calculate ellipticities: <br />
a. Galsim.HSM module (https://galsim-developers.github.io/GalSim/_build/html/hsm.html) <br />
b. Sf_tools package (https://github.com/sfarrens/sf_tools/blob/master/sf_tools/image/shape.py) <br />
c. ngmix (https://github.com/esheldon/ngmix/blob/master/examples/fitting/fitting.py) <br />
However all the three methods have very high biases. <br />


GalSim is unable to calculate the ellipticities for around 4-5% objects and even if I filter out such objects <br />
the residual bias is at the $10^{-2}$ level. <br />

Sf_tools always returns a positive ellipticty value somehow and I derive the correct sign using GalSim measurements. <br />

ngmix always returns a circular ellipticity ($~10^{-8}$) although the flux estimation is not too off <br />
It might be due to incorrect priors on ellipticty and/or galaxy size <br />
But I am not sure how to make it work for my case <br />


These results are quite suprising since the images I am using do not have any noise or PSF effects <br />
and thus the measurements should be quite accurate. However, this is not the case.


