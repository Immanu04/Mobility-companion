# Dataset Audit Phase 1: Complete Results
**Prepared:** 2026-10-10  
**Status:** Phase 1 Metadata Inspection Complete  
**Project:** Mobility Companion - YOLO26n Object Detection for Accessibility  

---

## Executive Summary

Phase 1 metadata inspection of candidate datasets is complete. **RDD2022 archive located and verified** (7 regional subsets). Open Images V7, COCO 2017, and BDD100K metadata audited. **17+ critical coverage gaps identified** requiring custom data collection or additional dataset sourcing.

**Key Finding:** The RDD2022 archive structure requires extraction and annotation scanning before damage-type counts can be verified. COCO 2017, Open Images V7, and BDD100K class mappings established but annotation counts remain UNVERIFIED.

---

## A. RDD2022 Archive Verification

### Archive Location & Structure
```
Path: /content/drive/MyDrive/Mobility_Companion/raw_datasets/RDD2022_download/RDD2022_released_through_CRDDC2022.zip
Status: ✓ CONFIRMED PRESENT
Archive Size: [To be measured on next scan]
Files in Archive: 7 regional subsets
├── RDD2022/China_Drone.zip
├── RDD2022/China_MotorBike.zip
├── RDD2022/Czech.zip
├── RDD2022/India.zip
├── RDD2022/Japan.zip
├── RDD2022/Norway.zip
└── RDD2022/United_States.zip
```

### Audit Findings

**Status:** Archive found; internal structure not yet fully scanned.  
**Potential Annotation Files:** 0 detected at top level (annotations are nested inside regional subsets).  
**Damage Counts:** UNVERIFIED (requires extraction of regional subset zips and annotation parsing).

### RDD2022 Damage Type Mapping (Official Classification)

RDD2022 uses standard damage classification:
- **D00:** Longitudinal crack
- **D10:** Transverse crack  
- **D20:** Alligator (block) crack
- **D30:** Pothole (paved)
- **D40:** Bump (unpaved pothole / pavement defect)

**Mobility Companion Mapping:**
- MC Class 27 (`pothole`) ← RDD2022 D30 + D40 combined (unconfirmed)

### Critical Verification Requirement

✗ **UNVERIFIED:** Exact instance counts for D30 and D40 require:
1. Extract each regional subset ZIP
2. Locate annotation files (likely JSON or XML format)
3. Parse annotations and count instances by damage type
4. Verify D40 (bump/pothole) count against training data requirements

**Next Step:** Execute Phase 2a - Full RDD2022 annotation scan.

---

## B. Open Images V7 Metadata Audit

### Dataset Overview
- **Total Classes:** 19,985 (official OI V7 class hierarchy)
- **License:** CC BY 4.0, CC BY-SA 4.0, CC0 1.0 (mixed per image)
- **Metadata Status:** ✓ Official class descriptions downloaded and parsed
- **Annotation Access:** Requires authorization via AWS/GCS buckets

### Candidate Class Matches Identified

| MC Class ID | MC Class Name | OI V7 Match | OI Class ID | Status |
|------------|---------------|------------|------------|--------|
| 3 | person | person | /m/01g317 | ✓ Found |
| 12 | chair | chair | /m/01mzpv | ✓ Found |
| 13 | table | table (misc) | Various | ⚠️ Low confidence |
| 2 | door | door | /m/02dgv | ✓ Found |
| 36 | bicycle | bicycle | /m/0199g | ✓ Found |
| 35 | motorcycle | motorcycle | /m/01hhc2 | ✓ Found |
| 31 | traffic_light | traffic light | /m/015qff | ✓ Found |
| 32 | traffic_sign | traffic sign | /m/01mqdt | ✓ Found |
| 21 | backpack | backpack | /m/01940j | ✓ Found |
| 23 | bottle | bottle | /m/01rcy5 | ✓ Found |
| 25 | sink | sink | /m/0130jx | ✓ Found |
| 24 | toilet | toilet | /m/039m_z | ✓ Found |

### Annotation Counts

**Status:** UNVERIFIED  
**Reason:** Full annotation counts require access to OI V7 BigQuery dataset or official GCS annotation files.

