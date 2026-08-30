# Self-Supervised Memory-Augmented Anomaly Detection for Early Stuck-Pipe Warning

This repository provides the data organization, experimental protocol,
configuration information, and reproducibility materials associated with the
manuscript:

**“Self-Supervised Memory-Augmented Anomaly Detection for Early Stuck-Pipe Warning under Label Scarcity”**

The proposed framework, termed **Enhanced Adaptive Memory-Augmented
Self-Supervised Learning (E-AMSL)**, is designed for early stuck-pipe warning
under limited anomaly annotations. The method learns normal drilling behavior
from unlabeled operational data and combines causality-preserving multi-view
representation learning, prototype-constrained reconstruction, and a causal
operational-disambiguation mechanism.

---

## Repository Scope

This repository is intended to document the experimental protocol and provide
materials required to reproduce the data organization and reported evaluation
procedure.

The current release includes or will include:

- dataset and sequence descriptions;
- development, validation, calibration, and independent-test split definitions;
- model and baseline configurations;
- predefined random seeds;
- threshold-calibration settings;
- window-level and event-level evaluation results;
- domain-shift and sensitivity-analysis results;
- preprocessing and reproducibility documentation.

The complete research source code is not included in the current public release.
It is temporarily withheld because parts of the implementation are being used
in ongoing follow-up research within the research group. The source code is
planned for public release after completion of the related follow-up work,
subject to institutional and intellectual-property requirements.

---

## Dataset

The experiments are based on the publicly available **Volve field dataset**
released by Equinor.

The original drilling data contain ten recorded variables:

1. Hole Depth (MD)
2. Bit Depth (MD)
3. Block Position
4. Average Surface Torque
5. Average Hookload
6. Average Rotary Speed
7. Weight on Bit (WOB)
8. Rate of Penetration (ROP)
9. Average Standpipe Pressure (SPP)
10. Mud Flow In

Hole Depth (MD) is excluded from the final E-AMSL input because of its
cumulative nature and strong redundancy with Bit Depth. Therefore, the final
model uses **nine input variables**.

The data are sampled at **4 s intervals**.

Each E-AMSL input sample is a strictly causal window containing

```text
125 time steps × 9 variables
