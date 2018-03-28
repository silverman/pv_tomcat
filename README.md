# TOMCAT_TMY
Code to prepare TOMCAT input based on TMY files

## Usage

The following example generate an input file for FEM calculations called `TOMCAT_input.csv` based on [TMY](https://www.nrel.gov/docs/fy08osti/43156.pdf) and optics input files.

```python
from tomcat_tmy import generate_input

input_df = generate_input(tmy_file, optics_file, out_file = 'TOMCAT_input.csv')
```

## Optics input file format

The optics file details where solar radiaiton is abosorbed within the module and photocurrent changes for different angles of incidence. It must be a `.csv` file with the following column names. Note that all values should include cosine losses from angle of incidence.  
`angle` The angle of incidence for solar illumination in degrees, 0 is normal  
`glass_abs_W/m2` Absorbed energy in the front glass  
`encapsulant_abs_W/m2` Absorbed energy in the front encapsulant  
`cell_abs_W/m2` Absorbed energy in the front cell  
`current_factor` The fractional change in photocurrent from relative to the value corespsonding to the baseline effeciency in the FEM simulation
