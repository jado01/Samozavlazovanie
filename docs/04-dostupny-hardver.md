# Dostupný hardvér

Zdroj: používateľský súpis `Arduino HW.txt`, načítaný 2026-06-30.

## Potenciálne použiteľné priamo v projekte

- ESP32 – hlavná riadiaca jednotka,
- približne 3 malé reléové moduly – použiteľnosť sa overí podľa napätia, logiky a prúdového zaťaženia,
- Zigbee záplavový senzor – doplnkový alarm cez Home Assistant,
- snímač teploty a vlhkosti, modrý so 4 vývodmi – treba identifikovať presný typ,
- tlačidlá – lokálne manuálne zavlažovanie,
- aktívny bzučiak a LED – voliteľná lokálna signalizácia,
- nepájivé polia a Dupont vodiče – laboratórny prototyp,
- odpory 10 kΩ, 1 kΩ a 220 Ω – prototypovanie,
- ultrazvukový modul – možné experimentálne meranie hladiny,
- senzor okolitého svetla – voliteľné orientačné meranie osvetlenia.

## Infraštruktúra

- Home Assistant na Raspberry Pi 5,
- existujúca lokálna Zigbee sieť integrovaná do Home Assistant.

## Poznámky k výberu

- ESP32 je vhodnejšie než klasické Arduino, pretože má sieťové pripojenie a priamu podporu ESPHome.
- Arduino Nano, Uno, Mega ani Esplora nie sú plánované pre základnú zostavu. Použijú sa iba v samostatnom vzdelávacom experimente, ak na to vznikne konkrétny dôvod.
- Orange Pi a ďalšie jednodeskové počítače nie sú súčasťou návrhu.
- Tuya Wi-Fi zariadenia ani Tuya cloud sa v projekte nebudú používať.
- Zigbee zariadenie môže byť použité ako doplnok, ak komunikuje lokálne cez existujúcu Zigbee sieť bez závislosti od cloudovej služby.
- Ultrazvukové meranie hladiny môže ovplyvniť tvar nádrže a kondenzácia. Nízku hladinu preto musí strážiť jednoduchší nezávislý prvok, napríklad plavák.
- Existujúca Wi-Fi smart zásuvka môže poslúžiť nanajvýš pri krátkom kontrolovanom teste. Nie je súčasťou trvalého riešenia ani integrácie do Home Assistant.
- Nepájivé pole a Dupont vodiče sú určené iba na skúšobný prototyp, nie na trvalú montáž pri vode.

## Pravdepodobne potrebné dokúpiť

Konkrétne typy a počty sa určia po meraniach:

- nádrž s vekom,
- vhodné nízkonapäťové čerpadlo alebo čerpadlá,
- prípadné normálne zatvorené ventily,
- hadice, rozdeľovače, koncovky a regulované kvapkovače,
- filter a prvky proti sifónovaniu,
- plavákový snímač minimálnej hladiny,
- lokálny snímač úniku,
- výkonový spínací modul vhodný pre zvolené čerpadlo/ventily,
- vhodný napájací zdroj, poistka a svorky,
- uzatvorená montážna krabica a káblové priechodky,
- materiál na pevné uchytenie hadíc a elektroniky.
