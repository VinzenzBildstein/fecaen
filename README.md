# fecaen

fecaen is a MIDAS frontend to read out CAEN x730 digitizers.
The main focus is the DESCANT setup at GRIFFIN using 5 V1730 VME digitizers, but it has also been used for the DT5730 desktop digitizer.

-----------------------------------------
## Compiling

There are two branches of the code, "main" and "c++".
The main branch is set up to work with the MIDAS version used at GRIFFIN, while the c++ branch is set up to work with newer MIDAS versions.
The difference between the branches is that no `extern "C"` blocks are used in the c++ branch.

To compile this code you need to have MIDAS installed as well as the CAENComm, and CAENDigitizer libraries.
The driver for the CAEN digitizer is also needed to use the frontend.

-----------------------------------------
## Running

The frontend can be run in a terminal or screen session and takes `-h <host name>` and `-e <experiment name>` arguments to specify on which host the MIDAS DAQ is running and under what experiment name.

Parameters can be set using the ODB under `/DAQ/params/VX1730/template` and `/DAQ/params/VX1730/custom`.
The parameters at the former location are used as default values for all channels, the latter ones are used to overwrite settings for specific channels.

For an explanation of the parameters, see [here](https://grsi.wiki.triumf.ca/w/index.php?title=CAEN_VX1730).
