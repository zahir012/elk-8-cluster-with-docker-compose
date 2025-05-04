# ELK Stack Setup using Docker Compose

This repository provides a Docker Compose setup for running the ELK stack (Elasticsearch, Logstash, and Kibana) for local development and testing purposes.

## 🧱 Stack Components

- **Elasticsearch** – Distributed search and analytics engine.
- **Logstash** – Data processing pipeline that ingests data from multiple sources.
- **Kibana** – Visualization tool for Elasticsearch data.
- **Filebeat (optional)** – Lightweight shipper for forwarding and centralizing log data.

## 📁 Directory Structure

elk-stack/
├── docker-compose.yml
├── logstash/
│ └── logstash.conf
├── filebeat/ (optional)
│ └── filebeat.yml
└── README.md


## 🚀 Getting Started

### Prerequisites

- Docker
- Docker Compose

### Clone the Repository

```bash
git clone https://github.com/your-username/elk-stack.git
cd elk-stack

Start the Stack

docker-compose up -d

    Note: It may take a few moments for all services to become available.

Access Kibana

    URL: http://localhost:5601

⚙️ Configuration Details
Elasticsearch

    Runs on port 9200 (HTTP) and 9300 (transport).

    Environment variables like discovery.type=single-node set for development mode.

Logstash

    Configuration is defined in logstash/logstash.conf.

    Listens on port 5044 for input (e.g., Filebeat).

Kibana

    Accessible via port 5601.

    Default configuration is used with Elasticsearch set as the backend.

Filebeat (Optional)

To enable Filebeat for log shipping, include the Filebeat container in your docker-compose.yml and configure filebeat/filebeat.yml.
🛠 Customization

    Modify logstash/logstash.conf to change how logs are parsed and indexed.

    Add pipelines, filters, or custom grok patterns as needed.

    Secure the stack with credentials and TLS for production use.

📦 Stopping and Cleaning Up

docker-compose down -v

This stops all containers and removes volumes to clean up data.
🧪 Testing

You can use curl or any client to post logs to Logstash input or test Kibana dashboards.
🔐 Security (Production Considerations)

This setup is for local/dev use only. For production:

    Enable authentication and TLS for all services.

    Use persistent volumes for data.

    Limit container resource usage.

    Monitor and alert using Prometheus, Elasticsearch X-Pack, etc.

📚 References

    Elasticsearch Documentation

    Logstash Documentation

    Kibana Documentation

👨‍💻 Author

    Md. Zahirul Islam

    DevOps Engineer | Cloud | Kubernetes | Monitoring
