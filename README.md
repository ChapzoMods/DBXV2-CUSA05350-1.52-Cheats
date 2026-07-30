# Dragon Ball Xenoverse 2 — CUSA05350 v1.52 GoldHEN Cheats

**Author:** ChapzoMods  
**GitHub:** [github.com/ChapzoMods](https://github.com/ChapzoMods)  
**Game:** Dragon Ball Xenoverse 2 (PS4)  
**Title ID:** CUSA05350  
**Version:** 01.52 (Future Saga Chapter 4 — latest)  

## Cheats Included (6 cheats, 12 patches)

| # | Cheat | Patches | Method |
|---|-------|---------|--------|
| 1 | Max/Infinite Health (Master Code) | 2 × NOP×9 | vmovss [r15+0xF0], xmm0 |
| 2 | Infinite Vigor (Stamina) | 1 × NOP×9 | vmovss [r15+0x15C], xmm0 |
| 3 | Infinite Ki | 4 × NOP×9 | vmovss [r15+0x7F0], xmm2 |
| 4 | Max Attribute Points | 3 × NOP×7 | mov [r15+0x200], ecx |
| 5 | Infinite TP Medals | 1 × NOP×4 | mov [r15+0x74], eax |
| 6 | Infinite Zeni (On Use) | 1 × cmp override | cmp ebx, 0x3B9ACA00 → 0x7FFFFFFF |

## Installation

1. Copy `cheats/CUSA05350_01.52.json` to your PS4:
   ```
   /data/GoldHEN/cheats/json/CUSA05350_01.52.json
   ```
   (via FTP at `ftp://PS4_IP:2121` or USB)

2. Open GoldHEN → Cheat Manager

3. Launch Dragon Ball Xenoverse 2

4. Open GoldHEN overlay (PS Button) → enable cheats

## Important — Format Fix

This JSON uses the **exact same format** as the official GoldHEN cheat files (verified against CUSA05350_01.34.json and CUSA05350_01.44.json from the GoldHEN repository). 

All offsets are **file offsets** (not virtual addresses), matching the convention used by all official GoldHEN cheat files.

## Testing Recommendations

- **Backup your save** with Apollo Save Tool before testing
- Test **one cheat at a time** in Training Mode (not online)
- Infinite Zeni is "On Use" — spend Zenni to trigger the max value
- Max Attribute Points: activate, spend 1 point, exit menu, re-enter

## Technical Details

- **EBOOT:** 42 MB ELF 64-bit, build "PS4 Ver.1.52.00 Build:May 24 2016"
- **Verification:** All offsets verified with capstone disassembly
- **No codecaves:** 100% direct NOP patches in .text section
- **All ON/OFF lengths match:** No instruction misalignment

## Credits

- **Ported & Verified by:** ChapzoMods ([github.com/ChapzoMods](https://github.com/ChapzoMods))
- **Original cheats (v1.50):** Celogamez (GoldHEN Cheat Repository)
- **Save format reversing:** Eternity, Falo, Zhaxxy, bucanero (Apollo)
- **Analysis tools:** capstone, pyelftools, angr
