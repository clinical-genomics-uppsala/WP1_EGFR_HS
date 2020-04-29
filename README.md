# WP1 High Sensitivity analysis of EGFR
1. Clone this git into analysis folder
2. cd analysis folder
2. Modify units.tsv to point to your fastq files
3. Module load slurm-drmaa
4. Start screen
5. Run following command:

snakemake -j 128 --drmaa "-A wp1 -s -p core -n {cluster.n} -t {cluster.time}"  \\
-s /projects/wp1/nobackup/ngs/utveckling/software/HS_Jonas_working_pipeline/swift.hs.Snakefile --directory ./ \\
 --wrapper-prefix git+file://projects/wp1/nobackup/ngs/utveckling/software/github-snakemake-wrappers \\
--use-singularity --singularity-args "--bind /data --bind /gluster-storage-volume \\
--bind /projects  " --latency-wait 30 --cluster-config cluster.json --latency-wait 30
