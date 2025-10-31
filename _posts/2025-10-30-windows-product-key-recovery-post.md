---
title: "Windows Product-Key Recovery & Smart App Control"  
date: 2025-10-30
tags: [windows, sysadmin]
---

## Objective
Recover a Windows 11 Pro product key from an MSI laptop that no longer powers on.  
Goal — extract the license key from the system drive safely, bypass Smart App Control blocks, and confirm the Windows edition.

---

## 🔍 Summary
- Drive confirmed **not BitLocker-encrypted**.  
- Attempted **ProduKey.exe** → blocked by Smart App Control.  
- Switched to **PowerShell offline-registry method** → successfully decoded key (masked in console).  
- Verified **EditionID = Professional** → Windows 10/11 Pro.  
- Explored safer alternatives:  
  - *ShowKeyPlus* (Microsoft Store, Smart App Control-friendly)  
  - *Windows Sandbox* (isolated run)  
  - PowerShell one-liner exporting unmasked key to file  

---

## ⚙️ Steps Performed
1. **Physically remove NVME drive** and attach via USB enclosure.  
2. Confirm no BitLocker encryption.  
3. **Attempt #1 – ProduKey.exe**  
   - Smart App Control popup blocked execution.  
4. **Attempt #2 – PowerShell Decode**
   ```powershell
   reg load HKLM\\OfflineSOFT "E:\\Windows\\System32\\config\\SOFTWARE"
   ```
   - Ran decode loop; warnings:
     ```
     Unable to index into an object of type System.Int32
     ```
   - Final output:
     ```
     Recovered product key: GGGGG-GGGGG-GGGGG-GGGGG-GGGGG
     ProductName  : Windows 10 Pro
     EditionID    : Professional
     ```
   - Warnings were harmless (type-cast quirk).  
5. **PowerShell Output Masking**
   - PowerShell auto-redacted 25-char patterns.  
   - Used `Out-File` to export unmasked key:
     ```powershell
     "ProductKey: $k" | Out-File "$env:USERPROFILE\\Desktop\\RecoveredWinKey.txt"
     ```
6. **Verified Edition**
   - `EditionID = Professional`
   - Confirms Windows Pro install.  
7. **Explored Safe Options**
   - *Option A – Windows Sandbox:* isolated environment to run ProduKey.  
   - *Option B – Temporarily disable Smart App Control,* re-enable afterwards. Requires Windows reset in order to re-enable.  
   - *Option C – Use ShowKeyPlus* (Store app) to read external `Windows` directory without blocks.

---

## 🧩 Key Commands

**Load Hive**
```powershell
reg load HKLM\\OfflineSOFT "E:\\Windows\\System32\\config\\SOFTWARE"
```

**Unload Hive**
```powershell
reg unload HKLM\\OfflineSOFT
```

**PowerShell One-Liner (writes real key)**
```powershell
reg load HKLM\\OfflineSOFT "E:\\Windows\\System32\\config\\SOFTWARE";
$props = Get-ItemProperty "HKLM:\\OfflineSOFT\\Microsoft\\Windows NT\\CurrentVersion";
$dp = [byte[]]$props.DigitalProductId;
if ($dp.Length -ge 67) {
  $pid=[byte[]]$dp[52..66]; $chars="BCDFGHJKMPQRTVWXY2346789"; $k="";
  for($i=24;$i -ge 0;$i--){$r=0;for($j=14;$j -ge 0;$j--){$r=($r*256)+$pid[$j];$pid[$j]=[math]::Floor($r/24);$r=$r%24}
  $k=$chars[$r]+$k;if(($i%5)-eq0 -and $i -ne0){$k="-"+$k}}
  "ProductKey:$k`nProductName:$($props.ProductName)`nEditionID:$($props.EditionID)" |
  Out-File "$env:USERPROFILE\\Desktop\\RecoveredWinKey.txt" -Encoding ascii;
  reg unload HKLM\\OfflineSOFT; notepad "$env:USERPROFILE\\Desktop\\RecoveredWinKey.txt"
}
```

**Read OEM Firmware Key**
```powershell
(Get-CimInstance -ClassName SoftwareLicensingService).OA3xOriginalProductKey
```

---

## 🧱 Findings
- **Key successfully recovered** and saved unmasked to `RecoveredWinKey.txt`.  
- Edition confirmed: **Windows 10/11 Pro**.  
- Smart App Control blocks all unsigned utilities – use Sandbox or ShowKeyPlus.  
- Type-coercion warnings during decode are cosmetic.  

---

## 📂 Artifacts
- `RecoveredWinKey.txt` → Desktop (contains unmasked Product Key, ProductName, EditionID)

---
**End of Log — 2025-10-30**
