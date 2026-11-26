# Troubleshooting-and-Helpdesk
# Q1. <p>Build a baseline report for a fictional Ahmedabad CA firm, 'Mehta & Rao Associates', by saving three read-only reports from your own PC into a folder named 'mehta_rao_diag': 'baseline_systeminfo.txt' from `systeminfo`, 'baseline_dxdiag.txt' from `dxdiag /t`, and 'baseline_msinfo.txt' exported from System Information. Hint: `dxdiag /t baseline_dxdiag.txt` writes the file in a few seconds. On Linux, save `lscpu`, `free -h` and `lsblk` into 'baseline_linux.txt' instead. Constraint: Replace your computer name, username and any serial number in the files with XXXX before submitting.</p>
Ans.> # Baseline System Diagnostic Report

**Organization:** Mehta & Rao Associates  
**Location:** Ahmedabad, Gujarat, India  
**Project:** Baseline System Diagnostics  
**Folder Name:** `mehta_rao_diag`

## Objective

To create a baseline diagnostic report for the system by collecting hardware, operating system, memory, storage, and DirectX information using built-in system diagnostic utilities.

## Reports Generated

The following read-only diagnostic reports are collected and stored in the `mehta_rao_diag` directory.

### Windows Reports

| File Name | Command / Utility | Description |
|---|---|---|
| `baseline_systeminfo.txt` | `systeminfo` | Operating system, system configuration, memory, and system details |
| `baseline_dxdiag.txt` | `dxdiag /t` | DirectX, graphics, display, and audio diagnostic information |
| `baseline_msinfo.txt` | System Information (`msinfo32`) | Detailed hardware resources, components, and software environment |

### Linux Alternative

For Linux systems, the following commands are used:

```bash
lscpu
free -h
lsblk
```

The output is saved in:

`baseline_linux.txt`

## Windows Execution

```cmd
mkdir mehta_rao_diag

systeminfo > mehta_rao_diag\baseline_systeminfo.txt

dxdiag /t mehta_rao_diag\baseline_dxdiag.txt

msinfo32 /report mehta_rao_diag\baseline_msinfo.txt
```

## Linux Execution

```bash
mkdir -p mehta_rao_diag

lscpu > mehta_rao_diag/baseline_linux.txt
free -h >> mehta_rao_diag/baseline_linux.txt
lsblk >> mehta_rao_diag/baseline_linux.txt
```

## Privacy and Data Sanitization

Before submitting the reports, the following sensitive information is replaced with `XXXX`:

- Computer name
- Username
- Hardware serial numbers

The reports are reviewed to ensure that personally identifiable or sensitive system information is not unintentionally disclosed.

## Expected Directory Structure

```text
mehta_rao_diag/
├── baseline_systeminfo.txt
├── baseline_dxdiag.txt
└── baseline_msinfo.txt
```

For Linux systems:

```text
mehta_rao_diag/
└── baseline_linux.txt
```

## Conclusion

The baseline diagnostic reports provide an initial overview of the system's hardware and software configuration. These reports can be used for documentation, troubleshooting, and future system comparison purposes.

All diagnostic commands are read-only and are intended for system information collection.
# Q2.<p>Capture the health of your own storage drive in 'storage_health.txt' inside 'mehta_rao_diag' using `Get-PhysicalDisk | Format-List FriendlyName,MediaType,HealthStatus,OperationalStatus`. On a laptop, also save `powercfg /batteryreport /output battery_report.html`. On Linux, use `lsblk -d -o NAME,TYPE,SIZE,ROTA`. Hint: Run PowerShell as Administrator for `powercfg`; on a desktop, write 'no battery' in the file. Constraint: Use read-only commands only; no repair, format or clean option.</p>
Ans.> # Storage Health Diagnostic Report

**Organization:** Mehta & Rao Associates  
**Location:** Ahmedabad, Gujarat, India  
**Project:** Storage and Battery Health Diagnostics  
**Directory:** `mehta_rao_diag`

## Objective

To capture the current storage drive health status and battery information, if available, using read-only system diagnostic commands.

## Storage Health Report

The storage health report is saved as:

`storage_health.txt`

### Windows PowerShell

Run PowerShell and execute the following commands:

```powershell
New-Item -ItemType Directory -Force -Path "mehta_rao_diag"

Get-PhysicalDisk |
Format-List FriendlyName,MediaType,HealthStatus,OperationalStatus |
Out-File "mehta_rao_diag\storage_health.txt"
```

The report contains:

- Drive name
- Media type
- Health status
- Operational status

## Battery Health Report

For laptop systems, generate a battery report using:

```powershell
powercfg /batteryreport /output "mehta_rao_diag\battery_report.html"
```

Run PowerShell as Administrator if required.

