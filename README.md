# -improved-octo-spoon
Demonstrates capabilities to crearte a scalable pipeline with airflow and a mock Redshift

### Components
| **Component**        | **Technology**             |
|----------------------|----------------------------|
| Orchestration        | Apache Airflow (Dockerized)|
| Storage (Staging)    | MinIO (mock S3)            |
| Warehouse (Mock)     | PostgreSQL (mock Redshift) |
| Transformations      | Pandas or PySpark          |
| Data Validation      | Great Expectations         |
| CI/CD                | GitHub Actions             |
| Deployment           | Docker Compose             |

### Dataflow

<pre> ```mermaid graph TD; Source[Public API] --> Staging[MinIO - Raw CSV] Staging --> Airflow[Airflow DAG] Airflow --> Transform[PySpark Transform] Transform --> Validate[Great Expectations] Validate --> Warehouse[PostgreSQL (Mock Redshift)] ``` </pre>