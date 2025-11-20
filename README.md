## 🏗️ Kiến trúc Hệ thống (Architecture)

```mermaid
graph LR
    Mongo[(MongoDB)] -->|Python Script| GCS[Google Cloud Storage]
    GCS -->|Python Script| BQ[(BigQuery Raw)]
    BQ -->|dbt| Staging[Staging Views]
    Staging -->|dbt| Marts[Star Schema Marts]
    Marts -->|One Big Table| Looker[Looker Studio Dashboard]
