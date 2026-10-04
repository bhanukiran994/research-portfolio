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

### Dissertation method flowcharts

These conceptual flowcharts summarize the architectures described in dissertation Chapters 3-6. They describe the dissertation methods; they do not assert that every archived implementation reproduces every component or that the systems have been independently validated.

#### HBKT with RSVM

Chapter 3 combines block-based Krawtchouk-Tchebichef features with RSVM classification.

```mermaid
flowchart TD
    H1["Face image"] --> H2["Face preprocessing"]
    H2 --> H3["Overlapping image blocks"]
    H3 --> H4["Krawtchouk-Tchebichef feature extraction"]
    H4 --> H5["Feature vector normalization"]
    H5 --> H6["RSVM classification"]
    H6 --> H7["Individual authentication decision"]
```

#### GSSGAN

Chapter 4 describes complementary facial features followed by the MAF-SfNet recognition architecture, CCF-GOA hyperparameter tuning and a GAN stage. The tuning connection represents model development rather than a required operation on every captured frame.

```mermaid
flowchart TD
    G1["Face image"] --> G2["MTCNN face detection and alignment"]
    G2 --> G3["ResNet deep features"]
    G2 --> G4["ENPT-LGIP features"]
    G2 --> G5["LGTP features"]
    G3 --> G6["Combined feature representation"]
    G4 --> G6
    G5 --> G6
    G6 --> G7["Siamese MAF-SfNet recognition"]
    G8["CCF-GOA hyperparameter tuning"] -.-> G7
    G7 --> G9["GAN stage"]
    G9 --> G10["Individual authentication decision"]
```

#### HT-HG with HS-SVM

Chapter 5 combines the HT-HG descriptor with ResNet features before HS-SVM classification.

```mermaid
flowchart TD
    T1["Face image"] --> T2["MTCNN detection, alignment and normalization"]
    T2 --> T3["Hyper Transformation"]
    T3 --> T4["Gradient magnitude and orientation"]
    T4 --> T5["Local orientation histograms and block normalization"]
    T5 --> T6["HT-HG descriptor"]
    T2 --> T7["ResNet residual features"]
    T6 --> T8["Handcrafted and deep feature fusion"]
    T7 --> T8
    T8 --> T9["HS-SVM classification"]
    T9 --> T10["Individual authentication decision"]
```

#### Combined dissertation ensemble

Chapter 6 sends the same preprocessed face to three independent recognition modules. Each produces a binary decision. The final decision accepts the enrolled identity when at least two of the three modules vote to accept; otherwise it rejects. Repeated decisions feed continuous authentication management.

```mermaid
flowchart TD
    E1["Repeated webcam image capture"] --> E2["Face detection, alignment and preprocessing"]
    E2 --> E3["HBKT and RSVM"]
    E2 --> E4["GSSGAN"]
    E2 --> E5["HT-HG and HS-SVM"]
    E3 --> E6["HBKT binary decision"]
    E4 --> E7["GSSGAN binary decision"]
    E5 --> E8["HT-HG binary decision"]
    E6 --> E9["Majority voting across three decisions"]
    E7 --> E9
    E8 --> E9
    E9 --> E10["Accept with at least two positive votes; otherwise reject"]
    E10 --> E11["Continuous authentication management"]
    E11 --> E1
```

The separate journal verification study evaluates score-fusion alternatives, including mean-score fusion. That is a different protocol from the dissertation's final majority-vote ensemble shown here.


### Engineering focus

- Modular Python applications and graphical interfaces
- Feature extraction, classification and model evaluation
- Experimental configuration, result tracking and technical documentation

These diagrams summarize software workflows and contain no implementation details or biometric data. Research prototypes are not presented as independently validated production authentication systems. No performance or security guarantee is asserted here.