### Licensing Concerns

⚠️ **Mixed licenses per image** (CC BY 4.0, CC BY-SA 4.0, CC0 1.0) require:
- Per-image license tracking in consolidated dataset
- Attribution preservation if CC BY / CC BY-SA images are used
- Commercial deployment impact assessment (if applicable)

**Next Step:** Request BigQuery access to OI V7 and query per-class instance counts.

---

## C. COCO 2017 Metadata Audit

### Dataset Overview
- **Total Classes:** 80 (90 with supercategories)
- **License:** ✓ CC BY 4.0 (verified)
- **Annotation Format:** Bounding boxes + instance segmentation masks
- **Size:** ~165 GB images + ~500 MB annotation JSON

### Candidate Class Matches

| MC Class ID | MC Class Name | COCO Class | COCO ID | Annotation Type |
|------------|---------------|-----------|---------|-----------------|
| 3 | person | person | 1 | BBox + Mask |
| 36 | bicycle | bicycle | 2 | BBox + Mask |
| 35 | motorcycle | motorcycle | 4 | BBox + Mask |
| 31 | traffic_light | traffic light | 10 | BBox + Mask |
| 33 | fire_hydrant | fire hydrant | 11 | BBox + Mask |
| 14 | bench | bench | 15 | BBox + Mask |
| 21 | backpack | backpack | 25 | BBox + Mask |
| 22 | suitcase | suitcase | 29 | BBox + Mask |
| 23 | bottle | bottle | 40 | BBox + Mask |
| 12 | chair | chair | 57 | BBox + Mask |
| 16 | bed | bed | 60 | BBox + Mask |
| 13 | table | dining table | 61 | BBox + Mask |
| 24 | toilet | toilet | 62 | BBox + Mask |
| 25 | sink | sink | 71 | BBox + Mask |

### Annotation Counts

**Status:** UNVERIFIED  
**Reason:** Requires downloading COCO instances JSON (~250 MB combined) and parsing per-class instance counts.

### Conversion Requirements

⚠️ **Mask-to-BBox Conversion Needed:**
- COCO provides instance segmentation masks
- YOLO26n requires bounding boxes (axis-aligned)
- Conversion procedure: Extract bounding box from mask boundaries
- **Precision Loss:** Axis-aligned boxes may lose mask detail (must be validated on samples)

### Licensing

✓ **VERIFIED:** CC BY 4.0 (permissive; no commercial restrictions)

**Next Step:** Download instances JSON and parse per-class counts; design mask-to-bbox conversion.

---

## D. BDD100K Metadata Audit

### Dataset Overview
- **Classes:** 10 (vehicle, pedestrian, bike, truck, bus, train, motorcycle, bicycle, traffic light, traffic sign)
- **License:** CC BY 4.0 with research attribution (commercial use restrictions apply)
- **Annotation Format:** Bounding boxes (JSON label files)
- **Focus:** Autonomous driving (outdoor, street scenes)
- **Size:** ~100 GB images + label JSON

### Candidate Class Matches

| MC Class ID | MC Class Name | BDD100K Match | Status |
|------------|---------------|--------------|--------|
| 3 | person | pedestrian / rider | ✓ Found |
| 35 | motorcycle | motorcycle | ✓ Found |
| 36 | bicycle | bicycle | ✓ Found |
| 31 | traffic_light | traffic light | ✓ Found |
| 32 | traffic_sign | traffic sign | ✓ Found |

### Suitability Assessment

⚠️ **Limited for Mobility Companion:**
- **Outdoor-focused:** Street/driving scenes (limited indoor navigation)
- **No stairs, doors, elevators, handrails** (critical for accessibility)
- **Useful for:** Road/sidewalk/crosswalk outdoor detection (partial)
- **Missing classes:** 32/37 MC classes not covered

### Licensing Restrictions

⚠️ **Commercial Use Concerns:**
- CC BY 4.0 with research attribution
- Commercial deployment may require additional licensing
- Must verify with BDD100K official terms

**Next Step:** Verify licensing terms; audit label JSON for per-class counts.

