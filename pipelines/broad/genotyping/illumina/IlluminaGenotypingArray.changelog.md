# 1.8.1
2020-07-31

* Have md5sum task stop using phusion/baseimage:latest docker image (it has been removed).  Start using a Google-hosted base image in it's stead.

# 1.8
2020-06-23

* Updated to use new version of GtcToVcf that uses bpm, rather than bpm.csv file.

# 1.7
2020-06-10

*  Updated Picard-Private to support population of additional column 'PIPELINE_VERSION' in ARRAYS_QC table

# 1.6
2020-05-15

* Added  md5sums for red idat, green idat, and vcf input/outputs of the arrays pipeline.
 
# 1.5
2020-03-05

* Allow use of optional 'contamination_controls_vcf' which lets the contamination checking tool 'VerifyIDIntensity' be run in multi-sample mode, improving contamination estimation.  
* Updated Picard to 2.22.0
    * Support multiple sample VCFs in VcfToAdpc tool

# 1.4
2019-12-19

* Updated Picard to 2.21.6
    * Updated CreateVerifyIDIntensityContaminationMetricsFile to handle negative LLK values
    * Corrected float output of GtcToVcf to avoid downstream problems in vcf parsing 
* Improve accuracy of Genotype Concordance with control samples by excluding filtered sites from VCF prior to calling GenotypeConcordance tool.

# 1.3

2019-12-16

* Adjusted memory parameters to avoid Google's new e2 instances because there are not enough machines to satisfy our production use case.

# 1.2
All docker images used by the IlluminaGenotypingArray pipeline are now public

# 1.1

## Bug fix, updated documentation
* Update WDL tasks to use latest Picard docker image
    * Bug fix in VcfToAdpc (Allow for null values of Normalized X and Y intensity)  https://github.com/broadinstitute/picard/pull/1415
* Update documentation

# 1.0
Initial public release of the IlluminaGenotypingArray pipeline

## Detailed Release Notes:

The Broad Data Sciences Platform is dedicated to Open Source software and open science. To support this pipeline and that mission, we have Open Sourced the following tools in Picard: 

* [GtcToVcf](https://software.broadinstitute.org/gatk/documentation/tooldocs/current/picard_arrays_GtcToVcf.php) - Class to convert a GTC file and a BPM file to a VCF file.
* [MergePedIntoVcf](https://software.broadinstitute.org/gatk/documentation/tooldocs/current/picard_arrays_MergePedIntoVcf.php) - Class to take genotype calls from a ped file output from zCall and merge them into a VCF generated by autocall.
* [CollectArraysVariantCallingMetrics](https://software.broadinstitute.org/gatk/documentation/tooldocs/current/picard_arrays_CollectArraysVariantCallingMetrics.php) - Collects summary and per-sample metrics about variant calls in a VCF file.
* [VcfToAdpc](https://software.broadinstitute.org/gatk/documentation/tooldocs/current/picard_arrays_VcfToAdpc.php) - A simple program to convert a Genotyping Arrays VCF to an ADPC file (Illumina intensity data file).
* [CreateVerifyIdIntensityContaminationMetricsFile](https://software.broadinstitute.org/gatk/documentation/tooldocs/current/picard_arrays_CreateVerifyIDIntensityContaminationMetricsFile.php) - A simple program to create a standard picard metrics file from the output of VerifyIDIntensity
