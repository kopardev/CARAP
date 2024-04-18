## CARLISLE development version

- Bug fixes (#127, @epehrsson)
    - Removes single-sample group check for DESeq.
    - Increases memory for DESeq.
    - Ensures control replicate number is an integer.
    - Fixes FDR cutoff misassigned to log2FC cutoff.
    - Fixes `no_dedup` variable names in library normalization scripts.
- Containerize rules that require R (`deseq`, `go_enrichment`, and `spikein_assessment`) to fix installation issues with common R library path. (#129, @kelly-sovacool)
    The `Rlib_dir` and `Rpkg_config` config options have been removed as they are no longer needed.

## CARLISLE v2.5.0
- Refactors R packages to a common source location (#118, @slsevilla)
- Adds a --force flag to allow for re-initialization of a workdir (#97, @slsevilla)
- Fixes error with testrun in DESEQ2 (#113, @slsevilla)
- Decreases the number of samples being run with testrun, essentially running tinytest as default and removing tinytest as an option (#115, @slsevilla)
- Reads version from VERSION file instead of github repo link (#96, #112, @slsevilla)
- Added a CHANGELOG (#116, @slsevilla)
- Fix: RNA report bug, caused by hard-coding of PC1-3, when only PC1-2 were generated (#104, @slsevilla)
- Minor documentation improvements. (#100, @kelly-sovacool)
- Fix: allow printing the version or help message even if singularity is not in the path. (#110, @kelly-sovacool)

## CARLISLE v2.4.1 
- Add GitHub Action to add issues/PRs to personal project boards by @kelly-sovacool in #95
- Create install script by @kelly-sovacool in #93
- feat: use summits bed for homer input; save temporary files; fix deseq2 bug by @slsevilla in #108
- docs: adding citation and DOI to pipeline by @slsevilla in #107
- Test a dryrun with GitHub Actions by @kelly-sovacool in #94

## CARLISLE v2.4.0
- Feature- Merged Yue's fork, adding DEEPTOOLS by @slsevilla in #85
- Feature- Added tracking features from SPOOK by @slsevilla in #88
- Feature - Dev test run completed by @slsevilla in #89
- Bug - Fixed bugs related to Biowulf transition

## CARLISLE v2.1.0
- enhancement
- update gopeaks resources
- change SEACR to run "norm" without spikein controls, "non" with spikein controls
- update docs for changes; provide extra troubleshooting guidance
- fix GoEnrich bug for failed plots

## CARLISLE v2.0.1
- fix error when contrasts set to "N"
- adjust goenrich resources to be more efficient

## CARLISLE 2.0.0
- Add a MAPQ filter to samtools (rule align)
- Add GoPeaks MultiQC module
- Allow for library normalization to occur during first pass
- Add --broad-cutoff to MACS2 broad peak calling for MACS2
- Create a spike in QC report
- Reorganize file structure to help with qthreshold folder
- Update variable names of all peak caller
- Merge rules with input/output/wildcard congruency
- Convert the "spiked" variable to "norm_method
- Add name of control used to MACS2 peaks
- Running extra control:sample comparisons that are not needed
- improved resource allocation
- test data originally included 1475 jobs, this version includes 1087 jobs (reduction of 25%) despite including additional features
- moved ~12% of all jobs to local deployment (within SLURM submission)

## CARLISLE 1.2.0
- merge increases to resources; update workflow img, contributions

## CARLISLE 1.1.1
- patch for gz bigbed bug

## CARLISLE 1.1.0
- add broad-cutoff to macs2 broad peaks param settings
- add non.stringent and non.relaxed to annotation options
- merge DESEQ and DESEQ2 rules together
- identify some files as temp

## CARLISLE 1.0.1
- contains patch for DESEQ error with non hs1 reference samples