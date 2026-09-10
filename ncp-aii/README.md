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

- [AI Infrastructure & Operations Fundamentals](https://www.nvidia.com/en-us/training/academy/course-detail/?id=course%3A15139841)
- [AI Infrastructure Professional workshop](https://www.nvidia.com/en-us/training/academy/course-detail/?id=course%3A15932196)
- [AI Infrastructure Professional workshop outline](https://academy.nvidia.com/en/wp-content/uploads/2026/01/AI-Infrastructure-Outline-2026.pdf)
- NVIDIA’s workshop covers compute, storage, BlueField, data-center management, cluster bring-up with BCM, and hands-on practice. The [2026 Academy catalogue](https://academy.nvidia.com/en/wp-content/uploads/2026/02/NVIDIA_Academy_Courses_Catalog.pdf) lists five five-hour remote sessions at $3,000 per seat; schedules and regional purchasing can vary.

### Resource assessment

- **Mandatory:** official blueprint and study guide.
- **Best single preparation product:** AI Infrastructure Professional, because its course sections are mapped directly to every exam domain and it includes hands-on infrastructure labs.
- **Best lower-cost foundation:** AI Infrastructure & Operations Fundamentals, followed by the free BCM lab described below. Fundamentals targets the associate-level foundation and is not sufficient by itself for NCP-AII.
- **Reading list:** authoritative for scope but broad and partially versioned. Prioritize DGX/HGX bring-up, BCM, SMI/NVSM/DCGM, BlueField/MIG, Container Toolkit, NCCL/HPL/ClusterKit, cabling, and storage in blueprint order.
- **Practice questions:** NVIDIA's infrastructure-certification webinar in [the discount tracker](../DISCOUNTS.md) includes sample questions. No official public NCP-AII practice exam was found.

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
| **NVIDIA AI Infrastructure Professional workshop** | Highest-coverage guided option: compute, networking, storage, BlueField, BCM bring-up, management and hands-on infrastructure exercises | $3,000 list price; temporary lab; actual physical component replacement may still be demonstrated rather than personally performed |
| **Three-VM BCM lab with free license** | Best low-cost control-plane lab: head-node install, software images, PXE provisioning, categories/interfaces, Slurm and node management | CPU VMs cannot provide GPU/BlueField, firmware, cable, power/cooling, NCCL/HPL fabric, or physical fault practice |
| **Cloud GPU VM** | Linux, CUDA, SMI, Container Toolkit, Docker, NGC CLI, DCGM level 1, and basic workload validation | Usually no BMC/OOB/TPM, physical cabling, BlueField, NVLink Switch, multi-node fabric, or true power/cooling validation |
| **Cloud 8-GPU node** | NCCL/HPL, NVLink visibility, DCGM and burn-in on a multi-GPU system; stronger than a one-GPU VM | Provider controls firmware/BMC/cabling and may restrict privileged diagnostics; verify SXM/NVLink topology before renting |
| **Local workstation/server with NVIDIA GPU** | SMI, DCGM, drivers, containers, CUDA, NCCL single-node, storage experiments, MIG on supported GPU | Hardware generation and virtualization support matter; cannot reproduce data-center bring-up or multi-node validation alone |
| **GPU passthrough VM** | OS, driver, container, NGC, and cluster software installation in a repeatable environment | BMC, firmware, cable, power, cooling, and many performance features are hidden from the guest |
| **Bare-metal multi-GPU / multi-node lab** | NCCL, HPL, burn-in, fabric bandwidth, cabling, firmware, storage, ClusterKit, and workload readiness | Expensive; requires compatible GPUs, NICs, switches, firmware, drivers, and storage |
| **DGX/HGX or BasePOD access** | Highest-fidelity server bring-up, NVLink/NVSwitch, BlueField, BMC/OOB, firmware, power/cooling, and full validation | Normally employer, partner, university, NVIDIA, or specialist-lab access; not a realistic personal purchase for most learners |
| **Kubernetes GPU lab** | Useful adjacent infrastructure practice: GPU Operator, drivers, container runtime, GPU scheduling, DCGM and workload validation | Kubernetes is not the core NCP-AII blueprint; it does not replace BCM/Slurm or physical cluster validation |

### Recommended self-built BCM lab

NVIDIA offers a free Base Command Manager license to organizations using it for themselves. A business email is required; personal addresses are not accepted. The free license has no node-count limit, allows up to eight accelerators per server, and excludes enterprise support.

For a study lab, build one head-node VM and two compute-node VMs on an isolated virtual network. NVIDIA's BCM 11 installation guide lists a head-node minimum of 4 GB RAM (8 GB practical for installation), 80 GB disk, and two 1 Gb NICs. This lab can cover installation, image management, network boot/provisioning, categories, interfaces, node state, users, and Slurm. Snapshot the VMs before provisioning tests.

- [BCM documentation and free-license entry point](https://docs.nvidia.com/base-command-manager/)
- [BCM free-license FAQ](https://docs.nvidia.com/pdf/base-command-manager-free-license-faq.pdf)
- [BCM 11 installation manual](https://docs.nvidia.com/base-command-manager/manuals/11/installation-manual.pdf)

### Lab coverage assessment

| Exam area | BCM VMs + one GPU | Add 8-GPU cloud node | Add Academy/physical DGX-HGX lab |
|---|---|---|---|
| Server bring-up (31%) | Low/medium | Medium | Full |
| Physical layer (5%) | Low | Medium if MIG is exposed | Full |
| Control plane (19%) | High | High | Full |
| Cluster validation (33%) | Low | Medium/high on one node | Full with multi-node fabric |
| Troubleshooting (12%) | Medium for software | Medium/high for GPU software | Full |

“Full” means the environment exposes the relevant mechanism, not that merely accessing it guarantees readiness. DCGM supports basic level-1 checks on non-data-center GPUs; deeper PCIe/NVLink, stress, power and NCCL diagnostics depend on supported data-center hardware and privileges.

## Suggested study/lab progression

1. Read the blueprint and official study guide; turn every numbered objective into a checklist.
2. Request the BCM free license and build the three-VM control-plane lab. Practice OS images, provisioning, categories/interfaces, Slurm, Enroot/Pyxis concepts, and failure recovery.
3. Use a cloud GPU or local GPU to practice SMI, DCGM, drivers, CUDA, Container Toolkit, Docker, NGC CLI, NCCL, and storage checks.
4. Rent an 8-GPU node briefly—or use employer hardware—for NCCL/HPL, topology, DCGM and burn-in. Verify the instance exposes NVLink before purchase.
5. Take the NVIDIA Academy workshop if you need guided access to BlueField, BCM and broader infrastructure exercises.
6. Get scheduled time on DGX/HGX/BasePOD or equivalent multi-node hardware for BMC/OOB, firmware, BlueField, cabling, NVLink, NCCL, HPL, ClusterKit, burn-in, and storage validation.
7. Practice failure scenarios: bad driver/firmware, missing GPU, failed NIC, cable/transceiver issue, power-supply/fan fault, storage bottleneck, and low fabric bandwidth.
8. Avoid exam dumps. NVIDIA’s official public resources are the blueprint, study guide, documentation, training, and workshops; third-party “actual questions” files are not authoritative and may violate exam rules.

## NCP-AII versus NCP-AIN

- **NCP-AII:** servers, physical layer, control plane, cluster validation, troubleshooting, and optimization.
- **NCP-AIN:** Spectrum-X/Ethernet, InfiniBand networking, Kubernetes Network Operator, network troubleshooting, and network automation.

The two certifications overlap around AI-factory topology, BlueField, InfiniBand, NCCL, and troubleshooting, but the lab requirements are different. DSX Air is useful for NCP-AIN Ethernet practice; it is not a substitute for NCP-AII server bring-up or GPU-cluster validation.

See [discounts and free-exam opportunities](../DISCOUNTS.md) before purchasing an exam or workshop.

## Verification notes

- NVIDIA’s page currently shows 70–75 questions even though the description says “approximately 70”; verify the booking screen before registering.
- Training availability, pricing, cloud lab access, and software licensing can change by region/account.
- The study guide references several release-specific documents. Prefer current documentation, but retain the terminology and workflows from the guide for exam preparation.