The generated report provides battery information such as installed battery details, design capacity, full charge capacity, and battery usage history.

For desktop systems without a battery, create the following file:

`battery_report.txt`

Contents:

```text
no battery
```

## Linux Alternative

For Linux systems, use the following read-only command:

```bash
lsblk -d -o NAME,TYPE,SIZE,ROTA
```

Save the output to:

```bash
lsblk -d -o NAME,TYPE,SIZE,ROTA > mehta_rao_diag/storage_health.txt
```

## Expected Directory Structure

```text
mehta_rao_diag/
├── baseline_systeminfo.txt
├── baseline_dxdiag.txt
├── baseline_msinfo.txt
├── storage_health.txt
├── battery_report.html
└── battery_report.txt
```

Note: Include `battery_report.html` for laptop systems and `battery_report.txt` containing `no battery` for desktop systems without a battery.

## Safety and Privacy

- Only read-only diagnostic commands are used.
- No repair, format, clean, or destructive operations are performed.
- Personal information and hardware serial numbers are reviewed and redacted before submission.

## Conclusion

The storage and battery diagnostic reports document the current storage device status and battery information, where applicable. These reports complement the baseline system diagnostic report and support future system health comparisons.
# Q3.<p>Capture your PC's last 7 days of Critical and Error events into 'recent_errors.txt' with `Get-WinEvent -FilterHashtable @{LogName='System';Level=1,2;StartTime=(Get-Date).AddDays(-7)} -MaxEvents 20`, and save one screenshot of Reliability Monitor (`perfmon /rel`) as 'reliability_monitor.png'. On Linux, use `journalctl -p err -b --no-pager | tail -n 20`. Hint: If no events match, PowerShell prints an error; keep the command and that message as your proof.</p>
Ans.> # Recent System Errors and Reliability Monitoring

**Organization:** Mehta & Rao Associates  
**Location:** Ahmedabad, Gujarat, India  
**Project:** System Error and Reliability Diagnostics  
**Directory:** `mehta_rao_diag`

## Objective

To capture recent Critical and Error-level system events from the last seven days and document system reliability using Windows Reliability Monitor.

## 1. Recent Error Events (Windows)

The following PowerShell command collects the last 20 Critical and Error events from the Windows System event log within the previous seven days.

```powershell
Get-WinEvent -FilterHashtable @{
    LogName='System'
    Level=1,2
    StartTime=(Get-Date).AddDays(-7)
} -MaxEvents 20 |
Out-File "mehta_rao_diag\recent_errors.txt"
```

**Output File:** `recent_errors.txt`

The report captures:
- Critical events
- Error-level events
- Event timestamps
- Event IDs
- Event descriptions

**Note:** If no matching events are found, PowerShell may display an error message. Preserve the original command and its error message in the report as evidence.

## 2. Reliability Monitor Screenshot

Open Windows Reliability Monitor using:

```cmd
perfmon /rel
```

Steps:
1. Open Reliability Monitor.
2. Review the system stability history.
3. Check critical events, application failures, and Windows failures.
4. Capture a screenshot of the Reliability Monitor window.
5. Save the screenshot as:

`mehta_rao_diag/reliability_monitor.png`

## 3. Linux Alternative

For Linux systems, use:

```bash
journalctl -p err -b --no-pager | tail -n 20
```

Save the output using:

```bash
journalctl -p err -b --no-pager | tail -n 20 > mehta_rao_diag/recent_errors.txt
```

This command captures the last 20 error-priority log entries from the current boot.

## 4. Expected Directory Structure

```text
mehta_rao_diag/
├── baseline_systeminfo.txt
├── baseline_dxdiag.txt
├── baseline_msinfo.txt
├── storage_health.txt
├── battery_report.html
├── recent_errors.txt
└── reliability_monitor.png
```

Include only the applicable battery report for your system.

## 5. Safety and Privacy

- Only read-only diagnostic commands are used.
- No system repair or modification is performed.
- No formatting or cleaning operations are performed.
- Personal information, usernames, computer names, and serial numbers are redacted before submission.

## Conclusion

The recent error logs and Reliability Monitor screenshot provide an overview of system stability and recent failures. These diagnostic records complement the baseline hardware, software, storage, and battery reports for Mehta & Rao Associates.

All collected information is intended for system health documentation and future troubleshooting reference.
# Q4.<p>Finish by building 'diagnostic_index.txt' in 'mehta_rao_diag' listing every file in the folder with the tool that produced it, then one line each for CPU, RAM, storage, display and events marked OK or CHECK with a quoted line from your files as evidence. Add the line 'PSU voltage: LAB ONLY - multimeter, not tested at home'. Zip the folder as 'mehta_rao_diag.zip' and submit it. Constraint: Do not open any hardware or buy any tool for this task.</p>
Ans.> 
