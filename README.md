# Bhanukiran Devisetty

## Python and computer vision research

My work includes Python applications for face recognition and authentication, and research pipelines for evaluating face-verification models. This portfolio describes two related project areas. Implementation repositories are private.

### Continuous Face Recognition and Authentication

A research prototype combining image capture, face preprocessing, feature extraction, model decisions and a graphical interface. The work explores individual recognizers and ensemble decisions in an authentication workflow.

```mermaid
flowchart LR
    A[Image capture] --> B[Face preprocessing]
    B --> C[Feature extraction]
    C --> D[Model decisions]
    D --> E[Application interface]
```

### Leakage-Controlled Multi-Model Face Verification

A research workflow for comparing heterogeneous face representations under subject-disjoint evaluation. It includes model comparison, fusion experiments and reproducibility records, with separate training, validation and testing responsibilities.

```mermaid
flowchart LR
    A[Authorized research data] --> B[Subject-disjoint split]
    B --> C[Training]
    C --> D[Validation and calibration]
    D --> E[Held-out evaluation]
    E --> F[Comparison and reporting]
```

### Engineering focus

- Modular Python applications and graphical interfaces
- Feature extraction, classification and model evaluation
- Experimental configuration, result tracking and technical documentation

These diagrams summarize software workflows and contain no implementation details or biometric data. Research prototypes are not presented as independently validated production authentication systems. No performance or security guarantee is asserted here.
