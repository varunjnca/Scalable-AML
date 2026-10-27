# Scalable AML Transaction Monitoring and Fraud Alert Optimization

**Group:** Scalable AML

## Team Members

- Babak Davarmanesh (`bda52`)
- Varun Jain (`vja15`)
- Amogh Anant Shanbhag (`aas61`)
- Shaik Mohammed Hassan (`smh47`)

## Project Overview

Money laundering can involve complex transaction patterns that are difficult to identify by examining individual transactions in isolation. This project proposes a scalable Anti-Money Laundering (AML) monitoring system using IBM's AMLSim synthetic transaction dataset (Altman et al.). The system will combine streamed data processing, rule-based detection, graph-based relationship analysis, and statistical threshold optimization to generate and evaluate suspicious transaction alerts.

## Product

The final product is organized into the following phases:

1. **Data engineering and processing:** Apache Spark will be used to clean, transform, and process transaction data through a scalable ETL pipeline. The system will support batch processing and simulated streaming to evaluate performance under different transaction volumes. The dataset will be expanded to approximately 10–20 GB, subject to resource availability, and converted into a graph-based model.

2. **Rule-based detection and segmentation:** Multiple AML detection rules will identify suspicious behaviors, including transaction structuring, unusually high transaction frequency, and abnormal transaction amounts. K-means clustering will segment accounts based on behavioral features. For continuous variables, a percentile-jump methodology within the P05–P85 range will identify candidate thresholds; percentile-based or count-based thresholds will be evaluated for discrete variables. Rules and segmentation will be applied to the generated graph database(s).

3. **Alert generation dashboard:** Alerts will be generated from the rules and segmentation using tuned thresholds, then displayed on a dashboard.

4. **Optional, time permitting — evaluation and scorecard:** Generated alerts will be compared with AMLSim's available synthetic suspicious-activity labels, including Suspicious Activity Report (SAR)-related labels where appropriate. Precision, recall, false-positive rate, alert volume, and processing performance will be measured. Above-the-line/below-the-line (ATL/BTL) analysis will help assess threshold changes. If time permits, a supervised scorecard will combine transaction, rule-based, and graph-derived features to prioritize alerts and evaluate whether false positives can be reduced without substantially decreasing recall.

## Experimental Design

Most available historical transactions will be used for feature development, threshold selection, and model training, while a held-out portion will be reserved for evaluation and replayed as a simulated transaction stream. The split will preserve temporal ordering where possible, with thresholds and models fitted only on the training portion. Batch processing time, streaming throughput, latency, and detection metrics will be compared across experiments.

## Technologies

- Python
- Apache Spark and Spark Structured Streaming
- IBM AMLSim
- AWS
- scikit-learn
- Standard data visualization tools

## Timeline

The project is planned as a six-week effort.

| Week | Focus | Deliverables |
| --- | --- | --- |
| 1 | Data engineering | Generate realistic/dirty AMLSim data; set up the GitHub repository; build the Spark ETL pipeline. |
| 2 | Streaming and graph | Set up the graph database and implement streaming. |
| 3 | Rules and segmentation | Decide and implement fraud-detection rules (including abnormal amounts and candidate thresholds); implement segmentation. |
| 4 | Tuning, evaluation, and dashboard | Tune thresholds; evaluate alerts against AMLSim labels (precision, recall, false-positive rate, and alert volume); build the alerts dashboard; optionally develop a supervised scorecard; integrate components. |
| 5 | Scale testing and wrap-up | Run integration tests with a larger (10–20 GB) dataset and evaluate performance; write the final report; prepare the demo and final presentation. |
| 6 | Buffer and improvements | Reserve time for testing, debugging, integration, and polishing the report, demo, and presentation. If time permits, improve the system with machine learning, false-positive reduction, and ATL/BTL testing. |

## Work Cited

Altman, Erik, et al. “Realistic Synthetic Financial Transactions for Anti-Money Laundering Models.” *Advances in Neural Information Processing Systems*, vol. 36. [View the original paper](https://research.ibm.com/publications/realistic-synthetic-financial-transactions-for-anti-money-laundering-models).
