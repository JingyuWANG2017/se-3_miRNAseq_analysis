# se-3_miRNAseq_analysis
#fastqdump,fastqc,trim_golare
#trim过的fastq与smallRNA数据库比对，输出map的fastq，去掉smallRNA, tRNA,snoRNA
#比对到smallRNA中，去掉不用的
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q col-0_mRNA_1_trimmed.fq --un col_1_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q col-0_mRNA_2_trimmed.fq --un col_2_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q col-0_mRNA_3_trimmed.fq --un col_3_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q hyl1-2_mRNA_1_trimmed.fq --un hyl_1_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q hyl1-2_mRNA_2_trimmed.fq --un hyl_2_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q hyl1-2_mRNA_3_trimmed.fq --un hyl_3_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q se-3_mRNA_1_trimmed.fq --un se_1_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q se-3_mRNA_2_trimmed.fq --un se_2_small_rna_unmapped.fastq
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_small_rna/small_rna_Chr -q se-3_mRNA_3_trimmed.fq --un se_3_small_rna_unmapped.fastq
##map过的fastq与pri和mature数据库比对，输出Sam文件
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q col_1_small_rna_unmapped.fastq -S col_1_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q col_2_small_rna_unmapped.fastq -S col_2_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q col_3_small_rna_unmapped.fastq -S col_3_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q hyl_1_small_rna_unmapped.fastq -S hyl_1_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q hyl_2_small_rna_unmapped.fastq -S hyl_2_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q hyl_3_small_rna_unmapped.fastq -S hyl_3_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q se_1_small_rna_unmapped.fastq -S se_1_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q se_2_small_rna_unmapped.fastq -S se_2_pri.sam
bowtie -p 1 -l 8 -n 1 /bios-store2/wjy/miRNA-seq_analysis/bowtie1index_ath_primary/ath_microRNA_primary -q se_3_small_rna_unmapped.fastq -S se_3_pri.sam
#mature比对
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q se_1_small_rna_unmapped.fastq -S se_1_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q se_2_small_rna_unmapped.fastq -S se_2_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q se_3_small_rna_unmapped.fastq -S se_3_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q col_1_small_rna_unmapped.fastq -S col_1_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q col_2_small_rna_unmapped.fastq -S col_2_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q col_3_small_rna_unmapped.fastq -S col_3_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q hyl_1_small_rna_unmapped.fastq -S hyl_1_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q hyl_2_small_rna_unmapped.fastq -S hyl_2_mature.sam
bowtie -p 1 -l 8 -n 1 /bios-store1/arabidopsis_reference/bowtie1index_microRNA/ath_microRNA_mature -q hyl_3_small_rna_unmapped.fastq -S hyl_3_mature.sam
#用featureCounts进行计数
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf col_1_pri.sam -o col_1_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf col_2_pri.sam -o col_2_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf col_3_pri.sam -o col_3_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf col_1_mature.sam -o col_1_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf col_2_mature.sam -o col_2_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf col_3_mature.sam -o col_3_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf hyl_1_pri.sam -o hyl_1_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf hyl_2_pri.sam -o hyl_2_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf hyl_3_pri.sam -o hyl_3_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf hyl_1_mature.sam -o hyl_1_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf hyl_2_mature.sam -o hyl_2_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf hyl_3_mature.sam -o hyl_3_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf se_1_pri.sam -o se_1_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf se_2_pri.sam -o se_2_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf se_3_pri.sam -o se_3_pri.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf se_1_mature.sam -o se_1_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf se_2_mature.sam -o se_2_mature.bam
/bios-store1/program/subread-1.5.3-Linux-x86_64/bin/featureCounts -T 8 -t transcript -g transcript_id -a /bios-store2/wjy/miRNA-seq_analysis/dcl1-11/TG/Arabidopsis_thaliana.TAIR10.27_Chr_primicroRNA.gtf se_3_mature.sam -o se_3_mature.bam
#计数结束，下一步用DEGseq分析差异表达


2018年3月2日发现之前用bowtie比对的结果不是很好，今天都改用bowtie2尝试一下
