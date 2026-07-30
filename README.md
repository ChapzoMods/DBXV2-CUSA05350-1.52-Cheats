# Dragon Ball Xenoverse 2 — CUSA05350 v1.52 GoldHEN Cheats

**Author:** ChapzoMods  
**GitHub:** [github.com/ChapzoMods](https://github.com/ChapzoMods)  
**Game:** Dragon Ball Xenoverse 2 (PS4)  
**Title ID:** CUSA05350  
**Version:** 01.52 (Future Saga Chapter 4 — latest)  

## Cheats Included (6 working + 1 deprecated)

| # | Cheat | Method | Patches |
|---|-------|--------|---------|
| 1 | Infinite Health | NOP × 9 (2 patches) | vmovss [r15+0xF0], xmm0 |
| 2 | Infinite Vigor (Stamina) | NOP × 9 (1 patch) | vmovss [r15+0x15C], xmm0 |
| 3 | Infinite Ki | NOP × 9 (4 patches) | vmovss [r15+0x7F0], xmm2 |
| 4 | Max Attribute Points | NOP × 7 (3 patches) | mov [r15+0x200], ecx |
| 5 | Infinite TP Medals | NOP × 4 (1 patch) | mov [r15+0x74], eax |
| 6 | Infinite Zeni | cmp override (1 patch) | cmp ebx, 0x3B9ACA00 → 0x7FFFFFFF |

## Important Fix (v1.52 vs v1.50)

Previous v1.50 cheats caused **CE-34878-0 crashes** in v1.52 due to:

1. **Off-by-0x4000 bug**: GoldHEN expects **virtual addresses**, not file offsets. The v1.52 EBOOT has `p_offset=0x4000` / `p_vaddr=0x0`, so `vaddr = file_offset - 0x4000`. All offsets in this JSON have been corrected.

2. **Codecaves over live strings**: The v1.50 codecave addresses (0x1CC7xxx) now point to live game strings in v1.52. All codecaves have been removed — only direct NOP patches are used.

3. **Multi-branch coverage**: Some cheats (Inf Health, Inf Ki, Max Attr) now patch ALL branches/instances of the target instruction, not just one.

## Installation

1. Copy `cheats/CUSA05350_01.52.json` to your PS4:
   ```
   /data/GoldHEN/cheats/json/CUSA05350_01.52.json
   ```
   (via FTP at `ftp://PS4_IP:2121` or USB)

2. Open GoldHEN → Cheat Manager

3. Launch Dragon Ball Xenoverse 2

4. Open GoldHEN overlay (PS Button) → enable cheats

## Testing Recommendations

- **Backup your save** with Apollo Save Tool before testing
- Test **one cheat at a time** in Training Mode (not online)
- If a cheat doesn't work, disable it and try the next one
- Infinite Zeni is "On Use" — spend Zenni to trigger the max value

## Technical Details

- **EBOOT:** 42 MB ELF 64-bit, build "PS4 Ver.1.52.00 Build:May 24 2016"
- **Verification:** All offsets verified with capstone disassembly + pyelftools ELF parsing
- **No codecaves:** 100% direct NOP patches in .text section
- **All ON/OFF lengths match:** No instruction misalignment

## Credits

- **Ported & Verified by:** ChapzoMods ([github.com/ChapzoMods](https://github.com/ChapzoMods))
- **Original cheats (v1.50):** Celogamez (GoldHEN Cheat Repository)
- **Save format reversing:** Eternity, Falo, Zhaxxy, bucanero (Apollo)
- **Analysis tools:** capstone, pyelftools, angr
