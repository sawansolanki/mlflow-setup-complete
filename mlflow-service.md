##To run mlflow service in production we need to create systemd service file in "/etc/systemd/system" with <serivce_name>.service (eg. - model.service)

[Unit]
Description=MLflow-tracking-server
After=network.target

[Service]
Type=simple
Restart=on-failure
RestartSec=30
User=azureuser  # Replace with the appropriate user
WorkingDirectory=/home/azureuser
ExecStart=/bin/bash -c 'mlflow server --host 0.0.0.0 --port 8080 --backend-store-uri mysql+pymysql://mlflow_user:mlflow@localhost/db_mlflow --default-artifact-root s3://first-bucket-sa2'

[Install]
WantedBy=basic.target


###sudo systemctl daemon-reload 

###sudo systemctl enable {service-name}

###sudo systemctl start {service-name}

###sudo systemctl status {service-name}


