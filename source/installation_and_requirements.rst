.. _installation_and_requirements:

Nextflow Pipeline for Nascent-Sequencing Analysis
============================================================

1. Read QC (`FastQC <https://www.bioinformatics.babraham.ac.uk/projects/fastqc/>`_)
2. Adapter Trimming (`Cutadapt <https://cutadapt.readthedocs.io/en/stable/>`_)
3. Trimmed Read QC (`FastQC <https://www.bioinformatics.babraham.ac.uk/projects/fastqc/>`_)
4. Alignment to Reference Genome for BD Rhapsody (`STAR <https://github.com/alexdobin/STAR>`_)
5. Sort and Index Aligned Reads (`SAMtools <http://www.htslib.org/>`_)
6. scBaNdicooT Model Fitting and Nascent Read Calling (`scBaNdicooT <https://github.com/theheking/scBaNdicooT>`_)
7. Generate Nascent Read Count Matrices (`scBaNdicooT <https://github.com/theheking/scBaNdicooT>`_)
8. Generate Summary Reports (`scBaNdicooT <https://github.com/theheking/scBaNdicooT>`_)


Usage 
-----------------------------
> [!NOTE]
> If you are new to Nextflow, please refer to the `Nextflow Documentation <https://www.nextflow.io/docs/latest/getstarted.html>`_ for installation and basic usage instructions.
> Make sure to [test your setup](https://nf-co.re/docs/usage/introduction#how-to-run-a-pipeline) with a simple pipeline with `-profile test` before running the nascent-sequencing analysis pipeline.


First, prepare a samplesheet with your input data that looks as follows:
.. code-block:: csv

   sample,fastq_1,fastq_2
   sample1,/path/to/sample1_read1.fastq.gz,/path/to/sample1_read2.fastq.gz
   sample2,/path/to/sample2_read1.fastq.gz,/path/to/sample2_read2.fastq.gz

Each row represents a sample, with columns for the sample name and paths to the paired-end FASTQ files single-cell nascent BD Rhapsody data.

The contrast file should be a tab-delimited text file with the following format:
.. code-block:: tsv
   sample	condition
   sample1	control
   sample2	treatment

Pipeline Output
-----------------------------
The pipeline will generate the following key output files:
1. Aligned BAM files for each sample.
2. Nascent read count matrices.
3. Summary reports in HTML format.

Citations and Acknowledgements
-----------------------------
Please cite the following publications when using this pipeline in your research:
*  Pending paper
  