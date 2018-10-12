
# PyWBNMts

This is my first github repository. It is planned to use this repository for a python version of current Fortan code of a hydrologic model.
The aim is to recode the Structured Fortran into OOP python. With the opportunity used to make major internal changes to how the code operates.
The main aim is to change the primary loop from the original version of WBNM from Sub Area to Time Step.
That is the current versions of WBNM have always had the primary loop being the Sub Areas within which the time step loops were called. There are many advantages to having the TIMESTEP as the outer loop and the internal loop as the sub area.

The existing Fortran Code is currently housed here: http://wbnm.com.au/index.php/downloads/
With plans to move it to here: https://github.com/tedrigby/wbnm2016 
