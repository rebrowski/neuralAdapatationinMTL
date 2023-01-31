# Analysis-Scripts for ''Single-neuron mechanisms of neural adaptation in the human temporal lobe''

## Data & dependencies
1. Sorted Spiking and behavioral data are stored in `sessions.mat` (~5GB), which can be downloaded here: 
2. Segmented intracranial EEG traces are stored in `ieeg_linked_mastoids_256Hz.mat` (~5GB) and can be downloaded here: 
3. Some scripts in this repository depend on scripts that can be found here: [https://github.com/mormannlab/common_analysis_scripts](https://github.com/mormannlab/common_analysis_scripts)

## Paths and startup.m
It is assumed that there is directory to the data, one for the scripts in this repo, and one for the abovementioned `common_analysis_scripts`. To adjust these paths to your situation, edit `startup.m` and run it once at startup of matlab.

## Behavioral Results & Figure 1B
1. `BehaviorAggregate.m` generates the file `reactiontimes_primed_control_category.mat`.
2. `BehaviorAnalysesAndPlots.m` outputs stats in the MATALB prompt and generate `Figure1B.png`.

## iEEG ERPs
1. `ERPsPlotfigure1C.m` generates the figure `Figure1C.png`
2. `ERPsLatencyAnalysesSITable1.m` prints output to terminal that was used for Supporting Information Table 1. 

## Single units tuning curves
1. `Figure2ASUExamples.m` generates `.tif` files in the `su_examples` subdirectory to the main directory of this script folder. `ospr_su_example_3628_LPHC.tif` is used in Figure 2A. 
2. `CalculateTuningCurves.m` generates `tuningCurvesMin[N]ResponsesPerUnit.mat` where `N`is the minimun number of stimuli the unit responds to.
3. `Figure2BPlotTuningCurves.m` generates  `Figure2BTuningCurvesMin[N]Resps.png` where `N`is the minimun number of stimuli the unit responds to. Note `N = 4` was used for Figure 2B.
4. `PrepareTuningCurvesDataForSpss.m` generates `FiringRatesByRankCondition.csv`, which re-arranges the data in `tuningCurvesMin4ResponsesPerUnit.mat` long format to be further processed wiht SPSS or R for the ANOVA as specified in the manuscript.
5. `firingRatesByRankCondition.sps` is an SPSS script file that does the Condition (primed, control) X Stimulus Rank (1,2,3,4) X Anatomical Region (AM, otherMTL) ANOVA on z-scored and raw firing rates reported in the main text and in Supplementary Table 2. It loads `FiringRatesByRankCondition.csv` and stores the output in SPSS viewer file (`FiringRatesByRankCondition.spv`).

## Single units firing latencies and burst duration

