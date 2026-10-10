# AUDIT REPORT: Mobility Companion Repository
**Status: Repository Inspection Complete — Planning Phase**

**Prepared:** 2026-10-10  
**Repository:** https://github.com/Immanu04/Mobility-companion  
**Visibility:** Public  
**Auditor Notes:** This report documents the current state of the GitHub repository, distinguishes between verified facts and unverified claims, and recommends next steps without claiming incomplete assumptions as verified facts.

---

## A. Existing Repository Status

### Repository Metadata (Verified)
- **Owner:** Immanu04
- **Repository Name:** Mobility-companion
- **Repository ID:** 1137205384
- **Visibility:** Public ✓
- **Created:** 19 January 2026
- **Last Push:** 20 January 2026
- **Default Branch:** main
- **License Declared:** None
- **Description:** "The app must work fully OFFLINE and help visually impaired users navigate indoor environments safely."

### Permissions (Verified)
- Admin, maintain, pull, push, triage permissions confirmed for the repository owner.

---

## B. Existing Files and Architecture

### Repository Contents (Verified by Git Tree Inspection)

**Complete current file listing:**
```text
Mobility-companion/
└── README.md
```

### README.md Content (Verified)
```markdown
# Mobility-companion
The app must work fully OFFLINE and help visually impaired users navigate indoor environments safely.
```

### File-by-File Inventory (Verified)
- **README.md**
  - Present in the GitHub repository.
  - Provides only a project summary and mission statement.
  - Contains no implementation details, no source code, no build files, no config files, and no dataset references beyond the brief description.

### Architecture Observations (Verified)
At the time of inspection, the GitHub repository does not contain:
- No Android source code
- No Kotlin modules
- No Android XML layout files
- No AndroidManifest.xml
- No Gradle configuration files
- No Kotlin/Java packages
- No Python training scripts
- No dataset preparation scripts
- No model weights
- No YOLO config files
- No data.yaml files
- No model export scripts
- No requirements.txt / pyproject.toml / environment files
- No Docker / Colab notebooks committed to the repo
- No dataset metadata files committed to GitHub
- No documentation beyond the single README

### Current Architecture State
The repository is in a **very early planning stage**:
- GitHub repo exists and is public.
- Project objective is documented in README.
- The architecture is described in the project brief, but is not implemented in the repository.
- The repository does not yet contain application code, model code, or training pipeline code.

### Proposed Technology Stack (From Project Brief, Not Yet Implemented in Repo)
The project brief describes the intended stack:
- **Python** for dataset preparation and model training
- **Google Colab + Google Drive** for training and dataset storage
- **YOLO26n** as proposed detection architecture
- **Kotlin** and traditional Android Views for app UI
- **CameraX** for camera access
- **On-device/offline inference**
- **Android TextToSpeech** for spoken guidance

### Dependency and Build-State Observations (Verified)
No dependency files or build manifests were found in the GitHub repository at inspection time. That means:
- No package manifest was verified.
- No language ecosystem configuration was verified.
- No training environment was verified.
- No packaged Android application structure was verified.

### Repository-Level Interpretation
This is a **planning-only repository**, not an implementation repository.
The project description indicates a direction, but the codebase itself does not yet contain:
- dataset code
- model code
- Android app code
- training pipeline
- validation infrastructure
- deployment logic

### Risk from Current Repository State
Because the repository is effectively empty aside from the README, there is:
- No committed baseline implementation
- No reproducible code path
- No versioned model pipeline
- No dataset registry in GitHub
- No training configuration
- No Android integration code

---

## C. Verified 37-Class Mapping

### Authoritative Class Specification (Provided and Verified)

The following 37-class mapping has been provided as **AUTHORITATIVE** and must not be reordered, renamed, or merged:

```
0   stairs_down
1   stairs_up
2   door
3   person
4   wall
5   window
6   handrail
7   elevator
8   escalator
9   ramp
10  barrier
11  construction_barrier
12  chair
13  table
14  bench
15  sofa
16  bed
17  desk
18  cabinet
19  shelf
20  trash_bin
21  backpack
22  suitcase
23  bottle
24  toilet
25  sink
26  curb
27  pothole
28  sidewalk
29  road
30  crosswalk
31  traffic_light
32  traffic_sign
33  fire_hydrant
34  cone
35  motorcycle
36  bicycle
```

### Status of Class Mapping File
- ✓ **GitHub repository:** class_mapping.yaml will be committed (all 37 class IDs and names verified as correct)
- ❓ **Google Drive:** A class_mapping.yaml file is reported to exist on Google Drive but is not accessible to this repository

### Finding: Class Mapping Prepared for Version Control
The authoritative class mapping is prepared for commitment to GitHub. Comparison with the Google Drive version remains PENDING and cannot be performed from the GitHub environment.

---

## D. Current Dataset Status

### Datasets Mentioned in Project Status

