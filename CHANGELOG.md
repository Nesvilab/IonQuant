## 1.10.27 - 2024-05-29
- Require Java 11+
- Calculate intensity and MaxLFQ intensity for MS1 labelling-based quantification
- Fully support MSstatsPTM
- Generate site reports even when there is no PTMProphet site localization information
- Add DiLeu-12 in the isobaric labeling list
- Support both `PeptideProphet Probability` and `Probability` column names
- Add `--msstats` tag 
- Set the default value of 'minions' (minimum number of ions) to 1 (MaxLFQ normalization options) 
- Minor improvements in the MBR mixture modeling module
- Significantly improved the speed of loading Thermo raw files
- Various bug fixes and improvements

## 1.10.12 - 2023-12-19
- Add support for multiple ranks per scan
- Add support for isobaric labelling. Add several new flags for isobaric labelling quantification.
- Significantly improve the ddaPASEF .d loading speed
- Propagate modification localization info to LFQ MSstats files
- Add `--perform-ms1quant` and `--site-reports` flag
- Add `combined_site_` before the site report file name
- Make the MBR ion probability threshold always `>= 0.5`
- Do not generate N/C-term modification site report
- Remove LC-MS file checking
- Various bug fixes and improvements

## 1.9.8 - 2023-05-31
- Add MBR support for the MS1-based label quantification
- Support fractionated data for the MS1-based label quantification
- Add apex RT, CV, and IM columns to `combined_ion.tsv` file
- Add `match type` column to some tsv files
- For FAIMS data, `ion = peptide + charge + cv`
- Print the number of transferred ions to console
- Big improvement on the LDA and mixture distribution modeling
- Overhaul the indexing of PSM, ion, peptide, and protein
- Improve the min scans filtering criteria
- Improve the isotope distribution filtering criteria for MBR
- Various bug fixes and improvements

## 1.8.10 - 2023-01-12
- Fix a crash when the first scan number is a big value
- Various minor bug fixes and improvements

## 1.8.9 - 2022-12-03
- Require Java 9+
- Write compensation voltage to `ion.tsv`
- Add `--modlist` parameter to take a list of mod masses to reduce the discrepancy issue
- Set the default value of `--mbrtoprun` to 10
- Change the default value of `--minexp` to 1
- Change the default values of `--tp` and `--minfreq` to 0
- Change the total intensity from the average of non-zero values back to summation of all isotopic intensities
- Do not write entries from the contaminant proteins to the reprint reports
- Print an error message when there are more than one run in an experiment for label quantification
- Various minor bug fixes and improvements

## 1.8.0 - 2022-05-27
- Require Java 9+
- Generate `combined_ion_label_quant.tsv`, `combined_modified_peptide_label_quant.tsv`, and `combined_protein_label_quant.tsv`
- `MSstats.tsv` supports label quant
- No longer require pepXML files
- Various minor bug fixes and improvements

## 1.7.17 - 2021-11-16
- Improve the logic of picking input spectral files from the folder
- Change an error message to warning
- Various minor bug fixes and improvements

## 1.7.16 - 2021-10-30
- Generate `combined_ion.tsv`, `combined_modified_peptide.tsv`, and `combined_peptide.tsv`
- Generate modification site reports
- Add `locprob` flag to control modification probability threshold (require running PTMProphet beforehand)
- Retire `proteinquant` flag. Add `maxlfq` flag.
- Make `MSstats.csv` support label quant (e.g., SILAC). If there are mixture of light and heavy in on peptide, using `NA` for the intensity
- Always write top-N intensity to protein report. Write MaxLFQ intensity when `maxlfq=1`
- Always use `minions=1` for top-N intensity
- Support using `quantindex` file as input
- Check the integrity of `quantindex` file before reading it
- Improve the total intensity calculation
- Increase the allowed gap of modification mass correction to 4 Da to support the PTM-Shepherd's glycan list
- Improve the total intensity calculation by taking the average of non-zero values to remove the effect due to different isotope counts
- Upgrade some libraries
- Various minor bug fixes and improvements

## 1.7.5 - 2021-07-22
- Require Philosopher 4.0.0+.
- Support `library` and `lib` keywords in the experiment names to recognize library runs. Library runs will always be used as donor runs.
- Support prmPASEF.
- Disable MBR when there is only one run.
- Change the default value of `mbrtoprun` to 100000.
- Add `filelist` flag to bypass command length limitation in Windows.
- Various minor bug fixes and improvements.

## 1.5.5 - 2021-03-02
- Add high-field asymmetric waveform ion mobility spectrometry (FAIMS) support.
- Remove `log10(KL_negative_1)`, `log10(KL_negative_2)`, `log10(intensity) diff`, `correlation between runs`, `matched run percentage` scores to make the LDA modeling more robust.
- Improve mixture distribution modeling.
- Add `minscans` parameter.
- Improve peak tracing with resampling and Savitzky–Golay smoothing.
- Substract background noise from the intensity.
- Improve the normalization to be more robust.
- Generate `protein_label_quant.tsv`. 
- Use log-ratio median to normalize peptide and protein log-ratios in label quantification.
- Always use `minions = 1` for the `top-N` protein intensity calculation algorithm (`proteinquant = 1`).
- Using the log-ratios within `[-log2(1.5), log2(1.5)]` to perform normalization in label quant.
- Suppress a warning due to a bug in Philosopher.
- Various bug fixes and improvements.

## 1.4.6 - 2020-11-09
- Don't stop when there is a protein with no PSM. When protein FDR threshold is 1, there may be proteins with no PSM passing 1% PSM FDR.
- Change O's mass to 255.15829.
- Remove a randomness from the algorithm.

## 1.4.4 - 2020-09-29
- Supporting SILAC and other isotopic labeled data.
- Print more information about match-between-runs.
- Add `--writeindex` to write index to disk for further usage.
- Add `--spectraldir` option to take spectral files' directories as input.
- Add `--excludemods` option to exclude certain modifications in protein quantification.
- Add `--minexps` option.
- Change the default value of `--proteinquant` to 2.
- Change the default value of `--mbrmincorr` to 0 and use `>` for it.
- Change the default values of `--proteinfdr` and `--peptidefdr` to 1.
- Change the default value of `--requantify` to 1.
- Change the default value of `--mbrtoprun` to 10.
- Changing `--proteinquant` to 1 and `--minexps` to 1 if there are less than 3 experiments.
- Implement a module writing `combined_protein.tsv` from scratch.
- If the experiment names do not have `_`, using `<exp>_<expIdx>` instead.
- Upgrade timsTOF data reading API to 2.7.0.
- Various bug fix and optimization.

## 1.3.0 - 2020-06-05
1. Implement the MaxLFQ protein intensity calculation algorithm. Add `--proteinquant 1/2` to control the used algorithm.
2. Add a Pearson correlation coefficient to measure the similarity of light and heavy `RT-intensity` profile in label quantification.
3. Add more info to label quantification output.
4. Change `> minFreq` to `>= minFreq`
5. Various bug fixes and improvements.

## 1.2.0 - 2020-05-21
1. Support non-timsTOF (e.g., Orbitrap) data. 
2. Support match-between-runs.
3. Support match-between-runs' ion, peptide, and protein level false discovery rate control.
4. Support isotope labeling based quantification. (beta)

## 1.1.0- 2020-05-15
1. Add new parameters.
2. Make the quantification more accurate.
3. Various bug fix and optimization.

## 1.0.0 - 2020-04-24
1. The first version after renaming IMQuant to IonQuant.
