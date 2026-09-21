# PITAP: Payment Intelligence & Decisioning Platform
An enterprise-grade, high-throughput payment failure triage and decisioning platform processing 10,000+ daily transactions across multiple payment gateways (Razorpay, PayU, Stripe).

## Key Production Metrics
- **Throughput:** 10,000+ transactions/day across 3 primary payment gateways.
- **Straight-Through Processing (STP):** Achieved an **81% STP rate** through automated ML classification.
- **Latency SLA:** P95 sub-second API response time (**$267\text{ms}$**).
- **Business Impact:** Prevented over **$\$1.2\text{M}+$** in annualized transaction drop-offs and routing failures.

## System Architecture Flow
[3 Gateways: Razorpay, PayU, Stripe] 
       │
       ▼
[PySpark Ingestion Engine] ──► [Delta Lake: Bronze / Silver / Gold Layers]
                                           │
                                           ▼
[SQL Root-Cause & Chi-Square Analysis] ──► [ML Classifier Pipeline (Scikit-Learn/Random Forest)]
                                           │
                                           ▼
[FastAPI REST Microservice] ─────────────► [Enterprise Systems / Alerting (CloudWatch/Grafana)]
