# 📊 GitOps Observability Stack (ArgoCD + Prometheus + Grafana)

[![ArgoCD](https://img.shields.io/badge/ArgoCD-GitOps-EF7B4D.svg?logo=argo&logoColor=white)](https://argo-cd.readthedocs.io/)
[![Prometheus](https://img.shields.io/badge/Prometheus-Operator-E6522C.svg?logo=prometheus&logoColor=white)](https://prometheus.io/)
[![Grafana](https://img.shields.io/badge/Grafana-Dashboards_as_Code-F46800.svg?logo=grafana&logoColor=white)](https://grafana.com/)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-1.28+-326CE5.svg?logo=kubernetes&logoColor=white)](https://kubernetes.io/)

Production-grade, end-to-end Kubernetes monitoring and SRE alerting platform deployed declaratively using the **ArgoCD App-of-Apps** pattern.

---

## 🏛️ Stack Architecture

```
                  [ GitOps Repository ]
                           │
                           ▼
                  [ ArgoCD Controller ]
                           │
         ┌─────────────────┼─────────────────┐
         ▼                 ▼                 ▼
 [ Prometheus Operator ] [ Grafana HA ] [ Alertmanager ]
 (Metrics Scraping &      (Dashboards   (Slack/PagerDuty
  PromQL SLO Rules)        as Code)      Alert Routing)
         ▲
         └── [ ServiceMonitors (Auto-Discovery) ]
```

---

## ⚡ Core Enterprise Features
- **Declarative GitOps Management:** 100% managed by ArgoCD with automated self-healing and drift detection.
- **SLO & SRE Alerting Rules:** PromQL alerts monitoring P99 latency breaches, pod crash loops, error budget burn rates, and node disk pressure.
- **Dashboards as Code:** Pre-packaged Grafana dashboards for cluster capacity, pod health, and ingress traffic.
- **High-Availability Architecture:** 2x replicated Prometheus and Alertmanager with anti-affinity across availability zones.
