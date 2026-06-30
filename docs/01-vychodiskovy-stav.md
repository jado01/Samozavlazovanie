# Východiskový stav

Aktualizované: 2026-06-30

## Balkón

- približné rozmery: 1 × 3,5 m,
- orientácia: juh,
- zasklenie: štyri časti; krajné sú bežne zafixované, používajú sa dve stredné,
- dostupná elektrická zásuvka,
- Wi-Fi je dostupné v susednej izbe; pokrytie balkóna sa ešte zmeria,
- káblové pripojenie je možné,
- predbežné miesto nádrže: pravý roh pod jahodami,
- v blízkosti plánovanej nádrže je zásuvka 230 V bez deklarovaného IP krytia,
- Home Assistant beží na Raspberry Pi 5,
- ďalší Linux server beží na Raspberry Pi 3.

### Home Assistant – overený systémový stav

Stav overený cez **System information** dňa 2026-06-30:

- inštalácia: Home Assistant OS,
- Home Assistant Core: 2026.6.4,
- Home Assistant OS: 18.0,
- Supervisor: 2026.06.2,
- architektúra: aarch64,
- doska: Raspberry Pi 5 (`rpi5-64`),
- úložisko: NVMe 468,7 GB; systém z neho priamo bootuje,
- stav systému: `Healthy: true`, `Supported: true`,
- časové pásmo: Europe/Bratislava,
- Zigbee koordinátor: Home Assistant Connect ZBT-1,
- Zigbee vrstva: Zigbee2MQTT 2.12.0-1 a Mosquitto broker 7.1.0,
- vzdialený prístup: Tailscale,
- zálohovanie: Home Assistant Google Drive Backup,
- ďalšie relevantné aplikácie: Terminal & SSH, Get HACS a Node-RED,
- ESPHome Device Builder zatiaľ nie je nainštalovaný.

Južná orientácia a zasklenie znamenajú riziko vysokej teploty a rýchlo sa meniacej spotreby vody. Teplota balkóna preto bude jedným zo sledovaných údajov.

## Rastliny

- 2 malé črepníky s cherry paradajkami,
- 10 jahôd v dvoch zvislých textilných kvetináčoch,
- jahody sú v piatich spodných vreckách každého kvetináča,
- horné vrecká pri preliatí prepúšťajú vodu nižšie,
- cez najnižšie vrecká voda ďalej nepretečie,
- jahody sú na západnej stene balkóna.

Zalievanie iba zhora by bolo ťažko kontrolovateľné: horné rastliny by mohli byť preliate a spodné nedostatočne zavlažené. Predbežne sa preto počíta so samostatným vývodom ku každému obsadenému vrecku. Prietoky sa doladia meraním.

## Požadovaná autonómia

- prvá funkčná verzia (MVP): funkčný systém aj s autonómiou iba 1 až 3 dni,
- neskoršie minimum: 8 dní,
- neskorší cieľ: 12 až 14 dní.

Dĺžka autonómie neovplyvňuje základnú logiku systému, ale priamo ovplyvní objem nádrže. Nádrž sa nebude dimenzovať odhadom; určí sa z reálnej dennej spotreby v horúcom dni a bezpečnostnej rezervy.

Predbežný výpočet:

`objem nádrže = najvyššia nameraná denná spotreba × počet dní × rezerva`

Ako počiatočná rezerva sa použije 25 až 40 %. K výsledku sa pripočíta nepoužiteľný zvyšok pod minimálnou hladinou čerpadla.

Používateľ pri ručnom polievaní počas veľkých horúčav minul približne 3 l vody denne pri dvoch zálievkach. Ide o spomienkový údaj, ktorý sa neskôr overí meraním.

Prvý prototyp použije dostupnú nádobu s objemom približne 4 až 5 l alebo malú štvorcovú 15 l nádobu. Veľkosť dovolenkovej nádrže sa začne riešiť až po sprevádzkovaní a kalibrácii systému.

## Odtok a rozpočet

- podlaha balkóna má podľa používateľa spád,
- pod zasklením sú v spodných rohoch medzery umožňujúce odtok vody,
- funkcia odtoku a smer odtekajúcej vody sa po návrate overia skúškou malým objemom,
- odtok sa nepovažuje za jedinú ochranu pred poruchou nádrže alebo hadice,
- rozpočet nemá pevný limit; prioritou je rozumný pomer ceny, kvality a spoľahlivosti.

## Fotodokumentácia

Prijaté boli fotografie:

- `PXL_20260620_144653523.jpg` – dva textilné vertikálne kvetináče s jahodami,
- `PXL_20260614_084943246.jpg` – čelný pohľad na štvordielne zasklenie balkóna.

Originály boli skopírované do `assets/photos/original/` a sú zámerne ignorované Gitom. Kontrola 2026-06-30 potvrdila, že oba súbory obsahujú EXIF aj GPS údaje, preto sa nesmú priamo publikovať. Po návrate sa doplní kompletná fotografická séria podľa kontrolného zoznamu. Vybrané zábery sa pred zverejnením očistia a uložia do `docs/images/`.
