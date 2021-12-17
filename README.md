# peakAnno

**peakAnno** is a R package to annotate genomic regions (peaks) called/defined from different High-throughput sequencing data, including ChIP-seq, ATAC-seq and MeRIP-seq. 

### install:  
devtools::install_github("https://github.com/BioEpi/peakAnno")

### usage:  
peakAnno(GTF,organism,up,down,peaktype,bedfile,outpath,outfile)  

**GTF**: GTF files are available from https://www.gencodegenes.org/.  
**organism**: the names of specie, such as homo sapiens and Mus musculus.  
**up**: the distance to the upstream of transcription start sites. default value is 2000.    
**down**: the distance to the downstream of transcription start sites. default value is 0.  
**peaktype**: what kind of sequencing data are used to call peaks.  default value is 'm6A'.  
**bedfile**: the name of peaks. The bed file must includes chromosome, start, end and strand (+/-/.). It is better to provide the absolute path of the file.  
| chr | start | end | strand |
| :------: |:------: |:------: |:------: |
| chr1 | 1000 | 1200 | + |
| chr1 | 1300 | 1500 | + |
| chr1 | 2000 | 2200 | + |
| chr1 | 2800 | 3200 | + |
| chr1 | 5000 | 5150 | + |
| chr1 | 6000 | 6350 | + |  

**outpath**: the path is used to save the results.  
**outfile**: the file name is used to save the results.   

### note:  
1.  Here genomic regions are separated to gene promoter/5'UTR/CDS/exon/intron/3'UTR. protein-coding genes have the following features: gene promoter/5'UTR/CDS/intron/3'UTR, while non-coding genes have the following features: gene promoter/5'UTR/exon/intron/3'UTR.  
2.  If your peak file is generated from ATAC-seq/ChIP-seq/Cut&Tag, peaks may be located in protein-coding genes have the following features: gene  promoter/5'UTR/CDS/intron/3'UTR, while non-coding genes have the following features: gene promoter/5'UTR/exon/intron/3'UTR. 
3.  If your peak file is generated from MeRIP-seq, peaks may be located in protein-coding genes have the following features: gene promoter/5'UTR/CDS/3'UTR, while non-coding genes have the following features: gene promoter/5'UTR/exon/3'UTR. 
