# Stav projektu

Posledná aktualizácia: **2026-07-18**

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
- používateľ sa oboznámil so základnou úlohou ESP32 a ESPHome,
- zamerané hlavné rozmery balkóna: výška 257 cm, šírka 96 cm, dĺžka 276 cm,
- doplnené výšky vreciek vo vertikálnych textilných kvetináčoch,
- doplnená vzdialenosť od plánovanej nádrže k paradajkám: približne 240 cm po zemi,
- doplnené rozmery textilného vrecka, črepníkov paradajok a poloha zásuvky,
- zmeraný predbežný Wi-Fi signál na balkóne pri zatvorených dverách: približne -74 až -82 dBm,
- doplnený dostupný riadiaci hardvér: ESP32-WROOM-32/HW-394 s USB-C a dva typy reléových modulov,
- vytvorené ESPHome zariadenie `balkon-zavlaha`,
- prvý firmware bol úspešne skompilovaný, nahratý do ESP32 a zariadenie bolo pridané do Home Assistant,
- zariadenie je v Home Assistant zaradené do oblasti `Balcony`,
- v izbe na stole bol cez ESP32/ESPHome pozorovaný Wi-Fi signál približne -66 dBm,
- do ESPHome boli doplnené diagnostické entity: Wi-Fi signál, uptime a restart button,
- test restart buttonu prebehol úspešne; uptime sa po reštarte vynuloval a zariadenie sa znova pripojilo,
- na balkóne pri zatvorenom zasklení bol cez ESP32/ESPHome pozorovaný veľmi slabý Wi-Fi signál približne -93 dBm,
- do lokálneho priečinka originálnych fotografií boli pridané nové zábery balkóna,
- rozhodnuté, že prvá verzia bude používať peristaltické 12 V čerpadlo riadené cez MOSFET modul, nie priame spínanie z ESP32 ani smart zásuvku,
- smart zásuvka bola vyhodnotená ako možný hlavný servisný alebo bezpečnostný vypínač napájania, nie ako hlavný spôsob dávkovania vody,
- vybraná prvá objednávka hardvéru: peristaltické čerpadlo, MOSFET LR7843, BME280, plavákový snímač hladiny, pôdne analógové vlhkomery, silikónová hadička a lacný vodný/dažďový senzor na experimenty,
- DHT11 zo staršieho Arduino kitu bude použitý len ako učebný a porovnávací senzor; pre balkónové meranie je preferovaný BME280,
- T-kusy, kvapkovače a finálny rozvod vody boli odložené až po kalibrácii reálneho prietoku čerpadla,
- prvý fyzický senzor BME280 bol pripájkovaný, pripojený k ESP32 cez I2C a úspešne zobrazený v Home Assistant,
- overené zapojenie BME280: `VIN -> 3V3`, `GND -> GND`, `SDA -> GPIO21`, `SCL -> GPIO22`,
- ESPHome I2C scan našiel BME280 na adrese `0x76`,
- v Home Assistant pribudli entity `Balkon Teplota`, `Balkon Vlhkost` a `Balkon Tlak`; prvé pozorované hodnoty boli približne 26,8 °C, 40,8 % a 930,4 hPa,
- živé meranie bolo overené zmenou hodnôt po dýchnutí na senzor.

## Čo práve riešim

Projekt je vo fáze prvých stolových hardvérových testov. ESP32 je online v Home Assistant, diagnostické entity fungujú a prvý externý senzor BME280 už odosiela teplotu, vlhkosť a tlak do HA. Wi-Fi na balkóne je slabé, ale používateľ ho teraz nechce riešiť ako blokujúcu tému; zlepšenie pokrytia zostáva neskorší stabilizačný krok. Ďalší vhodný krok je porovnanie BME280 s dostupným DHT11 alebo pokračovanie testom pôdneho vlhkomera.

## Najbližší odporúčaný krok

Pokračovať stolovým testovaním bez vody pri rastlinách:

1. porovnať hodnoty BME280 s dostupným DHT11 a prípadným existujúcim teplomerom v HA,
2. otestovať pôdny vlhkomer nasucho a vo vlhkom substráte, najprv s dôrazom na bezpečné napäťové úrovne pre analógový vstup ESP32,
3. otestovať MOSFET modul bez čerpadla alebo s bezpečnou skúšobnou záťažou,
4. pripojiť čerpadlo cez MOSFET a v pohári odmerať reálny prietok v ml/min,
5. výsledky zapísať do dokumentácie a až potom navrhnúť T-kusy, kvapkovače a rozvod k jahodám/paradajkám.

## Otvorené otázky a problémy

- presné doladenie trás hadíc, T-kusov a kvapkovačov po kalibrácii čerpadla,
- reálna denná spotreba vody jahôd a paradajok oddelene; aktuálny hrubý odhad pre jahody je približne 100 ml na jedno vrecko,
- kvalita Wi-Fi signálu na balkóne je veľmi slabá; ESP32 ukázalo približne -66 dBm v izbe a približne -93 dBm na balkóne pri zatvorenom zasklení,
- fyzické overenie pinoutu ESP32 dosky podľa potlače,
- presný typ staršieho snímača teploty/vlhkosti z Arduino kitu; pravdepodobne DHT11,
- použiteľnosť pôdneho vlhkomera pri napájaní z 3,3 V alebo potreba deliča napätia pri 5 V napájaní,
- rozhodnutie, či bude prvá vodná verzia používať jedno čerpadlo pre všetko alebo sa neskôr oddelia jahody a paradajky samostatnými čerpadlami,
- overenie elektrickej bezpečnosti zásuvky pri plánovanom umiestnení vody,
- overenie odtoku a správania vody vo vertikálnych textilných vreckách,
- zváženie smart zásuvky ako hlavného bezpečnostného odpojenia napájania,
- budúce rozšírenia: senzor svetla, robustnejšie meranie vetra pre automatizáciu zasklenia a prípadný dažďový/únikový senzor,
- výber verejných fotografií a ich očistenie od EXIF/GPS údajov.

## Pravidlo aktualizácie

Tento súbor sa aktualizuje na konci každej významnej pracovnej relácie. Nový veľký plán alebo zásadná zmena architektúry sa nezačne bez účasti používateľa.
