# NCP-AII — NVIDIA Certified Professional: AI Infrastructure

Research date: 2026-09-10

## Exam overview

NCP-AII validates the ability to deploy, configure, and validate advanced NVIDIA AI infrastructure. NVIDIA currently lists a remotely proctored 120-minute exam with 70–75 questions, a US price of $400, English delivery, and two-year certification validity. NVIDIA recommends two to three years of operational data-center experience with NVIDIA hardware.

- [Official NCP-AII certification page](https://www.nvidia.com/en-us/learn/certification/ai-infrastructure-professional/)
- [Official NCP-AII Exam Study Guide (PDF)](https://dam-cdn.nvd.orangelogic.com/AssetLink/8gauup66xn2gv80pu4m166li0bhyytk4.pdf)
- [NVIDIA AI Infrastructure Professional training outline](https://academy.nvidia.com/en/wp-content/uploads/2026/01/AI-Infrastructure-Outline-2026.pdf)
- Exam registration is handled through Certiverse from the official certification page.

## Exam blueprint

| Domain | Weight | Skills to study |
|---|---:|---|
| Systems and Server Bring-Up | 31% | Deployment sequence, AI-factory topologies, BMC/OOB/TPM, firmware, power/cooling, GPU servers, cabling, transceivers, physical GPUs, storage |
| Physical Layer Management | 5% | BlueField network platform and MIG for AI/HPC |
| Control Plane Installation and Configuration | 19% | Base Command Manager and HA, OS, Slurm, Enroot, Pyxis, GPU/DOCA drivers, NVIDIA Container Toolkit, Docker, NGC CLI |
| Cluster Test and Verification | 33% | Stress tests, HPL, NCCL, NVLink Switch, cable/signal validation, firmware checks, ClusterKit, burn-in, NeMo, storage tests |
| Troubleshooting and Optimization | 12% | GPU/fan/NIC/power faults, component replacement, AMD/Intel server optimization, storage optimization |

The highest-value preparation is real server bring-up and cluster validation: 64% of the exam is Systems and Server Bring-Up plus Cluster Test and Verification.

## Official preparation resources

### Training

- [AI Infrastructure & Operations Fundamentals](https://www.nvidia.com/en-us/training/academy/)
- [AI Infrastructure Professional workshop](https://www.nvidia.com/en-us/training/academy/course-detail/?id=course%3A15932196)
- NVIDIA’s workshop outline covers compute platforms, storage, BlueField, AI data-center management, cluster bring-up with BCM, and hands-on practice. Delivery and pricing can vary by region and account.

### Study-guide reading list

The official study guide is the complete authoritative reading index. Its references include:

- NVIDIA System Management Interface (SMI), NVIDIA System Management (NVSM), DCGM, and NVIDIA System Management User Guide
- NVIDIA CUDA compiler driver (NVCC), CUDA, NVIDIA Container Toolkit, Docker, and NGC CLI
- NVIDIA LinkX cables and transceivers; cabling data centers; cable validation; cable-management guidelines
- DGX BasePOD Deployment Guide
- DGX H100/H200 User Guide; DGX A100 and DGX-2 service documentation
- DGX SuperPOD Deployment, Administration, Design, and Data Center Design guides
- DGXOS User Guide and DGX CentOS Install Guide
- AI Factory Whitepaper; NVIDIA Networking; InfiniBand Fabric Utilities
- BlueField Networking Platform, BlueField bring-up/firmware/management, DPU modes, `mlxconfig`, BFB from BMC, and DOCA on a DPU
- MIG User Guide and NVIDIA AI Enterprise documentation
- Base Command Manager Administrator Manual and Initial Cluster Setup for DGX SuperPOD
- NVIDIA Certified Systems Configuration Guide and virtual GPU licensing guide
- Slurm, Enroot, Pyxis, and cluster-management concepts
- NCCL documentation, `ib_write_lat`, InfiniBand port counters, UFM counters/events, and AI fabric resiliency
- HPL, NCCL, NeMo, ClusterKit, storage validation, and DGX best practices
- RAPIDS cuDF, enterprise AI storage selection, and BlueField/VAST integration material

For exact document versions, use the links in the PDF and prefer the current NVIDIA documentation version over older release-specific guides.

## Lab options

| Option | Best coverage | Important limitations |
|---|---|---|
| **NVIDIA Academy professional workshop** | Closest structured preparation: AI infrastructure, compute, networking, storage, BlueField, management, and hands-on cluster activities | Paid/seat-based; availability and lab access depend on region and enrollment |
| **Cloud GPU VM** | Linux, CUDA, SMI, DCGM, Container Toolkit, Docker, NGC CLI, NCCL on one node, MIG where supported | Usually no BMC/OOB/TPM, physical cabling, BlueField, NVLink Switch, multi-node fabric, or true power/cooling validation |
| **Local workstation/server with NVIDIA GPU** | SMI, DCGM, drivers, containers, CUDA, NCCL single-node, storage experiments, MIG on supported GPU | Hardware generation and virtualization support matter; cannot reproduce data-center bring-up or multi-node validation alone |
| **GPU passthrough VM** | OS, driver, container, NGC, and cluster software installation in a repeatable environment | BMC, firmware, cable, power, cooling, and many performance features are hidden from the guest |
| **Bare-metal multi-GPU / multi-node lab** | NCCL, HPL, burn-in, fabric bandwidth, cabling, firmware, storage, ClusterKit, and workload readiness | Expensive; requires compatible GPUs, NICs, switches, firmware, drivers, and storage |
| **DGX/HGX or BasePOD access** | Highest-fidelity server bring-up, NVLink/NVSwitch, BlueField, BMC/OOB, firmware, power/cooling, and full validation | Normally employer, partner, university, NVIDIA, or specialist-lab access; not a realistic personal purchase for most learners |
| **Virtual BCM/Slurm cluster** | Control-plane concepts, OS deployment, Slurm/Enroot/Pyxis workflows, categories/interfaces, HA concepts, Docker and NGC CLI | Does not replace real GPU, BMC, fabric, firmware, or performance testing; BCM images/licensing may be restricted |
| **Kubernetes GPU lab** | Useful adjacent infrastructure practice: GPU Operator, drivers, container runtime, GPU scheduling, DCGM and workload validation | Kubernetes is not the core NCP-AII blueprint; it does not replace BCM/Slurm or physical cluster validation |

## Suggested study/lab progression

1. Read the blueprint and official study guide; turn every numbered objective into a checklist.
2. Use a cloud GPU or local GPU to practice SMI, DCGM, drivers, CUDA, Container Toolkit, Docker, NGC CLI, NCCL, and storage checks.
3. Build a small virtual control-plane lab with Linux, Slurm, Enroot, Pyxis, and containerized workloads.
4. Take the NVIDIA Academy workshop if you need guided hands-on access to the NVIDIA stack.
5. Get scheduled time on DGX/HGX/BasePOD or equivalent multi-node hardware for BMC/OOB, firmware, BlueField, cabling, NVLink, NCCL, HPL, ClusterKit, burn-in, and storage validation.
6. Practice failure scenarios: bad driver/firmware, missing GPU, failed NIC, cable/transceiver issue, power-supply/fan fault, storage bottleneck, and low fabric bandwidth.
7. Avoid exam dumps. NVIDIA’s official public resources are the blueprint, study guide, documentation, training, and workshops; third-party “actual questions” files are not authoritative and may violate exam rules.

## NCP-AII versus NCP-AIN

- **NCP-AII:** servers, physical layer, control plane, cluster validation, troubleshooting, and optimization.
- **NCP-AIN:** Spectrum-X/Ethernet, InfiniBand networking, Kubernetes Network Operator, network troubleshooting, and network automation.

The two certifications overlap around AI-factory topology, BlueField, InfiniBand, NCCL, and troubleshooting, but the lab requirements are different. AIR/Cumulus VX is useful for NCP-AIN Ethernet practice; it is not a substitute for NCP-AII server bring-up or GPU-cluster validation.

## Verification notes

- NVIDIA’s page currently shows 70–75 questions even though the description says “approximately 70”; verify the booking screen before registering.
- Training availability, pricing, cloud lab access, and software licensing can change by region/account.
- The study guide references several release-specific documents. Prefer current documentation, but retain the terminology and workflows from the guide for exam preparation.