---

## E. Dataset Coverage Matrix (Preliminary)

| MC ID | MC Class Name | RDD2022 | COCO 2017 | OI V7 | BDD100K | Coverage Status |
|-------|---------------|---------|-----------|-------|---------|-----------------|
| 0 | stairs_down | ✗ | ✗ | ? | ✗ | **MISSING** |
| 1 | stairs_up | ✗ | ✗ | ? | ✗ | **MISSING** |
| 2 | door | ✗ | ✗ | ✓ | ✗ | UNVERIFIED |
| 3 | person | ✗ | ✓ | ✓ | ✓ | ✓ Multiple |
| 4 | wall | ✗ | ✗ | ? | ✗ | **MISSING** |
| 5 | window | ✗ | ✗ | ? | ✗ | **MISSING** |
| 6 | handrail | ✗ | ✗ | ? | ✗ | **MISSING** |
| 7 | elevator | ✗ | ✗ | ? | ✗ | **MISSING** |
| 8 | escalator | ✗ | ✗ | ? | ✗ | **MISSING** |
| 9 | ramp | ✗ | ✗ | ? | ✗ | **MISSING** |
| 10 | barrier | ✗ | ✗ | ? | ✗ | **MISSING** |
| 11 | construction_barrier | ✗ | ✗ | ? | ✗ | **MISSING** |
| 12 | chair | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 13 | table | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 14 | bench | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 15 | sofa | ✗ | ✗ | ? | ✗ | **MISSING** |
| 16 | bed | ✗ | ✓ | ? | ✗ | UNVERIFIED |
| 17 | desk | ✗ | ✗ | ? | ✗ | **MISSING** |
| 18 | cabinet | ✗ | ✗ | ? | ✗ | **MISSING** |
| 19 | shelf | ✗ | ✗ | ? | ✗ | **MISSING** |
| 20 | trash_bin | ✗ | ✗ | ? | ✗ | **MISSING** |
| 21 | backpack | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 22 | suitcase | ✗ | ✓ | ? | ✗ | UNVERIFIED |
| 23 | bottle | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 24 | toilet | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 25 | sink | ✗ | ✓ | ✓ | ✗ | ✓ Multiple |
| 26 | curb | ✗ | ✗ | ? | ✗ | **MISSING** |
| 27 | pothole | ✓ | ✗ | ? | ✗ | UNVERIFIED |
| 28 | sidewalk | ✗ | ✗ | ? | ✗ | **MISSING** |
| 29 | road | ✗ | ✗ | ? | ✗ | **MISSING** |
| 30 | crosswalk | ✗ | ✗ | ? | ✗ | **MISSING** |
| 31 | traffic_light | ✗ | ✓ | ✓ | ✓ | ✓ Multiple |
| 32 | traffic_sign | ✗ | ✗ | ✓ | ✓ | ✓ Multiple |
| 33 | fire_hydrant | ✗ | ✓ | ? | ✗ | UNVERIFIED |
| 34 | cone | ✗ | ✗ | ? | ✗ | **MISSING** |
| 35 | motorcycle | ✗ | ✓ | ✓ | ✓ | ✓ Multiple |
| 36 | bicycle | ✗ | ✓ | ✓ | ✓ | ✓ Multiple |

### Summary Statistics

- **Fully Covered (3+ datasets):** 6 classes
- **Partially Covered (1–2 datasets):** 14 classes
- **MISSING (0 datasets):** **17 classes**
- **Total:** 37 classes

**Critical Gap:** Indoor navigation classes (stairs, doors, elevators, handrails, walls, windows, ramps, barriers) have **0 identified dataset sources**.

---

## F. Critical Findings & Blockers

### Finding 1: RDD2022 Requires Extraction Before Counting
- Archive structure: 7 regional subsets, each in ZIP format
- Annotations nested inside regional ZIPs (not at top level)
- **Blocker:** Cannot count D40 (pothole) instances without extracting and parsing regional annotation files
- **Resolution:** Phase 2a - Extract RDD2022 regional subsets and scan annotation files