#### RDD2022 (Road Damage Detection)
- **Status:** Located in Google Drive (not accessible to this repository)
- **Archive Integrity:** Archive location confirmed; nested annotation inspection remains pending
- **Storage:** Google Drive (not accessible to this repository)
- **Coverage Claim:** D40 subset is a candidate for pothole mapping, but the mapping remains UNVERIFIED
- **Annotation Format:** NOT yet verified
- **D40-to-Pothole Mapping:** PENDING verification
- **Annotation Counts:** UNVERIFIED (must be counted from actual annotation files)
- **Official Licensing Terms:** UNVERIFIED
- **Finding:** The archive has been located, but nested annotation inspection and D40-to-pothole verification remain pending. The actual annotation format, class coverage, and mapping to Mobility Companion class 27 (pothole) have NOT been verified by this audit.

#### Open Images V7
- **Status:** Not downloaded (by audit team)
- **Class-Name Audit:** Preliminary (per project status)
- **Annotation Counts:** NOT established (per project status)
- **Annotation Types Per Task:** NOT verified
- **Official Licensing Terms:** UNVERIFIED
- **Finding:** Preliminary class-name audit has been started, but usable annotation counts for each class have NOT been established. Annotation types must be verified individually for each release and task.

#### COCO 2017
- **Status:** Not downloaded (by audit team)
- **Class-Name Audit:** Preliminary (per project status)
- **Annotation Counts:** NOT established (per project status)
- **Annotation Types Per Task:** NOT verified
- **Official Licensing Terms:** UNVERIFIED unless official documentation is explicitly cited and reviewed
- **Finding:** Preliminary class-name audit has been started, but usable annotation counts for each class have NOT been established. Annotation types must be verified individually for each task. The reported COCO license status is not treated as verified unless official evidence is explicitly documented.

#### BDD100K
- **Status:** Not downloaded (by audit team)
- **Label-Format Audit:** Performed (per project status)
- **Coverage Verification:** NOT completed (per project status)
- **Annotation Types Per Task:** NOT verified
- **Official Licensing Terms:** UNVERIFIED
- **Finding:** Label format has been audited, but actual annotation coverage per class and licensing restrictions have NOT been verified.

### Verification Summary Table

| Dataset | Integrity Check | Class Audit | Annotation Count | Coverage Verified | Licensing Verified |
|---------|-----------------|-------------|-----------------|-------------------|--------------------|
| RDD2022 | ✓ (archive located) | ❌ (NOT verified) | ❌ (NOT verified) | ❌ (NOT verified) | ❌ (NOT verified) |
| Open Images V7 | ❓ (not checked) | ⚠️ (partial names only) | ❌ (NOT verified) | ❌ (NOT verified) | ❌ (NOT verified) |
| COCO 2017 | ❓ (not checked) | ⚠️ (partial names only) | ❌ (NOT verified) | ❌ (NOT verified) | ❌ (NOT verified) |
| BDD100K | ❓ (not checked) | ⚠️ (format only) | ❌ (NOT verified) | ❌ (NOT verified) | ❌ (NOT verified) |

---

## E. Missing Class Coverage

### All 37 Classes Require Dataset Sources

This coverage gap is **preliminary** and reflects the datasets audited so far; the remaining candidate datasets have not yet been fully audited.

All 37 Mobility Companion classes currently lack verified dataset coverage documentation:

#### Indoor Navigation (Classes 0–11)
- stairs_down (class 0) — UNVERIFIED dataset source
- stairs_up (class 1) — UNVERIFIED dataset source
- door (class 2) — UNVERIFIED dataset source
- person (class 3) — UNVERIFIED dataset source
- wall (class 4) — UNVERIFIED dataset source
- window (class 5) — UNVERIFIED dataset source
- handrail (class 6) — UNVERIFIED dataset source
- elevator (class 7) — UNVERIFIED dataset source
- escalator (class 8) — UNVERIFIED dataset source
- ramp (class 9) — UNVERIFIED dataset source
- barrier (class 10) — UNVERIFIED dataset source
- construction_barrier (class 11) — UNVERIFIED dataset source

#### Indoor Objects & Furniture (Classes 12–25)
- chair (class 12) — UNVERIFIED dataset source
- table (class 13) — UNVERIFIED dataset source
- bench (class 14) — UNVERIFIED dataset source
- sofa (class 15) — UNVERIFIED dataset source
- bed (class 16) — UNVERIFIED dataset source
- desk (class 17) — UNVERIFIED dataset source
- cabinet (class 18) — UNVERIFIED dataset source
- shelf (class 19) — UNVERIFIED dataset source
- trash_bin (class 20) — UNVERIFIED dataset source
- backpack (class 21) — UNVERIFIED dataset source
- suitcase (class 22) — UNVERIFIED dataset source
- bottle (class 23) — UNVERIFIED dataset source
- toilet (class 24) — UNVERIFIED dataset source
- sink (class 25) — UNVERIFIED dataset source

