# Running the historical notebooks

These notebooks document the project's development work. Original code is preserved; notebook outputs and cell metadata are cleared, and a version note is added. Original local files remain unchanged.

## Sentiment, aspects and topics

Open [01_Sentiment_ABSA_Topics.ipynb in Colab](https://colab.research.google.com/github/thynguyen1120/MIS-495/blob/main/01_Sentiment_ABSA_Topics.ipynb), select a T4 GPU runtime, then run the cells in order.

The input is the original `reviews_master_text_v1.csv`, with 47,466 review records and SHA-256 `8dc7ea0a9b6999438c47f85eb210bfd6aa604662f8937f4b5d24b3daeef07c00`. The checksum check deliberately rejects a different dataset. Obtain the authorized original dataset separately; it is not part of this public repository.

The notebook preserves Vietnamese text, pins the ViSoBERT model revision, computes three sentiment scores, applies six rule-based aspect definitions, runs TF-IDF + NMF, and exports six Excel sheets. Its historical snapshot expects 41,232 positive, 3,204 negative, 3,023 neutral and 7 unclassified reviews. These are earlier development counts, not the later final-report classification counts.

The selected STABLE V2 installs additional packages while preserving the runtime's NumPy, pandas and Matplotlib. It retains input, score, lineage and workbook checks. It was selected over the earlier dependency-changing notebook and the later submission copy with export QA removed. Fixed dependency versions and snapshot assertions may require maintenance when run in a different environment; investigate failures rather than bypassing checks.

## Seed market-gap analysis

Open [02_Seed_Market_Gap.ipynb in Colab](https://colab.research.google.com/github/thynguyen1120/MIS-495/blob/main/02_Seed_Market_Gap.ipynb). A GPU is not required. Run cells in order and upload these four CSVs, either individually or in a ZIP:

- `gia san pham - Ha Bac.csv`
- `gia san pham - Quang Anh VNUA.csv`
- `gia san pham - Vuon Babylon.csv`
- `gia san pham - Hiep Thuy (shop minh).csv`

The input schema and taxonomy are specified in the notebook's analysis code. An optional reference workbook supports cell-value comparison. Outputs include intermediate CSV/JSON tables, a five-sheet workbook and a QA report.

This notebook uses the July 28, 2026 snapshot: 680 competitor seed listings plus 111 Hiệp Thủy listings, across 17 groups. Its counts must not be mixed with the later 794-listing snapshot and 16-group analysis described in the repository overview.

## Verification and interpretation

For this publication, all 39 Python code cells across the two notebooks passed syntax inspection, with Colab `%%writefile` directives handled separately. No code logic was changed. Full inference and end-to-end workbook generation were not rerun for this publication. Historical project records document successful runs and workbook checks; these are not a guarantee of compatibility with a future Colab runtime.

The original data are required to reproduce results; this repository is not a data-free runnable demo. Validation samples contain model predictions until independently labeled. Technical QA, agreement with rules and star ratings do not establish model accuracy. Topic names apply to the historical fitted model, not arbitrary new datasets.
