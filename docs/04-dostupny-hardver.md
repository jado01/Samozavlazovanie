# Dostupný hardvér

Zdroj: používateľský súpis `Arduino HW.txt`, načítaný 2026-06-30.

## Potenciálne použiteľné priamo v projekte

- ESP32-WROOM-32 z HomeBrainz – hlavná riadiaca jednotka; podľa stránky produktu ide o 30-pin modul HW-394 s USB-C, napájaním 5 V/1 A, Wi-Fi 802.11 b/g/n, Bluetooth v4.2 BR/EDR + BLE, SPI flash 32 Mbit a rozmermi približne 54 × 28 × 10 mm; presný pinout sa ešte overí podľa fyzickej dosky pred prvým zapojením,
- reléový modul s relé SRD-12VDC-SL-C – 12 V cievka, svorky `+12V`, `GND`, `COM`, `NC`, `NO`; použiteľný skôr ako samostatný 12 V spínací modul, nie priamo z GPIO ESP32,
- 1-kanálový reléový modul s relé SRD-5VDC-SL-C – 5 V modul so vstupmi `VCC`, `GND`, `IN` a jumperom high/low level trigger; použiteľnosť s 3,3 V logikou ESP32 sa musí otestovať,
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
- Bežné ESP32-WROOM-32 podporuje 2,4 GHz Wi-Fi, nie 5 GHz Wi-Fi. Nameraný signál na balkóne sa preto hodnotí v 2,4 GHz pásme.
- GPIO piny ESP32 pracujú s 3,3 V logikou a nesmú byť zaťažované priamo cievkou relé alebo čerpadlom.
- Doska má na produktovej stránke pinout pre 30-pin variant. Pred zapojením sa bude porovnávať s potlačou na reálnej doske, pretože ESP32 vývojové dosky môžu mať rôzne rozloženie pinov aj pri rovnakom čipe.
- Relé SRD-5VDC-SL-C a SRD-12VDC-SL-C majú kontakty typicky označené pre 10 A pri vybraných AC/DC napätiach, ale pre trvalé riešenie pri vode sa bude dimenzovanie posudzovať konzervatívne podľa reálneho čerpadla a napájania.
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
