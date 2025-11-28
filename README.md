Code Files for Hybrid Embedding Fusion Framework
=================================================

This file lists all source code scripts used in the research 
“A Lightweight Hybrid Embedding Fusion Framework for Face Verification”.

All files below are cleanly categorized according to their function:
- Embedding generation
- Baseline evaluation
- Single-feature experiments
- Two-feature fusion
- Three-feature fusion
- Utilities

No augmentation-related files are listed, as requested.


--------------------------------------------------
1. Embedding Generation (Precompute Stage)
--------------------------------------------------
These scripts generate all deep embeddings used throughout the experiments.
Embeddings are computed once, stored, and reused by all downstream pipelines.

    benchmark3_batchEmbeddingALL.py
        - Generates embeddings for all backbone models.
        - Saves output to: outputs/embeddings/


--------------------------------------------------
2. Baseline Evaluation (Single Model Performance)
--------------------------------------------------
These scripts evaluate individual backbone models using various metrics
to produce baseline accuracy tables (e.g., Table 4).

    magface_multi_eval.py
        - Evaluates MagFace (and others if configured)
        - Writes performance tables into outputs/baseline/

    baseline_single_distance_adaface_all.py
        - Baseline AdaFace evaluation across detectors/metrics.

    baseline_single_distance_magface_all.py
        - Baseline MagFace evaluation across full combinations.

    baseline_single_distance_magface.py
        - Baseline MagFace specific-distance evaluation.

    baseline_single_distance_cv.py
        - Performs 10-fold cross-validation baseline.
        - Produces: single_baseline_cv.xlsx and single_baseline_cv_10fold.xlsx


--------------------------------------------------
3. Single-Feature Machine Learning Evaluation
--------------------------------------------------
This script evaluates AdaFace (or other chosen features) using several 
ML classifiers to find the best-performing single-feature pipeline.

    run_in_batches_all.py
        --mode single_feature
        --embeddings outputs/embeddings/
        --out outputs/single_feature/


--------------------------------------------------
4. Two-Feature Fusion (All Combinations)
--------------------------------------------------
Enumerates and evaluates all possible two-backbone fusion pairs
using a single ML classifier.

    fusion_2Model.py
        - Performs two-feature fusion experiments.
        - Generates results for:
            C.1. two feature-single ML results.xlsx


--------------------------------------------------
5. Three-Feature Fusion (All Combinations)
--------------------------------------------------
Enumerates and evaluates all possible three-backbone combinations 
using a single ML classifier.

    fusion_3Model.py
        - Performs three-feature fusion experiments.
        - Generates results for:
            D.1. three feature-single ML results.xlsx


--------------------------------------------------
6. Utility & Supporting Scripts
--------------------------------------------------

    evaluate_utils.py
        - Helper functions for evaluation, similarity metrics, scoring.

    convert.py
        - Converts intermediate outputs or formats where needed.

    net.py
        - Contains model definitions/utilities used across the pipeline.


--------------------------------------------------
End of README_CODE_ONLY.txt
--------------------------------------------------
