# mriqc_tsne
Quick analysis of MRIQC factors with feature reduction 

Credit to Satra Ghosh for the idea and Oscar Esteban for the code for interacting with the MRIQC api
Intermediate CSVs used in this analysis are available from the Open Science Foundation page for this project at https://osf.io/haf97/ in the OHBM2019-TSNE-Analysis directory.

## Playing with TSNE plots
If you just want to play with TSNE plots of this data, download the files t1_merge_datalad_with_tsnes.csv and bold_merge_datalad_with_tsnes.csv and use the MRIQC_TSNE_run_and_plot notebook. 

 ## Repeting the analysis
If you'd like to repeat the analysis you'l need to download the following files from the OSF repository:
* All.txt
* all_bolds_2018_12_26.csv
* all_bolds_2018_12_26.csv
* all_bolds_2018_12_26.csv

Additionally, you'll need to have [datalad installed](https://www.datalad.org/get_datalad.html), install the uberdataset, and then run the get_datalad_data notebook.

Once you've got all of that, you should be able to run MRIQC_preproc_and_merge and then MRIQC_TSNE_run_and_plot. Generating the TSNE plots at a number of different perplexities is computationally intense, so I've used [ipyparallel](https://ipyparallel.readthedocs.io/en/latest/) to parallelize that.

## Refreshing the analysis
If you've got new json dumps of the MRIQC database (we don't have an automated way to do this setup at the moment, but post an issue if you want new dumps and I'll get them for you) you'll first run the JSON_to_csv notebook, then MRIQC_preproc_and_merge, and finally MRIQC_TSNE_run_and_plot. You can download the data directly from the API with the MRIQC_slow_download notebook, but given the page size limits of HTML requests and the number of records, I've found that this can take a week or more.

