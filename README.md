# Automatické zavlažovanie balkóna

Projekt automatického zavlažovania rastlín na južne orientovanom zasklenom balkóne s integráciou do Home Assistant.

Projekt vzniká v lektorskom režime: jeho cieľom nie je iba hotové zariadenie, ale osvojenie práce s ESP32, elektronikou, ESPHome, Home Assistant, programovaním, Linuxom, meraním a Gitom. Jednotlivé časti bude používateľ navrhovať, zapájať, programovať a testovať s vedením Codexu.

## Cieľ

- spoľahlivo zavlažovať dve cherry paradajky a desať jahôd,
- v prvej verzii spoľahlivo zavlažovať aspoň 1 až 3 dni z malej skúšobnej nádrže,
- po overení funkcie rozšíriť autonómiu najmenej na 8 dní, cieľovo na 12 až 14 dní,
- umožniť automatické aj manuálne zavlažovanie z Home Assistant,
- fungovať bezpečne aj pri výpadku Home Assistant alebo Wi-Fi,
- zaznamenávať merania, zavlažovanie, alarmy a spotrebu vody,
- vytvoriť reprodukovateľný projekt s fotografiami, schémami, kódom a testami,
- neskôr rozšíriť systém o kameru a automatické ovládanie zasklenia.

## Aktuálny stav

Projekt je vo fáze zberu podkladov a návrhu. MVP (*Minimum Viable Product* – najmenšia funkčná verzia) použije malú dostupnú nádobu a sústredí sa na riadenie, dávkovanie a bezpečné vypnutie. Veľká nádrž nie je súčasťou tejto verzie.

## Navrhnuté etapy

1. Zamerať balkón a zdokumentovať existujúci stav.
2. Zmerať dennú spotrebu vody oboch skupín rastlín.
3. Postaviť stolový prototyp elektroniky a jedného vodného okruhu.
4. Otestovať prietok a rovnomernosť desiatich vývodov pre jahody.
5. Namontovať dva nezávislé zavlažovacie okruhy.
6. Integrovať ESPHome a Home Assistant.
7. Otestovať poruchové stavy a minimálne 7 dní skúšobnej prevádzky pod dohľadom.
8. Nasadiť systém na prevádzku počas neprítomnosti.

## Dokumentácia

- [Východiskový stav](docs/01-vychodiskovy-stav.md)
- [Predbežná architektúra](docs/02-predbezna-architektura.md)
- [Podklady po návrate](docs/03-podklady-po-navrate.md)
- [Dostupný hardvér](docs/04-dostupny-hardver.md)
- [Záznam návrhových rozhodnutí](docs/05-rozhodnutia.md)
- [Súkromné originálne fotografie](assets/photos/original/README.md)
- [Obrázky určené na zverejnenie](docs/images/README.md)
