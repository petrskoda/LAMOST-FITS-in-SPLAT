# LAMOST-FITS-in-SPLAT
Analysis of LAMOST FITS files in SPLAT-VO

This simple Jupyter notebook analyses the strange behaviour of SPLAT--VO when displaying spectrum from LAMOST FITS file.
If the FITS is sent by SSAP server in NATIVE format the SPLAT reads it directly without interpretting the individual lines of pseudoimage 
as described in http://dr2.lamost.org/doc/data-production-description#toc_13

It seems that SPLAT simply sums all 5 rows of pseudoimage and divides by 5
The wavelength is in log of angstrom value but despite the WFITTYPE='LOG-LINEAR' keyword it is not interpreted correctly
as CTYPE1='LINEAR'

So the usual LOGLAMBDA(x)=CRVAL1+(X-CRPIX1) * CD1_1 from 1 to NAXIS1 must be considered as log of lambda
So real lambda=10 ** LOGLAMBDA




