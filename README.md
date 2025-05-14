# Absoluutne drooni positsioneerimine aerofotodelt  
**Magistritöö – Gregor Nepste, TÜ 2025**

Eksperimentaalne prototüüp, mis määrab droonifoto täpse asukoha. 
Lahendus põhineb EXIF‑metaandmetel, Maa‑ameti WMS‑ortofotodel, eeltreenitud sügavõppe­mudelitel (ResNet‑50, DINOv2) ning konvolutiivsel koosinussarnasusel.

---

## Toimimisloogika

1. Loeb EXIF‑i ning konverteerib metaandmete alus laisu ning kõrguskraadid L‑EST97 (EPSG:3301) koordinaatsüsteemiks;
2. Tõmbab 4× FOV bbox‑i Maa‑ameti WMS-ist;
3. Eraldab tunnuskaardid;
4. Libistab koosinussarnasust üle aluskaardi;
5. Trükib soojuskaardil tuvastatud punki nihked reaalsest asukohast & genereerimiskiirused ning joonistab drooni trajektoori.

---

## Eeldused

| Tarkvara | Versioon | Märkused                |
|----------|----------|-------------------------|
| Python   | ≥ 3.9    | testitud 3.11‑ga        |
| pip      | ≥ 22     | või conda/poetry        |
| ExifTool | 12+      | metaandmete lugemiseks  |
| CUDA     | vabatahtlik | kui soovid GPU‑d    |
| Git LFS  | soovitus | suurte fotode hoidmine  |

---

## Muud eeldused

-Huggingface konto, mille abil saab genereerida endale WALDO30 mudeli kasutamiseks tokeni.
  1. Mine seadedesse, then
  2. Kliki "Access Tokens" aknale. 
  3. Kliki "New token".
  4. Vali roll ja nimi enda tokenile
  5. VALMIS!

-**NB** Prototüübiga ei tule kaasa drooniortofotod ehk need peab kasutaja ise lahendusesse juurde lisama!!!