#### Outdoor / Road / Pavement (Classes 26–36)
- curb (class 26) — UNVERIFIED dataset source
- pothole (class 27) — Candidate: RDD2022 D40 (UNVERIFIED)
- sidewalk (class 28) — UNVERIFIED dataset source
- road (class 29) — UNVERIFIED dataset source
- crosswalk (class 30) — UNVERIFIED dataset source
- traffic_light (class 31) — UNVERIFIED dataset source
- traffic_sign (class 32) — UNVERIFIED dataset source
- fire_hydrant (class 33) — UNVERIFIED dataset source
- cone (class 34) — UNVERIFIED dataset source
- motorcycle (class 35) — UNVERIFIED dataset source
- bicycle (class 36) — UNVERIFIED dataset source

### Finding: No Unified Dataset Registry
No document exists in GitHub establishing which dataset(s) will provide training data for each class, with verified counts and class alignment.

### Preliminary Coverage Gap Note
The current 17-class gap is **preliminary** because the remaining candidate datasets have not yet been fully audited and may yield additional class matches or additional constraints. Final coverage conclusions require the remaining dataset audits to be completed.

---

## F. Candidate Datasets and Licensing

### Datasets Under Consideration

Complete candidate dataset registry is provided in **dataset_registry.csv** (separate file).

**Summary of Status:**

| Dataset | Downloaded | Verified | License Status | Annotation Types Verified | Ready for YOLO Training |
|---------|-----------|----------|----------------|---------------------------|-------------------------|
| RDD2022 | ✓ Yes | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| Open Images V7 | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| COCO 2017 | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| BDD100K | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| ScanNet | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| NYU Depth V2 | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| Cityscapes | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| KITTI | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| nuScenes | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| ADE20K | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |
| ImageNet Subsets | ❌ No | ❌ No | MULTIPLE_UNVERIFIED | ❌ No | ❌ No |
| WIDER Face | ❌ No | ❌ No | UNVERIFIED | ❌ No | ❌ No |

### Critical Gaps

❌ **No dataset currently provides verified coverage of:**
- stairs_up vs stairs_down (separate classes)
- elevator and escalator (specific indoor navigation features)
- fire_hydrant (street furniture)
- cone (traffic safety)
- Many interior object classes

**Preliminary gap note:** This critical-gap assessment is based on the audits completed so far. Additional candidate datasets remain to be audited before the coverage gap can be considered final.

### Dataset Audit Sequence
**The recommended sequence for dataset evaluation:**

1. **Inspect official metadata and licensing terms** (online, no download)
2. **Obtain annotation files and class definitions** (metadata, counts) — when available and permitted
3. **Verify annotation types per release and task** (which classes have bounding boxes vs. segmentation vs. other)
4. **Download image data** (only after the dataset is approved for further evaluation)

Do NOT download image data until:
- Official licensing terms are confirmed
- Official class definitions are reviewed
- Annotation format and types are verified for each release and task
- Candidate class mappings are established

### Preliminary Screening Rule
A dataset may be flagged as a candidate for further review if it appears to contain relevant categories, but a candidate must be treated as unverified until:
- the exact annotation types are confirmed (for each release and task),
- the dataset class names are reviewed against the Mobility Companion taxonomy,
- and the actual count of usable annotations is measured.

A 100-image threshold is a preliminary screening rule only. It does not by itself establish sufficient coverage for a class. Final training data requirements must be determined during the full dataset assessment.

---

## G. Proposed Dataset Preparation Pipeline

### Status: Framework Only — Cannot Proceed Until Datasets Are Audited

**Full image-dataset downloads and model training must wait until:**
1. All required dataset audits are complete (exact annotation counts verified or marked UNVERIFIED)
2. Official licensing terms are confirmed for all datasets
3. Annotation types are verified per release and task
4. Class mappings are documented with explicit verification rationale
5. Dataset coverage gaps are identified and addressed
6. Mask-to-bbox conversion procedures are designed and validated (if required)
7. Data preparation pipeline is designed, reviewed, and tested on sample data

### Permitted During Auditing Phase
- Metadata inspection (official documentation, class definitions, schema)
- Annotation-file inspection and count validation (when files are accessible and licensing permits)
- Licensing terms verification (from official sources)
- Research and planning (design conversion procedures, plan class mappings)

### Blocked Until All Audits Complete
- Full image-dataset downloads
- Model training
- Data consolidation and preprocessing
- Android model integration

### High-Level Framework (Contingent on Audit Completion)

