# 📊 generate_report

PowerShell toolkit that automates the creation of JSON / CSV datasets, interactive HTML dashboards, performance benchmarks, and webhook tests—perfect for scheduled system-metric reporting or ad-hoc health checks.

---

## ✨ Features
- Multi-format report output (JSON, CSV, HTML)
- Performance benchmarking scripts
- Webhook payload tests
- Pester-based validation
- One-shot installer / uninstaller

---

## 🚀 Requirements
| Component            | Version / Notes                          |
|----------------------|------------------------------------------|
| **PowerShell**       | 7.x (Core)                               |
| **Modules**          | `PSHTML`, `Pester`                       |
| **.NET Framework**   | 4.7.2+ (for some PerfMon counters)       |
| **Network**          | Outbound access to your webhook targets  |

---

## ⚡ Quick Start

```powershell
# 1) Unzip & install
Expand-Archive generate_report.zip -DestinationPath C:\generate_report
cd C:\generate_report
.\install.ps1

# 2) Run a full report
.\generate_reportv9.ps1 -OutputPath "C:\Reports" -Verbose

# 3) Build an interactive HTML dashboard
.\generate_report_html.ps1 `
  -InputPath  "C:\Reports\report.json" `
  -OutputPath "C:\Reports\dashboard.html"

🔑 Key Scripts
Script / File	Purpose
generate_reportv9.ps1	Latest consolidated report generator
generate_reportv8.ps1-v5	Earlier versions (kept for reference)
generate_report_html.ps1	Converts JSON/CSV output to an HTML dashboard (via PSHTML)
performance.ps1	Local benchmark tests (CPU / I/O / latency)
performance(perfmon).ps1	PerfMon-based system metrics collection
test_webhook.ps1 / .bat	Sends sample payloads to validate webhook endpoints
install.ps1 / install.cmd	One-click dependency bootstrap
uninstall.ps1	Clean uninstall of modules and artifacts
test_reports.ps1	Pester tests to validate report content

🛠️ Parameters (main generator)
Parameter	Type	Required	Description
-OutputPath	Path	Yes	Destination directory for generated files
-Scope	Text	No	Custom data-collection scope
-Verbose	Switch	No	Streams detailed progress messages

📌 Usage Examples
powershell
# Generate everything (JSON, CSV) into default folder
.\generate_reportv9.ps1 -OutputPath "C:\Reports"

# Same run, but with verbose logging
.\generate_reportv9.ps1 -OutputPath "C:\Reports" -Verbose

# Performance test, 10 iterations, log to file
.\performance.ps1 -Iterations 10 -LogFile "C:\Reports\perf.log"

# Quick webhook sanity check
.\test_webhook.ps1 -Url "https://hooks.example.com/endpoint"

🧪 Testing
powershell
# Validate report JSON vs schema & CSV row counts
.\test_reports.ps1

🔄 Uninstallation
powershell
cd C:\generate_report
.\uninstall.ps1

🪪 License
MIT License

👤 Author
Franco • franco@generaltechnical.com.au
