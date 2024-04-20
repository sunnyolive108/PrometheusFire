# Prometheus' Fire
## ** or There is a need to value DATA

### Step 1: Download and Extract Prometheus
1. Download the latest version of Prometheus:
   ```bash
     wget https://github.com/prometheus/prometheus/releases/download/v2.34.0/prometheus-2.34.0.linux-amd64.tar.gz
  
2. Extract the downloaded file:
     ```bash
     tar xvfz prometheus-2.34.0.linux-amd64.tar.gz

### Step 2: Configure Prometheus
1. Navigate into the Prometheus directory:
    ```bash
    cd prometheus-2.34.0.linux-amd64

2. Open the Prometheus configuration file prometheus.yml using a text editor:
    ```bash
    vim prometheus.yml
3. Modify the prometheus.yml file to scrape metrics from your processing program
    ```yaml

      global:
        scrape_interval:     15s
        evaluation_interval: 15s

      scrape_configs:
        - job_name: 'data_processing_program'
          static_configs:
            - targets: ['localhost:9090']  # Address of your DATA processing program

4. Save and exit the text editor

### Step 3: Run Prometheus

- Run Prometheus using the following command:
    ```bash
    ./prometheus --config.file=prometheus.yml

- Prometheus will start and begin scraping metrics from the specified targets.

### Step 4: Access Prometheus UI

Open your web browser and navigate to 
   ```bash
      http://your_server_ip:9090.

Replace your_server_ip with the IP address of your Linux server.
You should see the Prometheus web UI.
