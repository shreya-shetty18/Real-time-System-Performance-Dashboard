# ⚙️ Real-time System Performance Dashboard using Power BI

This project provides a real-time system performance monitoring solution using Python, SQL Server, and Power BI. It continuously collects system-level metrics like CPU usage, memory stats, network I/O, and disk usage, logs them into a SQL Server database, and visualizes them using an interactive Power BI dashboard.

---

## 🚀 Project Objective

To build an automated pipeline that:
- Monitors key system performance metrics in real time.
- Stores these metrics in a structured SQL Server database.
- Enables users to analyze trends, detect anomalies, and visualize live stats using Power BI.

---

## 📊 Key Insights from the Dashboard

Here are insights observed over a multi-hour monitoring session:

### 🔹 CPU & Memory
- **Short CPU spikes every ~10 seconds** suggested background services or scheduled OS tasks (like antivirus scans or telemetry).
- **Sustained high memory usage (~70-80%)** during large file operations (e.g., browser + IDE + video editing).
- **Memory usage remained consistently high even after closing apps**, revealing **memory fragmentation** or slow release by certain processes.

### 🔹 Network Traffic
- **Gradual increase in `bytes_sent` and `bytes_received`** tied to video streaming and cloud syncing (e.g., OneDrive, Google Drive).
- **Sudden spikes in outbound traffic** were linked to system updates or third-party backup tools.
- Insight: Background services can heavily consume bandwidth without active user engagement.

### 🔹 Disk Usage
- **High disk write activity** correlated with temporary system files being created during application updates.
- **Disk free space declined rapidly during large downloads**, which was flagged using conditional formatting in Power BI.

### 🔹 Interrupts and Context Switches
- An **abnormal surge in `cpu_interrupts` and `cpu_calls`** was observed during system idle state — often a signal of device driver issues or high DPC activity.
- Insight: These metrics, though low-level, are useful in diagnosing performance bottlenecks at the OS/hardware interface.

### 📌 Summary Observations:
| Component    | Normal Behavior            | Anomalies / Alerts                     |
|--------------|-----------------------------|----------------------------------------|
| CPU          | < 40% on idle               | Frequent short spikes to 80%           |
| Memory       | ~60% average usage          | Retained >75% after app closure        |
| Network      | Flat during idle            | Random spikes from background uploads  |
| Disk         | Stable                      | Sudden drop in free space from update  |
| Interrupts   | Low baseline                | Spikes during system inactivity        |

---

## 🧰 Tech Stack

| Component      | Tool/Library              |
|----------------|---------------------------|
| Data Collection| Python, `psutil`, `pyodbc` |
| Data Storage   | Microsoft SQL Server       |
| Visualization  | Microsoft Power BI         |

---

## 💡 Use Cases
📊 Local system performance monitoring

🧪 Hardware testing or benchmark tracking

🔐 Detect suspicious network or disk activity

📉 IT team resource utilization reporting

⚠️ Early anomaly detection before failure



