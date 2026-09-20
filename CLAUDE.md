# Final Call

Final Call je mobilní hra pro jednu ruku: hráč jde k odletové bráně na letišti a cedule mu čím dál přesněji říkají, kde brána je, zatímco se musí rozhodnout, kdy tomu zúžení uvěřit a vsadit.

Kompletní herní design je v projektovém dokumentu (Final Call — zadání pro Cowork). Tohle CLAUDE.md popisuje jen technické konvence pro kód, ne herní pravidla.

## Konvence pro vývoj

- **Jeden soubor.** Celá hra je `index.html` — čisté HTML + CSS + JS v jednom souboru. Žádný build krok, žádné závislosti, žádný framework, žádný bundler. Otevře se přímo v prohlížeči a běží.
- **Jeden objekt s laditelnými čísly.** Všechny konstanty, které ovlivňují pocit ze hry (počet úseků, tempo zužování, rozsahy skoků, ceny, výplaty...), žijí v jednom objektu `BALANC` na začátku `<script>`. Nikdy je nerozsypat po kódu — ladění se dělá na telefonu úpravou tohoto jednoho místa.
- **Typografie místo grafiky.** Monospace čísla, šipky, cedule a hlášení jako text. Estetika letištního informačního systému (splitflap tabule). Žádné obrázky, žádné externí assety, žádné webfonty vyžadující síť.
- **Mobil na výšku, jeden palec.** Hra musí běžet v Chrome na Androidu (testováno na Motorola Edge 20), na výšku, ovladatelná jedním palcem. Ovládací prvky patří dolů na obrazovku, do dosahu palce. Zoom gestem je vypnutý (`viewport` meta + `touch-action`), ať se to nechová jako webová stránka.
- **Komentáře česky.** Veškeré komentáře v kódu jsou v češtině, protože se v kódu bude drobně upravovat přímo z mobilního editoru.
- **Commit po každém funkčním celku.** Každý krok, který jde otevřít a osahat, je samostatný commit. Po každém push na `main` se rovnou promítne na GitHub Pages.