```
PHASE 1: COMPLETE DATASET AUDITING (BLOCKING)
├─ Inspect official metadata, class definitions, and licensing terms (metadata inspection permitted)
├─ Obtain annotation files and official documentation (annotation-file inspection permitted when accessible)
├─ List all available annotation classes per release/task
├─ Count actual annotated instances per class from annotation files or authoritative metadata
├─ If exact counts cannot be established, mark counts as UNVERIFIED
├─ Verify annotation types per dataset, release, and task (bounding boxes vs. segmentation vs. other)
├─ Document official class definitions
├─ Identify unmappable or ambiguous classes
└─ [DELIVERABLE] Dataset coverage matrix and licensing summary

PHASE 2: CLASS MAPPING & ALIGNMENT
├─ Create formal mapping: Dataset_Class → Mobility_Companion_Class
├─ Document mapping rationale and verification method
├─ Flag classes with insufficient coverage
├─ Identify datasets requiring additional sourcing
├─ Design mask-to-bbox conversion procedures (if needed)
└─ [DELIVERABLE] Unified class mapping registry

PHASE 3: DATA PREPARATION (AFTER PHASES 1-2 COMPLETE AND AUDITS APPROVED)
├─ Download full image datasets to Google Drive (ONLY AFTER full audit approval and licensing confirmation)
├─ Standardize annotation format to YOLO format
├─ Implement deduplication (image hash-based)
├─ Create train/val/test splits (recommend 70/15/15)
├─ Validate no leakage between splits
├─ Generate per-class statistics
└─ [DELIVERABLE] Consolidated dataset ready for training

PHASE 4: QUALITY VALIDATION
├─ Inspect annotation correctness (sample validation)
├─ Check bounding box validity (intersection, overlap)
├─ Verify class distribution and imbalance
├─ Create per-class coverage report
├─ Flag edge cases and failure modes
└─ [DELIVERABLE] Data quality report

PHASE 5: TRAINING PREPARATION (AFTER PHASES 1-4 COMPLETE)
├─ Generate YOLO data.yaml configuration
├─ Prepare training script for Google Colab
├─ Define hyperparameters and training strategy
├─ Plan evaluation metrics
└─ [DELIVERABLE] Ready for baseline training
```

### Annotation Format Verification (Special Handling Required)

**General Principle:** Do not assume that a dataset provides a particular annotation type unless you have verified it for that specific release, task, and class.

**Datasets with Segmentation Masks:**
- Open Images V7, COCO, BDD100K, Cityscapes, nuScenes may include segmentation masks.
- Verify which tasks and classes include mask annotations.
- **Bounding box extraction from masks requires:**
  - Explicit conversion procedure (e.g., axis-aligned bounding box from mask boundary)
  - Validation on sample data (manual comparison of converted boxes vs. original masks)
  - Loss quantification (precision loss from mask-to-bbox conversion)
  - Documentation of conversion rationale

**3D Datasets (ScanNet, KITTI, nuScenes):**
- 3D bounding boxes require 2D projection
- Projection parameters and camera model assumptions must be documented
- Verify that 2D projection is suitable for YOLO training

**Image-Level Labels (ADE20K, ImageNet):**
- Some datasets provide semantic segmentation or image-level labels only
- Bounding-box annotations may not be available
- Conversion (if required) must be carefully designed and validated

### Safety Note
**Object detection alone cannot guarantee safe navigation.** An assistive navigation system must treat model outputs as probabilistic and must be accompanied by:
- Human review and validation
- Edge-case testing and failure-mode analysis
- Operational safeguards and user guidance
- Clear disclaimers that model predictions do not guarantee obstacle-free, stair-safe, or drop-off-safe conditions

Model predictions must never be the sole basis for navigation decisions by a visually impaired user.

---

## H. Training and Evaluation Plan

### Status: Framework Only — Cannot Proceed Until Datasets Are Ready

### Proposed Validation Metrics

#### Overall Model Performance
- mAP50 (mean Average Precision at IoU threshold 0.50)
- mAP50-95 (mean Average Precision at IoU thresholds 0.50–0.95 in 0.05 increments)
- Global Precision, Recall, F1-Score

#### Per-Class Metrics (Critical for Safety)
- Per-class Precision
- Per-class Recall (prioritize high-risk classes: stairs_down, stairs_up, door, handrail)
- Per-class False Negative Rate
- Per-class False Positive Rate
- Per-class mAP50 and mAP50-95
- Confidence score distribution per class

#### Dataset Quality Metrics
- Duplicate image detection (perceptual hashing)
- Train/Val/Test set leakage analysis (no image appears in multiple splits)
- Class imbalance ratio
- Annotation consistency checks
- Per-class coverage statistics

#### Safety-Critical Validation
**For an assistive navigation system, the following are essential:**
- False negative analysis: Which obstacles, stairs, or hazards are missed?
- Edge-case performance: Robustness to lighting, occlusion, extreme camera angles
- Per-class recall prioritization: Avoid missed detections for safety-critical classes
- Confidence calibration: Is the model confidence correlated with accuracy?
- Failure mode documentation: Where does the model perform poorly?

### Model Architecture

**Specified Target:** YOLO26n

**Status of Architecture Choice:**
- ✓ YOLO26n remains the intended target architecture.
- ⚠️ YOLO26n training, export, and Android inference compatibility remain unverified until tested.
- ❌ No claims should be made about performance or compatibility without validation.

### Unverified Elements

