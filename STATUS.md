# Stav projektu

Posledná aktualizácia: **2026-07-10**

Tento projekt je súčasťou centrálneho projektu **studijna-cesta**. Slúži zároveň ako praktické vzdelávanie v oblasti ESP32, ESPHome, Home Assistant, elektroniky, automatizácie, merania a Gitu a ako budúci portfóliový projekt.

## Cieľ projektu

Navrhnúť, postaviť a zdokumentovať spoľahlivý automatický zavlažovací systém pre dve cherry paradajky a desať jahôd na zasklenom balkóne. Systém má umožniť automatické aj manuálne zavlažovanie, dohľad a históriu v Home Assistant a bezpečné lokálne vypnutie pri poruche. Prvá verzia má overiť funkčnosť s malou skúšobnou nádržou; dlhšia autonómia 8 až 14 dní bude neskoršie rozšírenie.

## Čo je už dokončené

- vytvorený a zverejnený GitHub repozitár so základnou štruktúrou,
- zdokumentovaný východiskový stav balkóna, rastlín a dostupnej infraštruktúry,
- pripravená predbežná architektúra riadenia, vodnej časti a bezpečnostných prvkov,
- spísaný dostupný hardvér a predbežný zoznam potrebných nákupov,
- prijaté rozhodnutie začať malou funkčnou verziou namiesto veľkej dovolenkovej nádrže,
- pripravený kontrolný zoznam rozmerov, fotografií a skúšok po návrate,
- originálne fotografie oddelené od verejnej dokumentácie pre EXIF/GPS údaje,
- overená inštalácia Home Assistant OS na Raspberry Pi 5 s NVMe,
- vytvorená manuálna záloha Home Assistant,
- nainštalovaný a spustený ESPHome Device Builder; zapnuté automatické spustenie a watchdog,
- používateľ sa oboznámil so základnou úlohou ESP32 a ESPHome.
- zamerané hlavné rozmery balkóna: výška 257 cm, šírka 96 cm, dĺžka 276 cm,
- doplnené výšky vreciek vo vertikálnych textilných kvetináčoch,
- doplnená vzdialenosť od plánovanej nádrže k paradajkám: približne 240 cm po zemi,
- doplnené rozmery textilného vrecka, črepníkov paradajok a poloha zásuvky,
- zmeraný predbežný Wi-Fi signál na balkóne pri zatvorených dverách: približne -74 až -82 dBm,
- doplnený dostupný riadiaci hardvér: ESP32-WROOM-32/HW-394 s USB-C a dva typy reléových modulov,
- do lokálneho priečinka originálnych fotografií boli pridané nové zábery balkóna.

## Čo práve riešim

Projekt je v prípravnej fáze pred fyzickým návrhom a nákupom komponentov. Hlavné rozmery balkóna, základné výšky jahôd, rozmery vreciek, črepníkov, poloha zásuvky a predbežný Wi-Fi signál sú už doplnené. Ďalej treba skontrolovať fotografie, identifikovať dostupné elektronické moduly a spraviť základné merania spotreby vody.

## Najbližší odporúčaný krok

Pokračovať malou meracou reláciou podľa `docs/03-podklady-po-navrate.md`:

1. skontrolovať nové fotografie a vybrať, ktoré zábery budú vhodné do verejnej dokumentácie po odstránení EXIF/GPS údajov,
2. overiť fyzický pinout ESP32 dosky a otestovať reléový modul na stole bez čerpadla,
3. neskôr overiť Wi-Fi priamo cez ESP32/ESPHome a odmerať množstvo vody pre jahody a paradajky oddelene,
4. výsledky spolu skontrolovať a zapísať do dokumentácie ešte pred výberom čerpadla a nákupom dielov.

## Otvorené otázky a problémy

- presné doladenie časti trás hadíc,
- reálna denná spotreba vody jahôd a paradajok oddelene,
- kvalita Wi-Fi signálu je hraničná; treba overiť stabilitu priamo cez ESP32/ESPHome alebo doplniť lepšie pokrytie,
- fyzické overenie pinoutu ESP32 dosky podľa potlače a presný typ snímača teploty/vlhkosti,
- použiteľnosť dostupného 5 V reléového modulu s 3,3 V logikou ESP32,
- voľba čerpadla, výkonového spínania, hadíc a kvapkovačov až po meraní,
- rozhodnutie medzi jedným čerpadlom s ventilmi a dvoma čerpadlami,
- overenie elektrickej bezpečnosti zásuvky pri plánovanom umiestnení vody,
- overenie odtoku a správania vody vo vertikálnych textilných vreckách,
- výber verejných fotografií a ich očistenie od EXIF/GPS údajov.

## Pravidlo aktualizácie

Tento súbor sa aktualizuje na konci každej významnej pracovnej relácie. Nový veľký plán alebo zásadná zmena architektúry sa nezačne bez účasti používateľa.
