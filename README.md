# perl-dispersion-dos
Perl scripts to generate phonon dispersion and DOS plots from CASTEP calculations

This repo contains a public copy of the phonon/bandstructure dispersion and DOS plotting scripts from the CASTEP distribution.

These scripts read the `.phonon` or `.bands` output files written by CASTEP containing the phonon and electronic eigenvalues respectively, and generate near publication-quality plots.

Both will generate easy to parse, tabular data, or of invoked with the `-xg` or `-gp` flag will directly invoke either the [xmgrace](https://plasma-gate.weizmann.ac.il/Grace/) or [gnuplot](http://gnuplot.info/) plotting packages.
 
## dispersion.pl

  Example `dispersion.pl -xg -symmetry fcc <seed>.phonon` 
  
   Usage:
   
*   `-xg`           Write a script and invoke GRACE to plot data.
*   `-gp`           Write a script and invoke GNUPLOT to plot data.
*   `-mono`         Create monochrome xmgrace plot
*   `-ps`           Invoke GRACE to plot data and write as a PostScript file.
*   `-eps`          Invoke GRACE to plot data and write as an encapsulated PostScript (EPS) file.
*   `-np`           Do not plot data, write a GRACE script.
*   `-nj`           Do not attempt to perform eigenvector matching on phonon data for joined dispersion plots
*   `-bs`           Read band-structure from <>.castep or <>.bands.
*   `-up`           Extract and plot only spin up from <>.castep or <>.bands (implies -bs).
*   `-down`         Extract and plot only spin down from <>.castep or <>.bands (implies -bs).
*   `-symmetry SYM` Label plot according to Brillouin Zone of SYM=sc/fcc/bcc/hexagonal/tetragonal/orthorhombic....
*   `-expt FILE`    Read experimental data from EXPT and overplot.
*   `-dat`          Reread standard output from previous run and plot.
*   `-ftol f`       Set maximum discrepancy tolerance for phonon branch joining.
*   `-sf s`         Multiply frequencies by scaling factor of s.
*   `-units s`      Convert output to specified units for plotting.
*   `-v`            Be verbose about progres

## dos.pl

   Example `dos.pl -xg -w 10 <seedname>.phonon `

*    `-gp`        Write a script and invoke GNUPLOT to plot data.
*    `-ps`        Invoke GRACE to plot data and write as a PostScript file.
*    `-eps`       Invoke GRACE to plot data and write as an encapsulated PostScript (EPS) file.
*    `-np`        Do not plot data, write a GRACE script.
*    `-bs`        Read band-structure from <>.castep or <>.bands.
*    `-mirror`    Plot spin-polarized electronic DOS using "mirror" plot.
*    `-b w`       Set histogram resolution for binning (eV or cm**-1).
*    `-ir`        Extract ir intensities and model (fundamentals-only) ir spectrum from .phonon.
*    `-raman`     Extract raman intensities and model (fundamentals-only) raman spectrum from .phonon.
*    `-temp T`    Temperature to use (in raman spectrum modelling).
*    `-expt FILE` Read experimental data from EXPT and overplot.
*    `-dat`       Reread standard output from previous run and plot.
*    `-w s`       Set Gaussian/Lorentzian FWHM for broadening.
*    `-lorentz`   Use Lorentzian broadening instead of Gaussian
*    `-units s`      Convert output to specified units for plotting.
*    `-v`         Be verbose about progress
*    `-z`         Print zero-point energy
