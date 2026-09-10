# NVIDIA AI infrastructure certification study notes

Reviewed: 2026-09-10

This repository covers two different NVIDIA professional certifications:

- [NCP-AIN — AI Networking](ncp-ain-prep.md): Spectrum-X, InfiniBand, Network Operator, troubleshooting, and automation.
- [NCP-AII — AI Infrastructure](ncp-aii/README.md): server bring-up, cluster control plane, validation, burn-in, and optimization.
- [Exam discounts and free-exam opportunities](DISCOUNTS.md): dated, verified offers and availability notes.

## Lab recommendation at a glance

| Goal | Best starting point | Next step for exam fidelity |
|---|---|---|
| NCP-AIN Ethernet, NVUE, EVPN, and automation | NVIDIA DSX Air free trial, if eligible | Spectrum-X Administration instructor lab or physical Spectrum/ConnectX lab |
| NCP-AIN InfiniBand, UFM, and `ib*` troubleshooting | InfiniBand Network Administration instructor lab | Physical InfiniBand hosts and switches |
| NCP-AII control plane and provisioning | Base Command Manager free license with three local VMs | NVIDIA AI Infrastructure Professional workshop |
| NCP-AII GPU software and validation | Local or cloud multi-GPU Linux host | Bare-metal DGX/HGX/BasePOD access |
| NCP-AII physical bring-up | Study vendor service/deployment guides | Supervised physical DGX/HGX lab; this cannot be reproduced faithfully in VMs |

The official exam study guides are the source of truth. Some linked readings use old product releases, so use the exam guide for scope and current NVIDIA documentation for commands and implementation.
