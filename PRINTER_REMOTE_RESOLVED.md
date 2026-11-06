# Incident Report: INC909428 — Printer keeps asking for paper that is already in the tray[cite: 4]

## 1. Ticket Metadata
* **Ticket ID:** INC909428[cite: 4]
* **Priority:** Medium[cite: 4]
* **Status:** Solution Complete[cite: 4]
* **Assignee:** Priyanshu Thakur[cite: 4]
* **Reported By:** Kevin Zhang (`kzhang@servicedesk-simulator.com`)[cite: 4]
* **Department & Location:** Engineering | Floor 3 | Contact: x6210[cite: 4]
* **Affected Device:** `Floor3-Printer-C` (Office laser printer — IP: `10.0.2.52`)[cite: 4]

## 2. Issue Description
Whenever anyone on Floor 3 sent a print job, `Floor3-Printer-C` halted and prompted users on its display screen to load paper, even though the main tray was completely full of plain paper[cite: 4]. Holding down the physical button on the front of the printer forced the job to print from the small top bypass tray (`Tray 1`), which contained `A4` headed paper reserved for official letters rather than standard plain paper[cite: 4].

## 3. Preliminary Troubleshooting by User
* Verified the main paper tray was full of plain paper[cite: 4].
* Removed the paper stack, squared it up, and reloaded it twice with no change[cite: 4].
* Tested printing from three different computers across the team[cite: 4].

## 4. Business Impact
No one on Floor 3 could print on plain paper, causing all standard print jobs to halt and queue at the device[cite: 4].

## 5. Investigation & Resolution
1. Initiated a remote desktop session (`SD1022`) to Kevin Zhang's workstation[cite: 4].
2. Opened the web browser and connected to the printer's web management interface at `10.0.2.52` (`Floor3-Printer-C`)[cite: 4].
3. Inspected the **TRAYS** configuration tab, which showed `Arriving jobs are asking for: Letter`[cite: 4].
4. Identified a tray configuration mismatch and verified the tray settings[cite: 4]:
   * **Tray 1 (bypass):** Paper Size `A4` | Paper Type `Letterhead` | Capacity `100 sheets`[cite: 4]
   * **Tray 2:** Updated Paper Size to `Letter` | Paper Type `Plain` | Capacity `500 sheets`[cite: 4]
5. Clicked **APPLY CHANGES** and confirmed `Settings applied.` to resume normal plain-paper printing from Tray 2[cite: 4].

## 6. Resolution Screenshot
![Printer Remote Repair](PRINTER_REMOTE%20REPAIR.png)
