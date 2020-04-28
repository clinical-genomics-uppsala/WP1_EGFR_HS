# WP1 High Sensitivity analysis of EGFR
1. Clone this git into analysis folder
2. Modify units.tsv to point to your fastq files
3. Run following command after modifications according to your analysis folder and year
snakemake -j 128 --drmaa "-A wp1 -s -p core -n {cluster.n} -t {cluster.time}"  -s /projects/wp1/nobackup/ngs/utveckling/software/HS_Jonas_working_pipeline/swift.hs.Snakefile --directory /projects/wp1/nobackup/ngs/klinik/analys/{Year}/{Analysis folder} --wrapper-prefix git+file://projects/wp1/nobackup/ngs/utveckling/software/github-snakemake-wrappers --use-singularity --singularity-args "--bind /data --bind /gluster-storage-volume --bind /projects  " --latency-wait 30 --cluster-config cluster.json --latency-wait 30
