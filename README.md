## What is IonQuant? 
IonQuant is a label free quantification tool for TIMS-TOF PASEF data.

## Why choose IonQuant?
1. Fast
2. Accurate

## System requirements
1. Java 1.8+.
2. `ext` folder from [MSFragger](https://msfragger.arsci.com/upgrader/).

## Usage
#### GUI
1. Download [FragPipe](http://fragpipe.nesvilab.org/) from [here](https://github.com/Nesvilab/FragPipe/releases/latest).
2. Follow the [tutorial](https://msfragger.nesvilab.org/tutorial_fragpipe_pasef.html#set-quantification).

#### Command line
Download stanalone JAR from [here](https://github.com/Nesvilab/IonQuant/releases/latest).
```shell
java -jar IonQuant.jar <options> <.d/.mzML/.mzXML/.pepXML/_quant.csv files>
Options:
        --mztol <float>        # MS1 tolerance in PPM. Optional. Default: 10.0
        --imtol <float>        # 1/K0 tolerance. Optional. Default: 0.05
        --rttol <float>        # Retention time tolerance. Unit: min. Optional. Default: 0.4
        --plot 0/1             # Plot traced features or not. Optional. Default: 0
        --psm <string>         # Path to Philosopher's psm.tsv. Optional.
        --multidir <string>    # Output dir for the multi experimental result. Optional.
        --minfreq <float>      # Minimum required frequency of a ion being selected for protein quantification. Optional. Default: 0.5
        --tp <int>             # Number of ions used in quantifying each protein. If 0, using all ions. Optional. Default: 0
```
        
