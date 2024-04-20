# Prometheus' Fire

### Step 1: Download and Extract Prometheus
Download the latest version of Prometheus:
  ´´bash
  wget https://github.com/prometheus/prometheus/releases/download/v2.34.0/prometheus-2.34.0.linux-amd64.tar.gz
Extract the downloaded file:
  ´´´bash
  tar xvfz prometheus-2.34.0.linux-amd64.tar.gz

### Step 2: Configure Prometheus
Navigate into the Prometheus directory:
  ´´´bash
  cd prometheus-2.34.0.linux-amd64
Open the Prometheus configuration file prometheus.yml using a text editor:
  ´´´bash
  nano prometheus.yml
Modify the prometheus.yml file to scrape metrics from your RabbitMQ processing program. Here's an example configuration to scrape metrics from localhost:9090 (replace localhost:9090 with the address of your RabbitMQ processing program):
  ´´´yaml

  global:
    scrape_interval:     15s
    evaluation_interval: 15s

  scrape_configs:
    - job_name: 'rabbitmq_processing_program'
      static_configs:
        - targets: ['localhost:9090']  # Address of your RabbitMQ processing program
Save and exit the text editor.
Step 3: Run Prometheus
Run Prometheus using the following command:
  ´´´bash
  ./prometheus --config.file=prometheus.yml
Prometheus will start and begin scraping metrics from the specified targets.