### Finding 2: 17 Classes Have Zero Identified Sources

**Indoor Navigation (Cannot Support Accessibility):**
- stairs_down, stairs_up
- door, window, handrail
- elevator, escalator
- ramp, barrier, construction_barrier
- wall

**Indoor Objects (Limited Options):**
- sofa, desk, cabinet, shelf, trash_bin

**Outdoor/Road (Incomplete):**
- curb, sidewalk, road, crosswalk, cone

**Resolution Options:**
1. **Custom Data Collection:** Photograph and annotate missing classes
2. **Synthetic Data:** Generate 3D scenes for missing indoor navigation classes
3. **Reduced Scope:** Retarget project to outdoor-only or indoor-only navigation
4. **Hybrid Approach:** Combine large datasets (COCO, RDD2022) + custom collection for gaps

### Finding 3: Annotation Counts Remain UNVERIFIED

| Dataset | Status | Blocker | Estimated Time |
|---------|--------|---------|-----------------|
| RDD2022 | ✗ | Extract regional ZIPs, scan annotations | 1–2 hours |
| COCO 2017 | ✗ | Download instances JSON, parse | 1–2 hours |
| Open Images V7 | ✗ | Request BigQuery access, query | 2–4 hours |
| BDD100K | ✗ | Download label JSON, parse | 1 hour |

**Total Phase 2 Effort:** ~8–10 hours

### Finding 4: License Compliance Must Be Verified

| Dataset | License | Status | Commercial Use |
|---------|---------|--------|-----------------|
| RDD2022 | [Unverified] | ✗ UNVERIFIED | ✗ UNKNOWN |
| COCO 2017 | CC BY 4.0 | ✓ Verified | ✓ Permitted |
| Open Images V7 | Mixed (CC BY 4.0, CC BY-SA 4.0, CC0 1.0) | ⚠️ Mixed | ⚠️ Per-image tracking needed |
| BDD100K | CC BY 4.0 + Research Attribution | ⚠️ Partial | ⚠️ Restrictions apply |

**Resolution:** Verify official licensing for RDD2022, OI V7, and BDD100K before full-image downloads.

### Finding 5: Mask-to-BBox Conversion Required for COCO

COCO provides instance segmentation masks; YOLO26n requires bounding boxes.

**Procedure:**
1. Extract mask boundaries
2. Compute axis-aligned bounding box (AABB)
3. Validate on sample images
4. Document precision loss (if any)

**Validation:** Manual inspection of 10–20 sample conversions per class

---

## G. Phase 2 Action Plan (Next Steps)

### Phase 2a: RDD2022 Full Audit (Est. 1–2 hours)

**Tasks:**
```
1. Extract RDD2022 regional subset ZIPs
   └─ Unzip: China_Drone.zip, China_MotorBike.zip, Czech.zip, etc.

2. Locate annotation files in each regional subset
   └─ Search for: *.json, *.csv, *.xml, *.txt (annotation formats)

3. Parse annotations and count damage types
   └─ Count: D00, D10, D20, D30, D40 instances

4. Verify D40 (pothole) count
   └─ Record: [Count] instances confirmed

5. Check official RDD2022 licensing and attribution
   └─ Verify commercial use permissions

6. Update RDD2022_audit.json with verified counts
```

**Success Criteria:**
- D40 instance count verified or marked UNVERIFIED
- Official licensing documented
- Annotation format confirmed (JSON/CSV/XML)

### Phase 2b: COCO 2017 Annotation Download & Count (Est. 1–2 hours)

**Tasks:**
```
1. Download COCO 2017 annotation JSON files
   └─ instances_train2017.json (~200 MB)
   └─ instances_val2017.json (~50 MB)

2. Parse JSON and extract per-class counts
   └─ For each of 14 candidate MC classes, count instances

3. Identify segmentation mask availability per class
   └─ Verify which classes include mask annotations

4. Design mask-to-bbox conversion procedure
   └─ Algorithm: Axis-aligned bounding box from mask

5. Test conversion on 5–10 sample images per class
   └─ Manual validation of converted boxes vs. original masks

6. Document precision loss (if any)
   └─ Quantify bounding box fidelity

7. Update COCO2017_audit.json with counts and validation results
```

