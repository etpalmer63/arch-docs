##########
Hardware
##########

The Cluster One cluster is a high-performance computing (HPC) system operated by ARCH at Johns Hopkins University. As of 2026, Cluster One combines the previously separate Rockfish, DSAI, and EDU clusters into a single unified platform consisting of:

- **45,072+ CPU cores** across approximately 1,000+ nodes
- **GPU nodes:** NVIDIA A100 (40GB/80GB), H100 (80GB), H100-NVL (96GB), and L40S (48GB) accelerators
- **Theoretical peak performance:** 3.3 PFLOps+ (approximately)
- **Parallel file systems:** IBM GPFS (~13 PB usable) and WEKA storage (5 PB)
- **Network fabric:** Mellanox HDR100 (1:1.5 topology)

The following table summarizes the current node types available in Cluster One:

.. list-table::
   :header-rows: 1
   :widths: 15 8 25 12 8 20 12

   * - Partition
     - # Nodes
     - CPU
     - GPU
     - RAM / Node
     - Features
     - Total Cores

   * - Compute
     - 720
     - Intel Xeon Gold 6248R (Cascade Lake)
     - N/A
     - 192 GB DDR4 2933MHz
     - Standard compute nodes
     - 36,864

   * - Compute (Next-Gen)
     - 46
     - Intel Xeon Gold 6448Y (Sapphire Rapids)
     - N/A
     - 256 GB DDR5 4800MHz
     - Standard compute nodes
     - 2,944

   * - Large Memory
     - 25
     - Intel Xeon Gold 6248R (Cascade Lake)
     - N/A
     - 1.5 TB DDR4 2933MHz
     - High-memory nodes
     - 1,200

   * - GPU (A100 40GB)
     - 18
     - Intel Xeon Gold 6248R (Cascade Lake)
     - 4 x NVIDIA A100 40GB
     - 192 GB DDR4 2933MHz
     - GPU compute nodes
     - 864

   * - GPU (A100 80GB)
     - 10
     - Intel Xeon Gold 6338 (Icy Lake)
     - 4 x NVIDIA A100 80GB
     - 256 GB DDR4 3200MHz
     - GPU compute nodes
     - 640

   * - GPU (L40S)
     - TODO
     - Intel Xeon Gold / AMD EPYC
     - NVIDIA L40S 48GB
     - Varies
     - GPU compute nodes
     - TODO

   * - GPU (H100)
     - 16
     - AMD EPYC 9534
     - 4 x NVIDIA H100 80GB
     - 12 GB/core
     - AI/ML workloads
     - TODO

   * - GPU (H100-NVL)
     - 16
     - AMD EPYC 9534
     - 4 x NVIDIA H100-NVL 96GB
     - 12 GB/core
     - AI/ML workloads
     - TODO

   * - Fast Compute (Emerald Rapids)
     - 18
     - Intel Xeon Gold / Platinum 8592+
     - N/A
     - 512 GB TruDDR5 5600MHz
     - High-performance compute nodes
     - 2,304

   * - EDU Nodes
     - TODO
     - TODO
     - TODO
     - TODO
     - Dedicated for class instruction
     - TODO

.. note::
   Node specifications may change as new hardware is integrated into the cluster. Specs above reflect the post-merge configuration and may be updated as consolidation proceeds.

Total system core count: **approximately 65,748 cores across ~1000+ nodes** (estimate pending final merge)
Total system GPU count: **approximately 64 L40S, 240 A100, 64 H100, 64 H100-NVL GPUs** (estimate pending final merge)