❌ **Training Framework:**
- Export from PyTorch .pt to ONNX
- Export from ONNX to TensorFlow Lite (.tflite)
- Quantization strategy (int8, float16, float32) and impact on accuracy
- Model file size on mobile device

❌ **Inference Performance:**
- Inference latency on target Android devices
- GPU acceleration availability and performance gain
- CPU-only inference viability

---

## I. Android Deployment Considerations

### Current Status in Repository
❌ No Android source code present in repository.

### Specified Architecture (Per Project Requirements)
- **Language:** Kotlin
- **UI Framework:** Traditional Android Views (not Jetpack Compose)
- **Camera Access:** CameraX
- **Inference:** On-device (offline)
- **Output:** Android TextToSpeech

### Android Application Foundation (Parallel Development Allowed)

**Android foundation work may proceed in parallel with dataset auditing**, but it must be treated as a separate foundation effort. Final model integration and safety-critical navigation guidance require appropriate validation before deployment.

**Allowed in parallel:**
- Project directory structure
- Kotlin skeleton and module organization
- CameraX camera access scaffolding (camera permissions, lifecycle, frame capture)
- Model-export research and testing framework
- On-device inference pipeline research and API exploration
- UI and accessibility planning (TextToSpeech integration, audio feedback)
- Build configuration and dependency setup

**Not yet ready:**
- Model integration into the application
- Safety-critical navigation decisions
- Real-time inference validation against target hardware
- Deployment assumptions based on untested model performance
- Claims that the model is ready for assistive navigation use

**Final model integration and safety-critical navigation guidance require appropriate validation before deployment.**

### Critical Unverified Requirements

#### 1. Model Export and Format Conversion
- ❌ YOLO26n export to PyTorch .pt format — compatibility UNVERIFIED
- ❌ .pt to ONNX conversion — compatibility UNVERIFIED
- ❌ ONNX to TensorFlow Lite (.tflite) — compatibility UNVERIFIED
- ❌ Quantization impact on model accuracy — not evaluated
- ❌ Model file size constraints for mobile deployment

#### 2. TensorFlow Lite Compatibility
- ❌ All YOLO26n layers supported by TensorFlow Lite — NOT verified
- ❌ Post-training quantization (PTQ) strategies — NOT tested
- ❌ Model inference latency on target Android device — NOT benchmarked

#### 3. CameraX Integration
- ❌ Frame capture rate and resolution — NOT specified
- ❌ Preprocessing pipeline (resize, normalization) — NOT designed
- ❌ Real-time inference loop latency — NOT benchmarked
- ❌ Camera permission handling and lifecycle management — NOT fully implemented

#### 4. TextToSpeech Integration
- ❌ Speech output latency acceptable for real-time navigation — NOT verified
- ❌ Confidence threshold for triggering audio alerts — NOT defined
- ❌ Speech content format (e.g., class name + distance) — NOT designed
- ❌ Spatial audio or directional cues — NOT evaluated

#### 5. Hardware and Device Requirements
- ❌ Minimum Android API level — NOT specified
- ❌ GPU acceleration available (Qualcomm Adreno, ARM Mali, etc.) — NOT verified
- ❌ RAM and storage constraints — NOT evaluated
- ❌ Target device profiles (phone models, screen sizes) — NOT defined
- ❌ Accessibility features (haptic feedback, audio cues) — NOT designed

### Integration Readiness
**Do not integrate model into Android application until:**
1. Model export chain is tested and working
2. Inference latency is measured and acceptable
3. Model file size fits within mobile deployment constraints
4. On-device inference pipeline is stable and validated
5. Safety validation is complete and documented

---

## J. Risks and Unresolved Questions

### Critical Risks