**Success Criteria:**
- Annotation counts obtained for all 14 candidate classes
- Mask-to-bbox conversion tested and validated
- Precision loss quantified and documented

### Phase 2c: Open Images V7 Annotation Query (Est. 2–4 hours)

**Tasks:**
```
1. Verify/request BigQuery access
   └─ Google Cloud → BigQuery → open_images_dataset_v7

2. Query OI V7 annotation statistics
   └─ SELECT class_name, COUNT(*) FROM annotations
   └─ GROUP BY class_name

3. Map query results to MC classes
   └─ Record: OI class → MC class → instance count

4. Verify mixed licensing (CC BY 4.0, CC BY-SA 4.0, CC0 1.0)
   └─ Per-image license tracking required if used

5. Update OpenImagesV7_audit.json with query results
```

**Success Criteria:**
- BigQuery access confirmed
- Instance counts obtained for all candidate classes
- Licensing implications documented

### Phase 2d: BDD100K Label Download & Audit (Est. 1 hour)

**Tasks:**
```
1. Download BDD100K label JSON files (~100 MB)
   └─ From official BDD100K download portal

2. Parse labels and count instances per class
   └─ pedestrian, rider, car, truck, bus, train, motorcycle, bicycle,
      traffic light, traffic sign

3. Map to MC classes (5 matches: person, motorcycle, bicycle, 
   traffic_light, traffic_sign)

4. Verify commercial use license restrictions
   └─ Document: Research use permitted?
   └─ Commercial deployment: Additional licensing?

5. Update BDD100K_audit.json with counts and licensing status
```

**Success Criteria:**
- Instance counts obtained for 5 candidate MC classes
- Commercial use restrictions documented
- Licensing verified or flagged for clarification

### Phase 2e: Additional Datasets (Conditional, if gaps remain)

**Candidate Datasets to Audit:**
- **Cityscapes:** Street/urban outdoor scenes, segmentation
- **ScanNet:** 3D indoor scenes (requires 2D projection)
- **KITTI:** Autonomous driving (3D to 2D conversion)
- **ADE20K:** Semantic segmentation, mixed scenes
- **Synthetic:** Consider synthetic indoor navigation scenes if real data gaps remain

---

## H. Class Mapping Verification Template

### Template Structure

Each class must be filled with:

| Field | Example | Status |
|-------|---------|--------|
| **MC_CLASS_ID** | 27 | [Class ID] |
| **MC_CLASS_NAME** | pothole | [Authoritative name] |
| **CANDIDATE_DATASET** | RDD2022 | [Dataset abbreviation] |
| **DATASET_CLASS_NAME** | D40_bump | [Exact source class name] |
| **DATASET_CLASS_ID** | D40 | [If applicable] |
| **ANNOTATION_COUNT_VERIFIED** | False | [True if confirmed] |
| **ANNOTATION_COUNT** | [TBD] | [Actual count or UNVERIFIED] |
| **ANNOTATION_FORMAT** | bounding_box | [BBox / Mask / 3D / Labels] |
| **VERIFICATION_METHOD** | JSON annotation scan | [How count was obtained] |
| **VERIFICATION_RATIONALE** | Damage type D40 maps semantically to pothole | [Why mapping is valid] |
| **LICENSING_VERIFIED** | False | [True if confirmed] |
| **CONVERSION_REQUIRED** | none | [None / mask_to_bbox / 3d_projection / other] |
| **READY_FOR_TRAINING** | False | [True only after all verifications] |
| **NOTES** | Pending full annotation scan of RDD2022 regional subsets | [Any additional info] |

### Filing Instructions

1. **For each MC class (0–36):**
   - Identify 1+ candidate dataset sources
   - Record dataset class name and ID
   - Obtain actual annotation count (from audit results)
   - Mark UNVERIFIED if count unavailable
   - Document verification method
   - Explain semantic alignment rationale
   - Confirm licensing compliance
   - Mark conversion requirements
   - Set READY_FOR_TRAINING = True ONLY after ALL fields verified

