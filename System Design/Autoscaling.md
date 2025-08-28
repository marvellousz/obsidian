### How Autoscaling Works?

- Triggers:
	- CPU usage
	- Memory
	- Request Rate
	- Queue length
- Types:
	- Horizontal Scaling: Add/remove instances
	- Vertical Scaling: Resize a single instance
- Scaling Policies:
	- Reactive (based on thresholds)
	- Predictive (based on trends)
### Autoscaling Across Cloud Providers

- All major cloud providers support built in autoscaling across compute and container services
	- AWS
	- Azure
	- GCP
### Monitoring & Proactive Scaling

- Use metrics like
	- CPU, Memory, Network
	- Queue depth, Custom KPIs
- Proactive Scaling
	- Predictive algorithms (based on ML or trends)
	- Scheduled scaling (known traffic patterns)
- Tools: CloudWatch, Prometheus + Grafana, Azure Monitor, GCP Operations
### Cost Optimization Strategies

- Avoid over-provisioning - scale just enough
- Use spot/preemptible instances for batch workloads
- Apply resource limits & quotas
- Rightsize regularly on actual usage
- Use auto-pausing or scale to zero features for idle services