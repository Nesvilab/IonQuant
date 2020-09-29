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