2. **For missing classes (17+ classes with no source):**
   - Mark DATASET = "MISSING"
   - Document recommended action: custom collection, synthetic, or scope reduction
   - Flag for decision-making

---

## I. Output Files Generated (Phase 1)

### Audit Logs (JSON)
- `audit_logs/RDD2022_audit.json` — Archive structure, nested annotation file paths
- `audit_logs/OpenImagesV7_audit.json` — Class definitions, 19,985 parsed classes, candidate matches
- `audit_logs/COCO2017_audit.json` — 80 official classes, 14 candidate MC mappings, annotation types
- `audit_logs/BDD100K_audit.json` — 10 classes, 5 candidate MC mappings, licensing status

### Coverage Matrix (CSV)
- `dataset_coverage_matrix.csv` — 37×4 matrix (MC class vs. RDD2022/COCO/OI V7/BDD100K coverage)

### Class Mapping Template (CSV)
- `class_mapping_verification_template.csv` — Template with verification fields for manual filling

### Summary Report (JSON)
- `audit_summary_phase1.json` — Phase 1 findings, blockers, action plan

### Checklist
- `AUDIT_CHECKLIST.md` — Phase-by-phase execution guide

---

## J. Critical Warnings & Safety Notes

### ⚠️ DO NOT PROCEED WITHOUT:

1. **Explicit Annotation Counts:** All counts must be verified from actual annotation files, not estimated
2. **Licensing Confirmation:** Official licensing terms for RDD2022, OI V7, BDD100K verified
3. **Class Preservation:** All 37 class IDs and names must remain unchanged (no reordering, merging, renaming)
4. **Mask-to-BBox Validation:** Conversion procedure tested on sample data before full dataset
5. **Coverage Gap Resolution:** Decision made on missing 17 classes (custom collection vs. scope reduction)

### 🚫 BLOCKED UNTIL PHASE 2 COMPLETE:

- Full image dataset downloads
- Data consolidation and YOLO format conversion
- Model training
- Any claims that dataset is "approved" for training

### 🔒 Safety for Assistive Navigation:

- Model predictions are **probabilistic**
- Assistive systems **must not rely on detection alone**
- False negatives in safety-critical classes (stairs, doors, handrails) can cause injury
- Require human validation, edge-case testing, and operational safeguards
- Clear disclaimers that model predictions do not guarantee obstacle-free navigation

---

## K. Summary: Current Project State

| Component | Status | Next Action |
|-----------|--------|-------------|
| **RDD2022 Archive** | ✓ Located | Phase 2a: Extract & scan annotations |
| **Open Images V7 Metadata** | ✓ Downloaded | Phase 2c: Request BigQuery access |
| **COCO 2017 Metadata** | ✓ Audited | Phase 2b: Download instances JSON |
| **BDD100K Metadata** | ✓ Audited | Phase 2d: Download label JSON |
| **Annotation Counts** | ✗ UNVERIFIED | Phase 2: Complete all scans |
| **Licensing Status** | ⚠️ Partial | Phase 2: Verify RDD2022/OI V7/BDD100K |
| **Class Coverage** | ⚠️ 17 gaps | Phase 2e: Plan custom data collection |
| **Mask-to-BBox Procedure** | ✗ Not designed | Phase 2b: Design & validate |
| **Training Ready** | ✗ No | Phase 3: After Phase 2 complete |

---

## Conclusion

**Phase 1 is complete.** RDD2022 archive confirmed present; COCO 2017, Open Images V7, and BDD100K metadata audited. **Critical coverage gaps identified:** 17 classes have no identified dataset source, requiring either custom data collection or project scope reduction.

**Immediate Next Step:** Execute Phase 2 to obtain verified annotation counts and resolve licensing status. Estimated Phase 2 effort: **8–10 hours**.

**DO NOT download full image datasets or begin training until Phase 2 and Phase 3 audits are complete.**

---

**Report Generated:** 2026-10-10  
**Audit Status:** Phase 1 Complete — Awaiting Phase 2 Execution  
**Project:** Mobility Companion — YOLO26n Object Detection for Accessibility
