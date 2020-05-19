## What is IonQuant? 
IonQuant is a label free quantification tool for timsTOF PASEF DDA data.

## Why choose IonQuant?
1. Fast
2. Accurate

## System requirements
1. Java 1.8+.
2. `ext` folder from [MSFragger](https://msfragger.arsci.com/upgrader/).

## Download
The latest IonQuant stanalong JAR can be download from [here](https://github.com/Nesvilab/IonQuant/releases/download/1.1.0/IonQuant-1.1.0.jar).

## Usage
#### GUI
1. Download [FragPipe](http://fragpipe.nesvilab.org/) from [here](https://github.com/Nesvilab/FragPipe/releases/latest).
2. Follow the [tutorial](https://msfragger.nesvilab.org/tutorial_fragpipe_pasef.html#set-quantification).

#### Command line
Download stanalone JAR from [here](https://github.com/Nesvilab/IonQuant/releases/latest).
```shell
java -jar IonQuant.jar <options> <.d/.mzML/.mzXML/.pepXML/_quant.csv files>
Options:
        --threads <integer>    # Number of threads. 0 = all logical cores. Default: 0
        --mztol <float>        # MS1 tolerance in PPM. Default: 10.0
        --imtol <float>        # 1/K0 tolerance. Default: 0.05
        --rttol <float>        # Retention time tolerance. Unit: min. Default: 0.4
        --seedmz 0/1           # M/Z used as the start point of tracing. 0 = calculated M/Z; 1 = observed M/Z. Default:
        --minisotopes 1/2/3    # Required isotopes in feature extraction. Default: 2
        --psm <string>         # Path to Philosopher's psm.tsv. One --psm indicates one psm.tsv and can have multiple --psm. Optional. Default: <blank>
        --multidir <string>    # Output dir for the multi experimental result. Optional. Default: <blank>
        --normalization 0/1    # Normalize the intensities across all runs. Default: 1
        --minions <integer>    # Minimum ions required in quantifying proteins. Default: 1
        --minfreq <float>      # Minimum required frequency of a ion being selected for protein quantification. Default: 0.5
        --tp <int>             # Number of ions used in quantifying each protein. If 0, using all ions. Default: 3
```
**Note:** in some high-performance computing (HPC) servers, you may need to explectly specify `--threads <integer>` in case that Java cannot correctly get the logical core number.

## Publication (preprint)
[Fast quantitative analysis of timsTOF PASEF data with MSFragger and IonQuant](https://www.biorxiv.org/content/10.1101/2020.03.19.999334v1)