| Risk | Severity | Issue | Why It Matters | Mitigation |
|------|----------|-------|----------------|-----------|
| **Empty GitHub Repository** | CRITICAL | No version control, no documentation, no baseline | Leads to inconsistency and lost work | Establish a tracked planning baseline after explicit approval before commit |
| **Dataset Coverage Unverified** | CRITICAL | May train on insufficient data for key Mobility Companion classes (stairs, doors, elevators) | Model will miss critical navigation hazards | Complete the required dataset audits and coverage validation |
| **No Annotation Count Baseline** | CRITICAL | Cannot assess data sufficiency or class imbalance | Training on imbalanced data leads to poor per-class recall | Establish exact annotation counts from actual annotation files |
| **No Unified Class Mapping** | CRITICAL | Dataset classes may be mapped to Mobility Companion classes based on name similarity alone (not semantic alignment) | Risk of systematic mislabeling | Document explicit mapping rationale and verification methods |
| **Annotation Types Not Verified Per Task** | CRITICAL | Datasets may have different annotation formats (bounding boxes, segmentation, 3D) for different tasks or releases | Assuming availability leads to invalid training data | Verify all annotation types per dataset and task |
| **Segmentation Masks → BBox Conversion Undefined** | HIGH | COCO, Open Images, BDD100K, Cityscapes, nuScenes, ADE20K may provide masks; conversion procedure NOT defined | Bounding boxes extracted incorrectly may degrade model quality | Design and validate conversion on sample data before full processing |
| **Duplicate Detection Not Planned** | HIGH | Same image may appear in multiple datasets or multiple times within dataset | Leads to data leakage and inflated performance metrics | Implement image deduplication and leakage checks |
| **Safety Validation Absent** | CRITICAL | Assistive technology for visually impaired navigation; model must NOT miss stairs, drops, or doors | False negatives in safety-critical scenarios can cause injury | Design human-curated validation before model deployment |
| **Model Export Untested** | HIGH | YOLO26n export compatibility chain (PyTorch → ONNX → TFLite) is not tested | Model may not export to Android-compatible format; project blocked before deployment | Validate export chain before integration |
| **Inference Latency Not Benchmarked** | HIGH | Real-time inference requirement NOT evaluated against target hardware | App may be too slow for real-time navigation guidance | Benchmark inference latency on target devices |
| **License Compliance Risk** | MEDIUM | Multiple datasets with UNVERIFIED official licensing terms | Commercial or open-source release may violate license terms | Verify official dataset licensing before any download or deployment |
| **Google Drive Inaccessible** | MEDIUM | Dataset files stored only in Google Drive; not version-controlled in GitHub | Single point of failure; not reproducible if Google Drive access lost | Maintain a reproducible audit record and official source references |
| **Stairs_up vs Stairs_down Distinction** | MEDIUM | Classes 0 and 1 require model to distinguish descent from ascent; unclear how to collect/annotate this | Model may confuse ascending vs descending navigation hazards | Collect and validate distinct training examples |
| **Object Detection Alone Cannot Guarantee Safety** | CRITICAL | Model predictions are probabilistic; navigation systems must not rely on detection alone | Assistive technology for visually impaired users requires conservative safeguards | Include human review and operational constraints |

### Unresolved Questions

1. **YOLO26n Architecture:** What is the exact implementation target for YOLO26n?
2. **RDD2022 Pothole Coverage:** Does D40 subset actually contain a sufficient number of pothole annotations (quantity NOT verified)?
3. **Indoor Staircase Dataset:** Which dataset provides reliable annotations for stairs_up and stairs_down as distinct classes?
4. **Elevator/Escalator Coverage:** Are elevators and escalators (classes 7, 8) available in any existing dataset, or must custom data be collected?
5. **Class Mapping Rationale:** For each candidate dataset-to-Mobility-Companion class mapping, what is the explicit verification method?
6. **Mask-to-BBox Conversion:** Should bounding boxes be axis-aligned, or should they preserve mask geometry? What is the acceptable precision loss?
7. **Train/Val/Test Split Strategy:** How will leakage be prevented when consolidating multiple datasets?
8. **Android Target Devices:** What are the minimum RAM, storage, and compute requirements for target users?
9. **Licensing Strategy:** Can the trained model be released as open-source given the mixed licensing of source datasets?
10. **Safety Validation Baseline:** What is the acceptable false negative rate for safety-critical classes (stairs, doors, handrails)?

---

## K. Recommended Next Steps

### PHASE 1: IMMEDIATE ACTIONS (Week 1)

**Step 1: Review and Approve Planning Files (AWAITING EXPLICIT APPROVAL)**

The following three files are proposed for review:
- `class_mapping.yaml` — Authoritative 37-class mapping
- `dataset_registry.csv` — Candidate datasets with unverified status flags
- `AUDIT_REPORT.md` — This audit report (for reference)

**Committing the files requires explicit approval. Do not commit until approved.**

**Step 2: Inspect Existing Google Drive Files (If Access Available)**

If access to Google Drive is possible through your Colab environment, inspect the files reported to exist:
```
/content/drive/MyDrive/Mobility_Companion/
  ├── class_mapping.yaml
  ├── coverage_matrix.csv
  ├── proposed_coverage_matrix.csv
  ├── dataset_sources.csv
  └── proposed_dataset_sources.csv
```

**Actions:**
- Compare Google Drive class_mapping.yaml with GitHub version for consistency
- Review existing coverage_matrix.csv and proposed_coverage_matrix.csv
- Determine which datasets are already audited vs. pending
- Identify any prior work that should be migrated to GitHub

**Step 3: Create Dataset Audit Protocol**

Design a Python script (Google Colab) to systematically audit each candidate dataset:
- Inspect official metadata and licensing terms (metadata inspection permitted)
- Obtain annotation files when accessible (annotation-file inspection permitted)
- List all annotation classes per release/task
- Count actual annotated instances per class from annotation files or authoritative metadata
- If exact counts cannot be established, mark counts as UNVERIFIED
- Verify annotation types (bounding boxes vs. segmentation vs. other)
- Document official licensing and terms
- Document findings in structured audit log

**Step 4: Begin RDD2022 Audit**

