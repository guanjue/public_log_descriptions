- The `config.info.txt` includes all parameters used for the Interspec-EpiState-NMF pipeline. The details about the parameters in the `config.info.txt` file can be found [Here](https://raw.githubusercontent.com/guanjue/public_log_descriptions/main/Interspec-EpiState-NMF/parameter.details.md):
```
>>> cat /Path_to_Interspec-EpiState-NMF/input_files/config.info.txt
script_dir	/Users/guanjuexiang/Documents/projects/git/Interspec-EpiState-NMF/scripts/
working_dir	/Users/guanjuexiang/Documents/projects/analysis/test_cormat_NMF_FDR_pipeline_GATA1_Gata1/
#
hg38_gene	GATA1
mm10_gene	Gata1
hg38_gene_set	/Users/guanjuexiang/Documents/projects/git/Interspec-EpiState-NMF/input_files/hg38.gene.bed
mm10_gene_set	/Users/guanjuexiang/Documents/projects/git/Interspec-EpiState-NMF/input_files/mm10.gene.bed
hg38_gene_exp_win_u	50000
hg38_gene_exp_win_d	50000
mm10_gene_exp_win_u	50000
mm10_gene_exp_win_d	50000
#
hg38_state_set	/Users/guanjuexiang/Documents/projects/git/Interspec-EpiState-NMF/input_files/S3V2_IDEAS_hg38_r3_withHg38Mm10prior.state.matched_ct.bed
mm10_state_set	/Users/guanjuexiang/Documents/projects/git/Interspec-EpiState-NMF/input_files/S3V2_IDEAS_mm10_r3_withHg38Mm10prior.state.matched_ct.bed
EpigeneticState_meansignal_mat_file	/Users/guanjuexiang/Documents/projects/git/Interspec-EpiState-NMF/input_files/IDEAS.EpigeneticState.mean_signal_mat.txt
#
random_background_gene_num	100
fdr_threshold	0.1
NMF_component_num	6
```

- Due to the file size (~700 MB), the two epigenetic state bed files: `S3V2_IDEAS_hg38_r3_withHg38Mm10prior.state.matched_ct.bed` and `S3V2_IDEAS_mm10_r3_withHg38Mm10prior.state.matched_ct.bed` need to be generated by using the `get_IDEAS_epigenetic_state_file.sh` script. 

```
>>> # BED file containing data on Human epigenetic states across various cell types
>>> head S3V2_IDEAS_hg38_r3_withHg38Mm10prior.state.matched_ct.bed
CHR	POSst	POSed	AVE	B_B15_50	B_NC14_42	CMP_100246	ERY_S002R5	ERY_S002S3	GMP_100256	HSC_100258	MEP_Donor2596	MK_S004BTH2	MK_S00VHKH1	MONc_C0011IH1	NK_S005YG	T_CD4_S008H1	T_CD8_C0066PH1
chr1	792600	792800	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	792800	793000	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	793000	793200	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	793200	793400	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	793400	793600	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	793600	793800	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	793800	794000	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	794000	794200	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	794200	794400	0	0	2	0	0	0	0	0	0	2	0	0	2
```

```
>>> # BED file containing data on Mouse epigenetic states across various cell types
>>> head S3V2_IDEAS_mm10_r3_withHg38Mm10prior.state.matched_ct.bed
CHR	POSst	POSed	AVE	B_r1	B_r2	CMP_r1	ERY_ad_r1	ERY_ad_r2	GMP_r1	LSK_r1	MEP_r1	MK_fl_r1	MK_fl_r2	MON_r1	NK_r1	T_CD4_r1	T_CD8_r1
chr1	0	200	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	200	400	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	400	600	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	600	800	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	800	1000	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	1000	1200	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	1200	1400	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	1400	1600	0	0	0	0	0	0	0	0	0	0	0	0	0
chr1	1600	1800	0	0	0	0	0	0	0	0	0	0	0	0	0
```
