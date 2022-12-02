IonQuant is a fast and comprehensive tool for MS1 precursor intensity-based quantification for timsTOF PASEF DDA and non-timsTOF (e.g., Orbitrap) data. It enables label-free quantification with false discovery (FDR) controlled match-between-runs (MBR). It can also be used for quantification in labelling-based experiments such as those involving SILAC, dimethyl, or similar labelling strategies. IonQuant is available as part of [FragPipe](http://fragpipe.nesvilab.org/).  

### Workflow of peak tracing and quantification
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/Fig1.jpg" width="600"/>

### Workflow of FDR-controlled MBR
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/fig4.jpg" width="600"/>

## It is fast
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/fig2.jpg" width="600"/>

## It is accurate and sensitive

### Quantification accuracy evaluation using the three-organism dataset
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/fig3.jpg" width="600"/>

### Quantified proteins and coefficient of variation (CV)
<img src="https://raw.githubusercontent.com/Nesvilab/IonQuant/master/doc/fig5.jpg" width="600"/>

## System requirements
1. Java 1.9+.
2. `ext` folder from [the latest MSFragger](https://msfragger.arsci.com/upgrader/).
3. The latest FragPipe from [here](https://github.com/Nesvilab/FragPipe/releases/latest)

**Note:** Bruker's native library needs [Visual C++ Redistributable for Visual Studio 2017](https://aka.ms/vs/16/release/VC_redist.x64.exe) in Windows. If you see an error saying cannot find Bruker native library, please try to install the Visual C++ redistibutable.

## Download
The latest IonQuant can be downloaded from [here](https://msfragger.arsci.com/ionquant/).

## Changelog
Changelog can be found from [here](https://github.com/Nesvilab/IonQuant/blob/master/CHANGELOG.md).

## Usage
1. Download [FragPipe](http://fragpipe.nesvilab.org/) from [here](https://github.com/Nesvilab/FragPipe/releases/latest).
2. Follow the [tutorial](https://fragpipe.nesvilab.org/docs/tutorial_lfq.html).

## Tutorials:
- [Using FragPipe coupled with MSFragger and IonQuant to analyze samples](https://fragpipe.nesvilab.org/docs/tutorial_fragpipe.html)
- [Analyzing SILAC (or other labelling coupled with MS1-based quantification) samples with FragPipe](https://fragpipe.nesvilab.org/docs/tutorial_silac.html)
- [Running MSstats using MSstats.csv from IonQuant](https://fragpipe.nesvilab.org/docs/tutorial_msstats.html)

## Publications
<a href="https://doi.org/10.1074/mcp.tir120.002048" target="_blank">Fast quantitative analysis of timsTOF PASEF data with MSFragger and IonQuant</a>
<br>
Fengchao Yu, Sarah E. Haynes, Guo Ci Teo, Dmitry M. Avtonomov, Daniel A. Polasky, Alexey I. Nesvizhskii
<br>
Molecular & Cellular Proteomics, 19 (2020), 1575-1585, DOI: 10.1074/mcp.TIR120.002048

<a href="https://doi.org/10.1016/j.mcpro.2021.100077" target="_blank">IonQuant Enables Accurate and Sensitive Label-Free Quantification With FDR-Controlled Match-Between-Runs</a>
<br>
Fengchao Yu, Sarah E. Haynes, Alexey I. Nesvizhskii
<br>
Molecular & Cellular Proteomics, 20 (2021), 100077, DOI: 10.1016/j.mcpro.2021.100077

