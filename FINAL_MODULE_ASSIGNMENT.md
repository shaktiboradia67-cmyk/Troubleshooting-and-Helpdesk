# Final Module Assignment — Troubleshooting and Helpdesk

**Student repository owner:** shaktiboradia67-cmyk  
**Project:** Troubleshooting and Helpdesk — Integrated Module Portfolio  
**Date:** 27 November 2026

## Portfolio overview

This final module index brings together the five topic repositories submitted for the Troubleshooting and Helpdesk module. Each repository contains the topic work and its README.

## Topic repositories

1. **Module 1 — Mehta & Rao Associates: Baseline Diagnostics**  
   [Open repository](https://github.com/shaktiboradia67-cmyk/Troubleshooting-and-Helpdesk/blob/bd7f7e58d706f9ce8a51d0b696c9f77bf883dc5f/README.md)  
   Covers baseline system information, storage and battery health, recent Windows errors, Reliability Monitor, and a diagnostic index. The README records missing diagnostic evidence as CHECK rather than inventing results.

2. **Module 2 — Sanjeevani Medico: Performance and PSU Checks**  
   [Open repository](https://github.com/shaktiboradia67-cmyk/Troubleshooting-and-Helpdesk-2/blob/eb2a7c2df3c0a8b50e85ab97240b26d353931210/README.md)  
   Covers idle/load performance logging, PSU rail tolerance calculations, a 30-day hardware event hunt, and a fault register. Supplied voltage readings produced three PASS and three FAIL results. The event summary contains Kernel-Power entries but no Event ID 41 in the supplied output.

3. **Module 3 — Gyan Setu Classes: BIOS, POST and Boot Chain**  
   [Open repository](https://github.com/shaktiboradia67-cmyk/Troubleshooting-and-Helpdesk-3/blob/4407172c55f03181521be4f86697424e04af3c55/README.md)  
   Covers a Dell Latitude 5310 BIOS/UEFI snapshot, POST-code reference, non-destructive support tickets, and read-only boot-chain proof. Recorded firmware details include BIOS version 1.24.0, UEFI mode, and Secure Boot Off.

4. **Module 4 — Rangoli Textiles: RAM, Storage and Display Diagnostics**  
   [Open repository](https://github.com/shaktiboradia67-cmyk/Troubleshooting-and-Helpdesk-4/blob/e6f72b89e6357cb05d1a047065c503db278f5fbc/README.md)  
   Covers Windows Memory Diagnostic, read-only disk checking, display-event review, and service ticket RT-2026-014. The memory test was canceled, disk access was denied, and the dxdiag report was not found; these are recorded as WARN/unverified, not as confirmed hardware failures.

5. **Module 5 — NightOwl Connect: Ticketing, SLA and Shift Handover**  
   [Open repository](https://github.com/shaktiboradia67-cmyk/Troubleshooting-and-Helpdesk-5/blob/862b3d8c480b0bd038d63576a72185373475b564/README.md)  
   Covers the six-ticket workbook, SLA priorities, NO-102 restart evidence, formula-based Summary, unresolved-ticket handover, and final archive. The README currently contains placeholders for the two open-ticket handover rows. The final Summary and handover archive must be checked against the saved workbook before this module can be marked complete.

## Safety and evidence standards

- Diagnostic commands are read-only unless the task explicitly specifies otherwise.
- No event logs were cleared.
- No live power supply was opened and no home multimeter testing was performed.
- No BIOS boot, password, Secure Boot, or SATA settings were changed.
- No disk repair flags (/f or /r) were used.
- No graphics driver was updated, rolled back, or uninstalled.
- Missing or inconclusive evidence is identified honestly; no readings or test outcomes are fabricated.

## Overall status

The five topic repositories are linked here as the integrated module portfolio. Modules 1–4 document their available evidence and limitations. Module 5's final handover still requires its two unresolved ticket rows, exact SLA_Due values, Summary verification (6 tickets and 2 breaches), and the nightowl_s5.zip archive to be confirmed from the workbook.

**Submission note:** This page is the central index for the five topic repositories. It does not claim that the outstanding Module 5 handover/archive has been completed.
