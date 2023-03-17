# Galaxy_Project Creating a Bioinformatics Pipeline 

Aim of the pipeline is to take raw NGS sequencing reads from a single patient and output a list of genetic variants most likely to pathogenic and associated with dilated hypertrophic cardiomyopathy 

1. FastQC: This analyses the FASTQ files and ouputs some quality metrics, indicating the quality with a green, yellow and red colour key. 
2.  Map with BWA-MEM: Alignment to the reference genome. This pipeline aligns the reads to GRCh37/ hg19. 
3. Upload .bed file. The .bed file contains the genetic coordinates of the regions of interest. In this pipeline this is the position of the exons in the panel of 'green' genes for dilated hypertrophic cardiomyopathy on PanelApp. 
4. FreeBayes: Variant Calling. Identifies all the positions within the bed files where the sequenced reads don't match the reference genome 
5. Variant Effect Predictor (VEP): Annotates the variants with information such as the gene the variant resides in, the HGVS nomenclature, the variant type, in silico predications of the variant impact. 
6. VCF Filter: Depth> 10 
7. VCF Filter: Alternate Allele Calls >5
8. VCF Filter: gnomAD frequency < 2% 
