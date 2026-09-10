# NCP-AIN preparation and lab options

Research date: 2026-09-10

## Scope clarification

NCP-AIN means **NVIDIA-Certified Professional: AI Networking**. It is not the similarly named NCP-AII (AI Infrastructure) exam. NVIDIA describes NCP-AIN as an intermediate professional certification for deploying and configuring NVIDIA AI networking environments.

Exam facts currently published by NVIDIA:

- 70–75 questions, 120 minutes, English, remotely proctored
- US price shown as $400; verify regional pricing before booking
- NVIDIA recommends two to three years of operational data-center experience with NVIDIA hardware solutions
- Certification validity: two years
- Exam registration: [NVIDIA certification page](https://www.nvidia.com/en-us/learn/certification/ai-networking-professional/)

## Exam blueprint

| Domain | Weight | Main skills |
|---|---:|---|
| AI data-center design and optimization | 5% | AI factory components, rail-optimized topology, GPU-to-GPU communication |
| NVIDIA Spectrum networking | 30% | RoCE, QoS, ECN, PFC, adaptive routing, telemetry, BGP-EVPN, NetQ, WJH, DOCA, SuperNIC, NVIDIA Air |
| NVIDIA InfiniBand networking | 30% | Provisioning/HA, PKeys, QoS, adaptive routing, UFM |
| Kubernetes integration | 5% | NVIDIA Network Operator, RDMA and InfiniBand integration |
| Troubleshooting tools | 20% | `cl-resource-query`, WJH, UFM, `ib_write_lat`, `ib_write_bw`, `ibping`, `ibstat`, `ibdiagnet`, `ibnodes`, `iblinkinfo` |
| Automation and configuration | 10% | NVUE templates and Ansible for VLAN/RoCE/network setup |

The highest-return study order is Spectrum + InfiniBand (60%), troubleshooting (20%), automation (10%), then design and Kubernetes.

## Official preparation resources

### Start here

1. [NCP-AIN certification page and blueprint](https://www.nvidia.com/en-us/learn/certification/ai-networking-professional/)
2. [Official NCP-AIN Exam Study Guide (PDF)](https://dam-cdn.nvd.orangelogic.com/AssetLink/32ljugfxg1hs1sd42371npw1xmcuo1yo.pdf)
3. [NVIDIA Academy course catalogue](https://academy.nvidia.com/en/wp-content/uploads/2026/02/NVIDIA_Academy_Courses_Catalog.pdf)

The study guide is the authoritative preparation index. It contains the complete recommended reading list, organized by every exam domain. The resources below reproduce its training recommendations and consolidate the reading list into study bundles.

### NVIDIA Academy courses

- [InfiniBand Essentials](https://www.nvidia.com/en-us/training/academy/course-detail/?id=course%3A15139827)
- [InfiniBand Network Administration](https://www.nvidia.com/en-us/training/academy/course-detail/?id=course%3A15139854)
- [Cumulus Linux Essentials](https://www.nvidia.com/en-us/training/academy/course-detail/?id=course%3A15139853)
- Cumulus Linux Administration
- Spectrum-X Network Platform Administration
- MLXlink and MLXcables Debugging Tools
- Ansible Essentials for Network Engineers

The last four are named in the study guide as recommended optional training or supporting preparation. The [2026 Academy catalogue](https://academy.nvidia.com/en/wp-content/uploads/2026/02/NVIDIA_Academy_Courses_Catalog.pdf) describes Spectrum-X Networking Platform Administration as private remote/on-site training (three four-hour sessions) with hands-on DSX Air, Cumulus Linux, and NetQ labs. InfiniBand Network Administration is private remote/on-site training with hands-on UFM and SHARP labs. Availability and pricing depend on region and organization.

### Resource assessment

- **Mandatory:** blueprint plus official study guide. They define the testable objectives and weighting.
- **Best structured preparation:** Cumulus Linux Essentials, InfiniBand Essentials, InfiniBand Network Administration, and Spectrum-X Networking Platform Administration.
- **Use selectively:** the PDF's long reading list. Several links target old Cumulus, MLNX-OS, NetQ, or Network Operator releases. Study the named concept, but use current product documentation for commands.
- **Practice questions:** the two NVIDIA certification webinars linked in [the discount tracker](DISCOUNTS.md) show sample questions. No official public NCP-AIN practice exam was found.
- **Udemy:** see the [verified Udemy inventory](UDEMY.md) for one taught course and nine practice-test listings. They are third-party supplements, not official NVIDIA preparation or substitutes for labs.

### Design and AI-fabric reading

- BlueField-3 Administrator Quick-Start Guide; NVIDIA BlueField Networking Platform; BlueField reset/reboot procedure
- DGX SuperPOD: key components; enterprise deployment; scalable infrastructure
- NVIDIA Spectrum-X Whitepaper and Spectrum-X Network Platform Architecture Whitepaper
- NVIDIA NVLink and NVSwitch; NCCL overview and troubleshooting
- Rail-Optimized Topology Validation
- Networking for Data Centers and the Era of AI; Turbocharging Generative AI Workloads with Spectrum-X
- NVIDIA reference architecture for AI cloud providers
- GB200 NVL72 technical overview
- SONiC Wiki
- LUG’24 AI networking presentation by Aurelien Degremont and Nathan Dauchy

### Spectrum-X, Cumulus Linux, NetQ, WJH, DOCA

- [Cumulus Linux in a virtual environment](https://docs.nvidia.com/networking-ethernet-software/cumulus-linux-53/Cumulus-Linux-in-a-Virtual-Environment/)
- [DSX Air custom topology guide](https://docs.nvidia.com/networking-ethernet-software/nvidia-air-v2/Custom-Topology/)
- [DSX Air pre-built demos](https://docs.nvidia.com/networking-ethernet-software/nvidia-air/Pre-Built-Demos/)
- Cumulus basic configuration, NVUE 5.x interface/command reference, QoS, VRF, EVPN multihoming, VXLAN/EVPN, BGP weighted ECMP, adaptive routing, flow analysis, threshold-crossing events
- NetQ administration and network operations
- WJH (What Just Happened), resource diagnostics with `cl-resource-query`, and NetQ latency/congestion monitoring
- [DOCA SDK documentation](https://docs.nvidia.com/doca/sdk/)
- ConnectX-8 SuperNIC user manual; Ethernet SuperNICs overview; Spectrum-X datasheet
- CloudAI Benchmark Framework
- NVIDIA technical blogs on NVUE + Ansible, WJH, digital twins on Air, and Spectrum-X

### InfiniBand and UFM

- [NVIDIA InfiniBand documentation](https://docs.nvidia.com/networking/)
- InfiniBand fabric managed by UFM; UFM Enterprise User Manual; UFM datasheet
- InfiniBand switching, initial configuration, installation notes, operations procedures, transport modes, telemetry, and subnet manager documentation
- InfiniBand QoS, adaptive routing/self-healing, partitioning/PKeys, HA with SSH trust
- InfiniBand fabric utilities and diagnostic utilities
- MLNX-OS User Manuals and MLNX_OFED documentation
- `ib_write_lat`, `ib_write_bw`, `ibping`, `ibstat`, `ibdiagnet`, `ibnodes`, and `iblinkinfo`
- GPUDirect RDMA bandwidth benchmarking; NCCL and SHARP documentation

### Kubernetes and automation

- [NVIDIA Network Operator documentation](https://docs.nvidia.com/networking/display/kubernetes2610/getting-started-with-kubernetes.html)
- [NVIDIA Network Operator GitHub repository](https://github.com/Mellanox/network-operator)
- Network Operator deployment guide, DGX BasePOD on RHEL guide, and NVIDIA “Getting Started with Kubernetes”
- Getting Started with Red Hat OpenShift and the GPUDirect RDMA/OpenShift chapter
- NVUE templates and command reference
- Cumulus automation with Ansible; NVUE automation with Ansible; ONIE command-line reference

## Lab options

| Option | What it is good for | What it cannot faithfully reproduce | Cost/access notes |
|---|---|---|---|
| **NVIDIA DSX Air free trial** | Best self-service option for Cumulus/NVUE, leaf-spine topology, BGP/OSPF, EVPN/VXLAN, VRR/MLAG, ZTP and Ansible | Virtual Cumulus does not support WJH, adaptive routing, QoS buffer management/monitoring or shaping; no real RoCE performance, GPU, InfiniBand, or UFM | Eligible NGC organizations receive a one-year trial with 10,000 compute hours, 60 concurrent vCPUs and 60 GiB RAM. A business email is required; personal email addresses are rejected. |
| **Spectrum-X Networking Platform Administration** | Most aligned guided Ethernet lab: Spectrum-X design/deployment, RoCE concepts, congestion control, Air, NetQ and Cumulus troubleshooting | Instructor environment details vary; it still does not give unrestricted ownership of physical production hardware | Private remote/on-site course; three sessions of four hours. The 2026 catalogue lists $1,500 per seat. Request availability from NVIDIA Academy. |
| **InfiniBand Network Administration** | Best guided IB lab: fabric management, UFM, SHARP, monitoring and troubleshooting | Temporary course environment, not a permanent personal fabric | Private remote/on-site; four sessions of about 4.5 hours with hands-on labs. Request a quote/seat. |
| **Legacy Cumulus VX image on KVM/GNS3** | Repeatable control-plane and automation practice if you already have a lawful image | Same virtual hardware gaps as Air; old images are version-skewed | NVIDIA no longer distributes Cumulus VX as a standalone image. Do not plan a new lab around downloading it. Use DSX Air instead. |
| **Production Ready Automation examples** | Reference topologies and Ansible/IaC patterns | Published examples can target end-of-life Cumulus releases and do not provide a current VX image | Useful as code/design references; adapt to current Cumulus/NVUE syntax in Air. |
| **NetQ 5.3 KVM appliance on-prem** | NetQ UI/CLI, telemetry, validation and operations workflows | Requires access to licensed images and monitored devices; does not create Spectrum or InfiniBand hardware | Current single-server minimum: 16 vCPU, 64 GB RAM, 500 GB SSD. NetQ is a per-switch subscription and downloads require NVIDIA Application Hub/licensing. |
| **Physical Ethernet AI lab** | Highest-fidelity Spectrum/ConnectX/SuperNIC, RoCE, QoS, PFC, ECN, telemetry, WJH, NetQ and GPU-network validation | Expensive and hardware/software release dependent | Typically requires access through an employer, NVIDIA partner, university, or rented specialist lab. |
| **Physical InfiniBand lab** | Switch provisioning, subnet manager, PKeys, QoS/adaptive routing, UFM, `ib*` diagnostics, GPUDirect RDMA and NCCL | Little can replace this for the IB 30% + troubleshooting domains | Requires ConnectX adapters, IB switch(es), hosts, cables, firmware/drivers, and usually UFM licensing/support. |
| **Kubernetes lab** | Helm/operator lifecycle, CRDs, manifests and troubleshooting methodology | Functional RDMA/SR-IOV/GPUDirect exercises require NVIDIA RDMA-capable NICs; a VM-only cluster covers manifests, not the data path | Network Operator's quick start requires a running cluster with NVIDIA NICs. Use VMs for control-plane study and physical NICs for validation. |

### Lab coverage assessment

| Exam area | Air only | Add guided NVIDIA courses | Add physical Spectrum + InfiniBand |
|---|---|---|---|
| Design (5%) | Medium | High | High |
| Spectrum (30%) | Medium | High | Full |
| InfiniBand (30%) | None | High with IB course | Full |
| Kubernetes (5%) | None | Low/medium | High with Kubernetes + NVIDIA NICs |
| Troubleshooting (20%) | Low/medium | High | Full |
| Automation (10%) | High | High | Full |

“Full” means the platform can expose the relevant mechanisms; it does not guarantee exam readiness. This matrix is an assessment derived from the blueprint and documented platform limitations.

## Recommended progression

1. Read the blueprint and study guide; create a checklist from each numbered objective.
2. Complete InfiniBand Essentials, InfiniBand Network Administration, and Cumulus Linux Essentials.
3. Obtain DSX Air access with an eligible business/NGC organization. Build a 2-leaf/1-spine topology and practice NVUE, BGP/EVPN, VLAN/VRF, VXLAN, ZTP, and Ansible.
4. Take or obtain lab access equivalent to Spectrum-X Administration and InfiniBand Network Administration; Air alone leaves the entire IB domain and hardware troubleshooting uncovered.
5. Use a licensed NetQ environment for NetQ workflows where available.
6. Obtain time on real NVIDIA Ethernet and InfiniBand hardware—especially for PFC/ECN/RoCE, WJH, adaptive routing, UFM, PKeys, `ibdiagnet`, and bandwidth/latency diagnostics.
7. Add a Kubernetes cluster with NVIDIA NICs and deploy/verify Network Operator.
8. Do not rely on “exam dumps.” No official public NCP-AIN practice bank was identified; use blueprint-based self-tests and NVIDIA webinar sample questions.

## Important uncertainty / items to verify before spending money

- The NVIDIA page publishes the three core courses directly, but course enrollment, paid/ free status, and the availability of Spectrum-X, debugging-tools, and Ansible courses can vary by account/region.
- DSX Air access, trial eligibility, quotas, and image catalogue can change; verify them before basing a study schedule on Air.
- The current public study guide is versioned May 2026 in its PDF metadata, while some linked documentation is for older Cumulus/NetQ releases. Learn the concepts and command families, then prefer the current documentation version for implementation.
- NVIDIA’s exam page says English for the US listing; regional pages may offer different languages/pricing.

## Primary sources

- [NVIDIA NCP-AIN certification page](https://www.nvidia.com/en-us/learn/certification/ai-networking-professional/)
- [NVIDIA NCP-AIN Exam Study Guide](https://dam-cdn.nvd.orangelogic.com/AssetLink/32ljugfxg1hs1sd42371npw1xmcuo1yo.pdf)
- [DSX Air account setup and free-trial limits](https://docs.nvidia.com/networking-ethernet-software/nvidia-air-v2/Account-Setup/)
- [DSX Air custom topology](https://docs.nvidia.com/networking-ethernet-software/nvidia-air-v2/Custom-Topology/)
- [DSX Air pre-built demos](https://docs.nvidia.com/networking-ethernet-software/nvidia-air/Pre-Built-Demos/)
- [Cumulus virtual-environment limitations](https://docs.nvidia.com/networking-ethernet-software/cumulus-linux-53/Cumulus-Linux-in-a-Virtual-Environment/)
- [Cumulus VX distribution status](https://docs.nvidia.com/networking-ethernet-software/cumulus-vx/)
- [NetQ 5.3 deployment requirements](https://docs.nvidia.com/networking-ethernet-software/cumulus-netq-53/Installation-Management/Install-NetQ/Before-You-Install/)
- [NVIDIA Production Ready Automation Guide](https://docs.nvidia.com/networking-ethernet-software/guides/production-ready-automation/)
- [NVIDIA Network Operator documentation](https://docs.nvidia.com/networking/display/kubernetes2610/getting-started-with-kubernetes.html)
- [Spectrum-X Network Platform Administration outline](https://academy.nvidia.com/en/wp-content/uploads/2025/06/Spectrum-X-Networking-Platform-Administration-2024.pdf)
- [InfiniBand Network Administration outline](https://academy.nvidia.com/en/wp-content/uploads/2026/01/InfiniBand-Network-Administration-Outline.pdf)
- [Discounts and free-exam tracker](DISCOUNTS.md)
- [Verified Udemy resources and assessment](UDEMY.md)
