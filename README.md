# ROMS-tutorial
This repository is to store ROMS results and python post-processing notebooks

### Job script on Amarel
```
#!/bin/bash

#SBATCH --partition=p_omg_1          # Partition (job queue)

#SBATCH --requeue                 # Return job to the queue if preempted

#SBATCH --job-name= Eddy_variability       # Assign a short name to your job

#SBATCH --nodes=1                 # Number of nodes you require

#SBATCH --ntasks=1                # Total # of tasks across all nodes

#SBATCH --cpus-per-task=10         # Cores per task (>1 if multithread tasks)

#SBATCH --mem=60000                # Real memory (RAM) required (MB)

#SBATCH --time=10:00:00           # Total run time limit (HH:MM:SS)

#SBATCH --output=slurm.%N.%j.out  # STDOUT output file

#SBATCH --error=slurm.%N.%j.err   # STDERR output file (optional)

cd /scratch/$USER

module purge

module load intel/19.0.3 

srun /scratch/$USER/zipper/4.1.5/bin/zipper < my-input-file.in
```
