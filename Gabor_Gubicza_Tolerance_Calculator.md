# ISO Tolerance Calculator program

by Gabor Gubicza

The program helps Machine Shop Technicians and Mechanical Engineers in translating ISO tolerances into specific tolerance zones in mm and um.

## Principle Operation

- The program takes a String as a user input
- It performs error checking and correction, such as deleting non-alphanumeric characters
- After correction three main parameters are extracted from the String
  - Dimension (Nominal parameter)
  - Hole Tolerance designator (if exists)
  - Shaft Tolerance designator (if exists)
- It parses two ISO Tolerance Tables as Excel Spreadsheets and converts them to JSON objects
- The program then searches separately in the table for the Hole and Shaft parameters: It checks which column does the dimension lie in.
  It checks which row does the Tolerance Designator corresponds to.
- It then extracts the minimum and maximum values, and Console Logs it.

## Block Diagram

![TolCalc](https://github.com/gabor-gubicza/CV/blob/main/Gabor_Gubicza_Tol.Calc-1.1.jpg)

## Output

      Input String:     %132,5/a13tr5H6

      ------ Input Decoding ------

      String is OK:     Max   char: 18
                        Input char: 15
      Original string:  %132,5/a13tr5H6
      New string:       132.5a13tr5H6
      Dimension is:     132.5 mm
      Shaft tolerance:  a13
      Hole  tolerance:  H6



      ---- Output Calculation ----

      Input Dimension: 132.5 mm
      Input Tolerance: a13 ->  Shaft
      Column: 12,      Row: 3
      Deviation:       Max: -1090 um,
                       Min: -460 um
                       Abs: 630 um
      Tolerance zone:  Max: 131.410 mm
                       Min: 132.040 mm

      Input Dimension: 132.5 mm
      Input Tolerance: H6 ->  Hole
      Column: 11,      Row: 27
      Deviation:       Min: 0 um,
                       Max: 25 um
                       Abs: 25 um
      Tolerance zone:  Min: 132.500 mm
                       Max: 132.525 mm

      [Done] exited with code=0 in 0.287 seconds