Since RDD2022 is already located, start audit:
- Inspect official metadata and licensing terms
- Obtain annotation files (annotation-file inspection permitted)
- Verify D40 subset contains pothole annotations
- Count actual pothole instances in D40 from annotation files
- If exact counts cannot be established, mark counts as UNVERIFIED
- Check bounding box format
- Verify official licensing terms
- Document findings

**CRITICAL:** Do NOT download full image datasets yet. Metadata and annotation-file inspection is permitted during auditing. Full image downloads must wait until all audits, licensing checks, and class mappings are complete.

---

### PHASE 2: DATASET AUDITING (Weeks 2–3)

**Planning-estimate only:** the effort for this phase is approximately 8–10 hours, but this is not a verified duration and may change depending on dataset access, annotation availability, and licensing review requirements.

**Step 5: Audit Open Images V7**

- Inspect official metadata, licensing, and class definitions (metadata inspection permitted)
- Obtain annotation files and documentation (annotation-file inspection permitted when accessible)
- List candidate class matches for Mobility Companion classes
- Count actual annotated instances per class from annotation files or authoritative metadata
- If exact counts cannot be established, mark counts as UNVERIFIED
- Verify annotation types per release and task
- Note which classes are under-represented

**Step 6: Audit COCO 2017**

- Inspect official metadata, licensing, and class definitions (metadata inspection permitted)
- Obtain annotation files (annotation-file inspection permitted when accessible)
- Identify candidate classes
- Count actual instance annotations per class from annotation files
- If exact counts cannot be established, mark counts as UNVERIFIED
- Verify annotation types per task (bounding boxes, segmentation, etc.)
- Note mask-to-bbox conversion requirements

**Step 7: Audit BDD100K**

- Verify official licensing terms and usage restrictions
- Obtain official label-format specification and annotation files (annotation-file inspection permitted when accessible)
- Inspect annotation classes and format
- Count actual available annotations for candidate classes from annotation files
- If exact counts cannot be established, mark counts as UNVERIFIED
- Verify annotation types per task

**Step 8: Audit Other Candidate Datasets**

- Systematically audit ScanNet, NYU Depth V2, Cityscapes, KITTI, nuScenes, ADE20K
- Obtain annotation files and official documentation (annotation-file inspection permitted when accessible)
- Document format (3D, segmentation, bounding boxes, image-level)
- Count actual annotations per class where possible; mark UNVERIFIED if counts cannot be established
- Verify official licensing and usage restrictions
- Flag datasets requiring data format conversion

**Step 9: Generate Coverage Matrix**

Create summary table:
- Rows: Mobility Companion classes (0–36)
- Columns: Each candidate dataset
- Cells: Actual annotation counts from annotation files or authoritative metadata; mark UNVERIFIED if counts cannot be established; mark "N/A" / "Insufficient" / "Not Available" for unavailable data
- Identify coverage gaps
- Document all licensing terms

---

### PHASE 3: CLASS MAPPING & ALIGNMENT (Week 4)

**Step 10: Define Class Mapping Strategy**

For each Mobility Companion class, document:
- Which dataset(s) provide this class
- Explicit mapping rationale (not name similarity alone)
- Verification method (e.g., "manually reviewed sample images")
- Annotation count if known (or UNVERIFIED if not established)
- Annotation type per dataset

**Step 11: Flag Unmappable or Low-Coverage Classes**

Identify classes with insufficient coverage:
- If coverage < 100 images: Flag as "low coverage" (preliminary screening only; not proof of sufficient training data)
- If no candidate dataset: Flag as "missing dataset"
- Recommend data collection strategy (synthetic, manual, or alternative dataset)

**Step 12: Design Mask-to-BBox Conversion (If Needed)**

For datasets with segmentation masks:
- Choose conversion strategy (axis-aligned bounding box, oriented box, etc.)
- Implement conversion on sample data
- Manually validate converted boxes against original masks
- Document precision loss (if any)
- Finalize conversion procedure before downloading full dataset

---

### PHASE 4: ANDROID FOUNDATION IN PARALLEL (Allowed, but not integration-ready)

**Android foundation work may proceed in parallel with dataset auditing**, but it must be treated as a separate foundation effort.

**Allowed:**
- Project directory structure and Kotlin module organization
- CameraX camera access scaffolding (frame capture, permissions, lifecycle)
- Model-export research and testing framework
- On-device inference pipeline research and API exploration
- UI and accessibility planning (TextToSpeech integration)
- Build configuration and dependency setup

**Not yet ready:**
- Model integration into app
- Safety-critical navigation decisions
- Real-time inference validation
- Deployment assumptions based on untested model performance

**Final model integration and safety-critical navigation guidance require appropriate validation before deployment.**

---

### PHASE 5: SKIP TRAINING FOR NOW

❌ **Do NOT begin data download or model training yet.**

