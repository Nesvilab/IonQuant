IonQuant is a label free quantification tool for timsTOF PASEF DDA and non-timsTOF (e.g., Orbitrap) data. It supports match-between-runs (MBR) and light/heavy chemical labeling.

<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/Fig1.jpg" width="600"/>

## It is fast
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/fig2.jpg" width="600"/>

## It is accurate and sensitive
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/fig3.jpg" width="600"/>

## System requirements
1. Java 1.8+.
2. `ext` folder from [MSFragger](https://msfragger.arsci.com/upgrader/).

## Download
The latest IonQuant standalone JAR can be downloaded from [here](https://github.com/Nesvilab/IonQuant/releases/download/1.3.0/IonQuant-1.3.0.jar).

## Usage
### GUI
1. Download [FragPipe](http://fragpipe.nesvilab.org/) from [here](https://github.com/Nesvilab/FragPipe/releases/latest).
2. Follow the [tutorial](http://msfragger.nesvilab.org/tutorial_fragpipe.html#lfq-label-free-quantification).

## Command line
```shell
java -jar IonQuant.jar <options> <.d/.mzML/.mzXML/.raw/.pepXML/_quant.csv files>
Options:
        --threads <integer>    # Number of threads. 0 = all logical cores. 
                               # Default: 0
        --mztol <float>        # MS1 tolerance in PPM. Default: 10.0
        --imtol <float>        # 1/K0 tolerance. Default: 0.05
        --rttol <float>        # Retention time tolerance. Unit: min. Default: 0.4
        --seedmz 0/1           # M/Z used as the start point of tracing. 
                               # 0 = calculated M/Z; 1 = observed M/Z. Default: 0
        --minisotopes 1/2/3    # Required isotopes in feature extraction. Default: 2
        --psm <string>         # Path to Philosopher's psm.tsv. One --psm indicates 
                               # one psm.tsv and can have multiple --psm. Optional.
                               # Default: <blank>
        --multidir <string>    # Output directory for the multi experimental result. 
                               # Optional. Default: <blank>
        --normalization 0/1    # Normalize the intensities across all runs. Default: 1
        --minions <integer>    # Minimum ions required in quantifying proteins. 
                               # Default: 2
        --proteinquant 1/2     # Protein quantification algorithm. 1 = top-N, 
                               # 2 = MaxLFQ. Default: 1
        --minfreq <float>      # Minimum required frequency of an ion being selected 
                               # for protein quantification. Default: 0.5
        --tp <int>             # Number of ions used in quantifying each protein. 
                               # If 0, using all ions. Default: 3
        --mbr 0/1              # Perform match-between-runs. Default: 0
        --mbrrttol <float>     # Retention time tolerance used in match-between-runs. 
                               # Unit: min. Default: 1.0
        --mbrimtol <float>     # 1/K0 tolerance used in match-between-runs. Default: 0.05
        --mbrtoprun <integer>  # Maximum number of matched runs in mapping one run. 
                               # Default: 3
        --mbrmincorr <float>   # Minimum required correlation coefficient in matching 
                               # two runs. Default: 0.5
        --ionmobility 0/1      # The data has ion mobility information or not (for 
                               # conventional LC-MS data). Default: 0
        --ionfdr <float>       # Transferred ion false discovery rate threshold. 
                               # Default: 0.01
        --peptidefdr <float>   # Transferred peptide false discovery rate threshold. 
                               # Default: 0.01
        --proteinfdr <float>   # Transferred protein false discovery rate threshold. 
                               # Default: 0.01
        --label <string>       # A pair of light and heavy labelling mass. Can have 
                               # multiple --label for multiple pairs of light and heavy 
                               # labelling, but one peptide can only have one of these 
                               # pairs. Format: <light mass>;<heavy mass>. Optional. 
                               # Default: <blank>
        --requantify 0/1       # Re-quantify unidentified feature based on identified 
                               # feature. Only activate when --label is not empty. Default: 0
```
**Note:** in some high-performance computing (HPC) servers, you may need to explicitly specify `--threads <integer>` in case that Java cannot correctly get the logical core number.

## Publication
<a href="https://www.mcponline.org/content/early/2020/07/02/mcp.TIR120.002048" target="_blank">Fast quantitative analysis of timsTOF PASEF data with MSFragger and IonQuant</a>
<br>
Fengchao Yu, Sarah E. Haynes, Guo Ci Teo, Dmitry M. Avtonomov, Daniel A. Polasky, Alexey I. Nesvizhskii
<br>
Molecular & Cellular Proteomics July 2, 2020, mcp.TIR120.002048; DOI: 10.1074/mcp.TIR120.002048



