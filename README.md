# Network Traffic Analyzer

Advanced network traffic analysis tool for detecting advanced threats, data exfiltration, and command & control communication.

## Features
- **Zeek Log Analysis**: Parse and analyze Zeek (formerly Bro) logs
- **NetFlow Processing**: V5, V9, and IPFIX flow processing
- **Anomaly Detection**: Statistical and ML-based anomaly detection
- **C2 Detection**: Pattern matching for known C2 infrastructure
- **Data Exfiltration Detection**: Volume, protocol, and pattern-based detection
- **Protocol Analysis**: Deep inspection of DNS, HTTP, TLS, SSH, SMB, RDP
- **Visualization**: Interactive dashboards and timeline analysis

## Detection Patterns
- DNS exfiltration and tunneling
- HTTP/HTTPS command & control
- Unusual port combinations
- Protocol anomalies
- Bandwidth abuse
- Beaconing behavior
- Long connections (persistence indicators)

## Example Usage
```python
from network_analyzer import ZeekAnalyzer

analyzer = ZeekAnalyzer("zeek_logs/")
anomalies = analyzer.detect_c2()
exfiltration = analyzer.detect_exfiltration(threshold=1GB)
beacons = analyzer.detect_beaconing(interval_threshold=60)

analyzer.generate_report("threat_report.html")
```

## Performance
- Process 1M flow records: <30 seconds
- Real-time analysis support
- Distributed processing for large datasets

## Data Sources
- Zeek/Bro IDS logs
- Netflow/IPFIX collectors
- Suricata Eve logs
- CloudFlare network logs
- VPC flow logs (AWS, Azure, GCP)