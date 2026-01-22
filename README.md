# Sigma Detection Rules Collection


A collection of Sigma detection rules for Windows security monitoring, focusing on common attack techniques and anomaly detection.

## 📋 About

This repository contains custom Sigma detection rules designed to detect various security threats and anomalous activities in Windows environments. These rules follow the [Sigma specification](https://github.com/SigmaHQ/sigma) and can be converted to various SIEM query languages.

## 🎯 Purpose

- **Learning Resource**: Practical examples of Sigma rule creation
- **Threat Detection**: Ready-to-use detection logic for common attacks
- **SOC Enablement**: Help Security Operations Centers detect malicious activities
- **Blue Team Tooling**: Defensive security automation and monitoring

## 🗂️ Rule Categories

### Process Creation & Execution
- Detection of suspicious process spawn patterns
- Office application abuse detection
- Script-based attack chains
- Living-off-the-land binary (LOLBin) misuse

### Persistence Mechanisms
- Scheduled task creation anomalies
- Windows service creation monitoring
- Common persistence techniques used by malware

### Authentication & Access
- Brute force attack detection
- Suspicious authentication patterns
- Account manipulation attempts

## 🛠️ Usage

### Prerequisites
- Sigma CLI (`sigmac`) for rule conversion
- Target SIEM platform (Splunk, Elastic, QRadar, etc.)
- Windows Event Logging or Sysmon configured

### Converting Rules
```bash
# Convert to Splunk SPL
sigmac -t splunk rules/windows/process_creation/office_suspicious_files.yml

# Convert to Elasticsearch Query DSL
sigmac -t es-qs rules/windows/persistence/scheduled_task_creation.yml

# Convert to all supported targets
sigmac -t list  # List all available targets
