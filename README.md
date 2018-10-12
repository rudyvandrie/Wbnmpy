
# PyWBNMts

This is my first github repository. It is planned to use this repository for a python version of current Fortan code of a hydrologic model.
The aim is to recode the Structured Fortran into OOP python. With the opportunity used to make major internal changes to how the code operates.
The main aim is to change the primary loop from the original version of WBNM from Sub Area to Time Step.
That is the current versions of WBNM have always had the primary loop being the Sub Areas within which the time step loops were called. There are many advantages to having the TIMESTEP as the outer loop and the internal loop as the sub area.

The existing Fortran Code is currently housed here: http://wbnm.com.au/index.php/downloads/
With plans to move it to here: https://github.com/tedrigby/wbnm2016 

PyWBNMts, will still operate with the parameters as it does in WBNM2017, however the aim is to have an option such that the source of the parameters may be derived automatically from GIS data such as described below. For example rather than the user entering the Area for each sub area, sub area polygons may be used to determine the area.

DESIGNING CLASS OBJECTS for Hydrologic Model:
https://stackoverflow.com/questions/15081542/python-creating-objects 

     A Catchment {Object} includes
                 multiple Sub Area {Object} that include a 
                       Watercourse Segment {Object} and
                       Local Storage {Object}
                       Outlet Storage {Object}
                       Recorded Data {Object}
                 Rainfall Event {Object}

  OBJECT CONCEPT:     
  MODEL      
  MODEL.SubArea
               .PERV
               .PERV.PervHo
               .PERV.PervLR
               .PERV.PervRP
               .PERV.PervVLR
                            .PervIL
               .PERV.PervVRP
                            .PervIL
               
  MODEL.SubAreas.Watercourse
                 Watercourse.NonLinQ
                 Watercourse.Musk
                 Watercourse.Delay
  MODEL.SubAreas.Storage.Local   
  MODEL.SubAreas.Storage.Outlet   
  MODEL.SubAreas.RecordedData   
  MODEL.Rainfall    
  MODEl.Rainfall.Losses    
  MODEl.Rainfall.Recorded   
