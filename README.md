# MIS 495 | Hiệp Thủy E-commerce Analytics

A completed team consulting project for **Vật tư Nông nghiệp Hiệp Thủy**, an agricultural supplies retailer in Vietnam. The project used competitor analysis and Vietnamese customer-review analytics to support assortment and customer-experience recommendations, with a focus on assessing expansion opportunities in northern Vietnam.

**Status:** Completed and handed over to Hiệp Thủy.

## Business questions

- Which seed-product categories offer opportunities to extend the retailer's assortment?
- What do customers value, and which service or product issues recur in reviews?
- How does Hiệp Thủy compare with competing shops, and which improvements should be prioritized?

## Approach

1. Consolidate Shopee product and review snapshots and check duplicate records and analysis eligibility.
2. Benchmark seed assortments against Hà Bắc, Quang Anh VNUA, and Vườn Babylon.
3. Classify Vietnamese review sentiment using ViSoBERT.
4. Analyze review themes and compare customer-experience signals across shops.
5. Translate findings into business recommendations and presentation materials.

Exploratory work also used rule-based aspect tagging and TF-IDF + NMF topic modeling. These earlier experiments are distinct from the seven-theme analysis used in the later project outputs.

## Final reporting scope

| Measure | Project snapshot |
| --- | ---: |
| Product listings across the overall dataset | 1,889 |
| Seed listings | 794 |
| Hiệp Thủy seed listings | 111 |
| Competitor seed listings | 683 |
| Competitor listings used in the 16-group opportunity analysis | 682 |
| Text reviews before duplicate removal | 47,622 |
| Master reviews after removing 156 duplicate records | 47,466 |
| Reviews eligible for final sentiment analysis | 47,465 |
| Hiệp Thủy reviews eligible for final sentiment analysis | 9,575 |

One multi-family Hà Bắc listing was excluded from the 16-group opportunity analysis. Seed market-gap analysis and whole-assortment sentiment analysis have different scopes.

## My contribution

**Thy Nguyễn** contributed sentiment analysis, aspect-level summaries, and topic interpretation, and supported data preparation and topic modeling within the team. The wider project was a collaborative delivery.

## Interpretation and limitations

- The data represent historical project snapshots, not live prices or current market conditions.
- Cumulative sales and review counts are demand indicators, not revenue forecasts.
- Model-based sentiment and rule-based themes require independent validation. Technical pipeline checks do not establish predictive accuracy.
- Whole-assortment review findings should not be presented as seed-only findings.
- Assessing northern expansion also requires regional customer, shipping-cost, delivery-time, and pilot-order evidence.

## Repository contents

| File | Purpose |
| --- | --- |
| [01_Sentiment_ABSA_Topics.ipynb](01_Sentiment_ABSA_Topics.ipynb) | ViSoBERT sentiment, rule-based aspects, NMF topics and six-sheet Excel export |
| [02_Seed_Market_Gap.ipynb](02_Seed_Market_Gap.ipynb) | Competitor assortment, price quartiles, category opportunities and five-sheet Excel export |
| [RUNNING.md](RUNNING.md) | Input requirements, execution instructions and version boundaries |

The notebooks are historical development artifacts selected for their self-contained code and quality checks. Their snapshots differ from the final reporting scope above: sentiment uses the earlier six-aspect/NMF pipeline; market-gap uses 791 seed listings and 17 groups. They are not represented as reproducing the final seven-theme/794-listing report.

Raw customer-review records, internal working files and final client reports are not distributed in this repository.

## Tools

Python · pandas · Google Colab · ViSoBERT · scikit-learn · Excel
