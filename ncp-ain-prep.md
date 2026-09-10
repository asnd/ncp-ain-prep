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

The last four are named in the study guide as recommended optional training or supporting preparation; availability, price, and enrollment may depend on account and region.

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

- [Cumulus Linux in a virtual environment](https://docs.nvidia.com/networking-ethernet-software/cumulus-linux-52/Cumulus-Linux-in-a-Virtual-Environment/)
- [NVIDIA Air custom topology guide](https://docs.nvidia.com/networking-ethernet-software/nvidia-air/Custom-Topology/)
- [Cumulus Linux pre-built Air demos](https://docs.nvidia.com/networking-ethernet-software/cumulus-linux-55/Try-It-Pre-built-Demos/)
- Cumulus basic configuration, NVUE 5.x interface/command reference, QoS, VRF, EVPN multihoming, VXLAN/EVPN, BGP weighted ECMP, adaptive routing, flow analysis, threshold-crossing events
- NetQ administration and network operations
- WJH (What Just Happened), resource diagnostics with `cl-resource-query`, and NetQ latency/congestion monitoring
- [DOCA installation guide and profiles](https://docs.nvidia.com/doca/)
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

- [NVIDIA Network Operator documentation](https://docs.nvidia.com/network-operator/)
- [NVIDIA Network Operator GitHub repository](https://github.com/Mellanox/network-operator)
- Network Operator deployment guide, DGX BasePOD on RHEL guide, and NVIDIA “Getting Started with Kubernetes”
- Getting Started with Red Hat OpenShift and the GPUDirect RDMA/OpenShift chapter
- NVUE templates and command reference
- Cumulus automation with Ansible; NVUE automation with Ansible; ONIE command-line reference

## Lab options

| Option | What it is good for | What it cannot faithfully reproduce | Cost/access notes |
|---|---|---|---|
| **NVIDIA Air / DSX Air** | Free personal cloud simulation; Cumulus VX CLI, leaf-spine topologies, BGP/OSPF, EVPN/VXLAN, VRR/MLAG, ZTP, topology experiments, basic automation | Real Spectrum ASIC behavior, physical RoCE/PFC/ECN performance, real GPUs, InfiniBand fabric, UFM, and end-to-end NCCL/RDMA performance | Best first lab. NVIDIA documents it as a free virtual data-center network. Requires an NVIDIA account/browser. |
| **Cumulus VX on local KVM/QEMU** | Repeatable virtual switches, Cumulus Linux/NVUE, BGP/EVPN/VXLAN, Ansible, CI and topology automation | ASIC pipelines, hardware telemetry, true PFC/ECN behavior, Spectrum-X, InfiniBand/UFM | Free virtual appliance; local CPU/RAM/storage required. |
| **Cumulus VX with VirtualBox/GNS3** | Small three-node leaf/spine practice and packet-path visualization | Same hardware and InfiniBand limitations as VX; older guides/images may need version adjustment | NVIDIA documents a two-leaf/one-spine setup; use current image/version where possible. |
| **Production Ready Automation / libvirt simulation** | Larger Cumulus reference topology, golden EVPN-VXLAN configurations, Ansible/IaC and NetQ Cloud CI examples | Spectrum ASIC, physical RoCE, InfiniBand, UFM | Strong virtual option for automation and operations practice. |
| **NetQ KVM appliance on-prem** | NetQ UI/CLI, telemetry and operations workflows | Requires licensed NetQ image; still does not emulate switch ASICs or InfiniBand | NVIDIA’s current single-server example lists 16 vCPU, 64 GB RAM, 500 GB SSD, 1 Gb NIC, KVM/QCOW. Download is through NVIDIA Application Hub/licensing. |
| **Physical Ethernet AI lab** | Highest-fidelity Spectrum/ConnectX/SuperNIC, RoCE, QoS, PFC, ECN, telemetry, WJH, NetQ and GPU-network validation | Expensive and hardware/software release dependent | Typically requires access through an employer, NVIDIA partner, university, or rented specialist lab. |
| **Physical InfiniBand lab** | Switch provisioning, subnet manager, PKeys, QoS/adaptive routing, UFM, `ib*` diagnostics, GPUDirect RDMA and NCCL | Little can replace this for the IB 30% + troubleshooting domains | Requires ConnectX adapters, IB switch(es), hosts, cables, firmware/drivers, and usually UFM licensing/support. |
| **Kubernetes lab on VMs or bare metal** | Network Operator manifests, RDMA resources, device plugins, validation and troubleshooting concepts | VM networking generally cannot reproduce real RDMA/IB performance; GPU integration may be absent | Use a small local Kubernetes cluster for control-plane practice, then validate RDMA on physical NICs if possible. |

## Recommended progression

1. Read the blueprint and study guide; create a checklist from each numbered objective.
2. Complete InfiniBand Essentials, InfiniBand Network Administration, and Cumulus Linux Essentials.
3. Build a 2-leaf/1-spine topology in Air. Practice NVUE, BGP/EVPN, VLAN/VRF, VXLAN, QoS concepts, ZTP, and Ansible.
4. Rebuild the topology locally with Cumulus VX/libvirt if repeatability or automation testing matters.
5. Use a licensed NetQ environment for NetQ workflows where available.
6. Obtain time on real NVIDIA Ethernet and InfiniBand hardware—especially for PFC/ECN/RoCE, UFM, PKeys, `ibdiagnet`, and bandwidth/latency diagnostics.
7. Add a Kubernetes cluster and deploy/verify Network Operator.
8. Do not rely on “exam dumps.” NVIDIA’s public material found here provides the blueprint and study guide, but no official public practice-question bank was identified. Use objective-based self-tests and vendor documentation instead.

## Important uncertainty / items to verify before spending money

- The NVIDIA page publishes the three core courses directly, but course enrollment, paid/ free status, and the availability of Spectrum-X, debugging-tools, and Ansible courses can vary by account/region.
- Air’s exact image catalog, simulation quotas, and supported feature set can change; verify in the current Air UI.
- The current public study guide is versioned May 2026 in its PDF metadata, while some linked documentation is for older Cumulus/NetQ releases. Learn the concepts and command families, then prefer the current documentation version for implementation.
- NVIDIA’s exam page says English for the US listing; regional pages may offer different languages/pricing.

## Primary sources

- [NVIDIA NCP-AIN certification page](https://www.nvidia.com/en-us/learn/certification/ai-networking-professional/)
- [NVIDIA NCP-AIN Exam Study Guide](https://dam-cdn.nvd.orangelogic.com/AssetLink/32ljugfxg1hs1sd42371npw1xmcuo1yo.pdf)
- [NVIDIA Cumulus Linux virtual environments](https://docs.nvidia.com/networking-ethernet-software/cumulus-linux-52/Cumulus-Linux-in-a-Virtual-Environment/)
- [NVIDIA Air custom topology](https://docs.nvidia.com/networking-ethernet-software/nvidia-air/Custom-Topology/)
- [NVIDIA Air pre-built demos](https://docs.nvidia.com/networking-ethernet-software/cumulus-linux-55/Try-It-Pre-built-Demos/)
- [NetQ KVM requirements](https://docs.nvidia.com/networking-ethernet-software/cumulus-netq-49/Installation-Management/Install-NetQ/KVM-Setup-sngl-op/)
- [NVIDIA Production Ready Automation Guide](https://docs.nvidia.com/networking-ethernet-software/guides/production-ready-automation/)
- [NVIDIA Network Operator](https://docs.nvidia.com/network-operator/)