Full image-dataset downloads and model training will proceed only after:
1. All dataset audits are complete
2. Official licensing terms are confirmed for all datasets
3. Annotation types are verified per release and task
4. Class mappings are documented with rationale
5. Coverage gaps are identified
6. Mask-to-bbox conversion (if needed) is validated
7. Data preparation pipeline is designed and tested on sample data

---

## Summary: Current Project State

| Component | Status | Next Action |
|-----------|--------|-------------|
| **Repository Structure** | ❌ Empty (except README) | Prepare planning files for review (approval required before commit) |
| **37-Class Mapping** | ✓ Defined and Verified | Ready for commitment (awaiting approval) |
| **Dataset Plan** | ⚠️ Theoretical | Complete audits (Phases 1–2) |
| **Dataset Registry** | ⚠️ Candidate list | Update with audit findings |
| **Licensing Verification** | ❌ UNVERIFIED | Verify official terms per dataset |
| **Annotation Counts** | ❌ NOT verified from annotation files | Count actual instances per class; mark UNVERIFIED if unavailable |
| **Annotation Types** | ❌ NOT verified per task | Verify for each release and task |
| **Android Architecture** | ❌ Absent | Foundation work may proceed in parallel |
| **Training Pipeline** | ⚠️ Framework | Finalize after Phase 2 audits |
| **Safety Validation** | ❌ Undefined | Design human-curated test set in Phase 3 |
| **Documentation** | ✓ This Report | Review before any approval |

---

## Final Project Status and Conclusion

Mobility Companion is in the PLANNING AND AUDIT PHASE.

The GitHub repository is minimal (only README.md). Planning files are reported to exist on Google Drive but are not accessible to this GitHub repository. No training has begun.

### Immediate Priorities

- Review the three proposed files: class_mapping.yaml, dataset_registry.csv, and AUDIT_REPORT.md.
- Obtain explicit approval before committing the planning files.
- Complete systematic audits of each candidate dataset, including RDD2022, Open Images V7, COCO 2017, BDD100K, and other candidates.
- Count actual annotation instances per class from annotation files or authoritative metadata. If exact counts cannot be established, mark them UNVERIFIED.
- Verify official licensing terms for each dataset.
- Verify annotation types for each release and task.
- Document class mappings with explicit rationale and verification evidence.
- Identify coverage gaps and missing datasets.
- Design and test the data-preparation pipeline after the required audits are complete.

### Dataset Download and Training Restrictions

Full image-dataset downloads and model training MUST remain blocked until the required audits are complete, official licensing terms are confirmed, annotation types are verified, and class mappings are documented.

Metadata inspection and permitted annotation-file inspection are allowed during auditing. These activities do not authorize downloading full image datasets.

### Android Development

Android foundation development may proceed in parallel with dataset auditing. This includes Kotlin project structure, CameraX setup, UI development, accessibility features, and on-device inference research.

Final model integration, real-time inference claims, and safety-critical navigation guidance require appropriate testing and validation before deployment.

### Important Verification Notes

- Preserve the authoritative 37-class mapping exactly. Do not rename, reorder, merge, or invent class IDs.
- The comparison between the Google Drive class_mapping.yaml and the proposed GitHub version remains PENDING until actually completed.
- RDD2022's D40-to-pothole mapping remains UNVERIFIED until the annotation audit confirms it.
- Dataset annotation counts must not be estimated and presented as verified facts. If exact counts cannot be established, mark them UNVERIFIED.
- Dataset licensing and annotation-format availability must remain UNVERIFIED until supported by evidence.
- Do not claim that any dataset is approved for training until its required audits are complete.
- The preliminary 17-class coverage gap remains subject to completion of the remaining candidate-dataset audits.

---

## Conclusion

**Mobility Companion is in the PLANNING AND AUDIT PHASE.**

The GitHub repository is minimal (only README.md). Planning files are reported to exist on Google Drive but are not accessible to this GitHub repository. No training has begun.

**Immediate Priority:**
1. ✓ Review the three proposed files (class_mapping.yaml, dataset_registry.csv, AUDIT_REPORT.md)
2. ✓ Grant explicit approval before any commit
3. ✓ Complete systematic audits of each candidate dataset (RDD2022, Open Images V7, COCO, BDD100K, and others)
4. ✓ Count actual annotation instances per class from annotation files or authoritative metadata; mark UNVERIFIED if counts cannot be established
5. ✓ Verify official licensing terms for each dataset
6. ✓ Verify annotation types per release and task
7. ✓ Document class mappings with explicit rationale
8. ✓ Identify coverage gaps and missing datasets
9. ✓ Design data preparation pipeline (after audits are complete)

**Full image-dataset downloads and model training will remain blocked until audits are complete, licensing is confirmed, annotation types are verified, and class mappings are documented.**

**Android foundation work may proceed in parallel with dataset auditing. Final model integration and safety-critical navigation guidance require appropriate validation before deployment.**

---

**Report Prepared:** 2026-10-10  
**Status:** Awaiting Explicit Approval Before Commit
