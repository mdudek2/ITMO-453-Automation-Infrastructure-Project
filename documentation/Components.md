## Automated Deployment

Automated deployment is achieved through a combination of bash scripts and ansible playbooks. The bash scripts are used to control the deployment process and execute the ansbile playbooks when necessary. The system is able to deploy with only minimal human intervention. 

### Configuration Management

Each server is configured automatically via ansible. No manual configuration is necessary to setup any service that is running as a part of this deployment.

### Service Deployment

This system deploys webservers hosted on nginx as well as a single prometheus instance that is used to provide real time monitoring for those servers. The webservers also run the nginx and node exporter services to allow monitoring.

### Security Baseline Application

All systems that are depoloyed as part of this project have undergone scanning and compliance checks using the openscap-scanner. Remediations scripts were generated so that the systems are up to the standards of a CIS level 1 server.

### Logging Setup

An ansible playbook which gathers logs was created as part of this project. This playbook aggregates and then exports logs from each server in the
inventory to the ansible host. This approach was chosen because it allows an administrator to view logs from any system at will.

### Monitoring Integration

A prometheus server is included as part of the infrastructure in this project. It is configured to monitor each webserver via nginx-exporter and node-exporter. Prometheus provides a web interface that can be used for real time monitoring and collection of metrics.