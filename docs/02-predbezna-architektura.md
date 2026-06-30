# Predbežná architektúra

Toto je pracovný návrh. Konkrétne čerpadlo, ventily, priemery hadíc a kvapkovače sa vyberú až po zameraní a prietokovej skúške.

## Funkčné členenie

### Riadenie

- ESP32,
- ESPHome,
- integrácia do Home Assistant,
- lokálna automatika pre základné zavlažovanie,
- manuálne spustenie fyzickým tlačidlom a z Home Assistant,
- pevný maximálny čas jedného zavlažovania,
- blokovanie čerpadla pri nízkej hladine alebo úniku vody.

Home Assistant bude slúžiť na dohľad, nastavovanie, históriu a upozornenia. Nesmie byť jediným miestom, kde sa vykonáva kritická logika zavlažovania.

### Vodná časť

- malá stabilná uzatvorená skúšobná nádrž; pre prvé testy približne 4 až 15 l,
- filter pred čerpadlom alebo rozvodom,
- nízkonapäťové čerpadlo,
- ochrana proti spätnému toku a samovoľnému sifónovaniu,
- dve samostatne ovládané vetvy:
  - vetva A: 10 jahôd,
  - vetva B: 2 paradajky,
- samostatný vývod ku každému obsadenému vrecku jahôd,
- záchytné riešenie pre prípad pretečenia.

O tom, či sa použije jedno čerpadlo s dvoma ventilmi alebo dve samostatné čerpadlá, rozhodne skúška prietoku, požadované dávkovanie, hlučnosť a cena.

Veľká dovolenková nádrž nie je súčasťou prvej funkčnej verzie (MVP). Najprv sa overí opakovateľnosť dávky, rovnomernosť vývodov, lokálne bezpečnostné vypnutie a ovládanie cez Home Assistant. Nameraná spotreba potom určí požadovaný objem bez zbytočného predimenzovania.

### Elektrická bezpečnosť pri nádrži

- pri nádrži, hadiciach a na úrovni podlahy bude iba bezpečné malé napätie,
- napájací zdroj a všetky časti na 230 V musia byť mimo možného úniku a striekajúcej vody,
- existujúca zásuvka bez deklarovaného IP krytia sa pred použitím odborne posúdi,
- preverí sa ochrana zásuvkového okruhu prúdovým chráničom,
- podľa výsledku sa zásuvka nahradí vhodným krytým vyhotovením alebo sa napájací zdroj umiestni do suchého interiéru,
- káble budú vedené so slučkou proti stekaniu vody a s odľahčením ťahu,
- riadiaca skrinka nebude ležať na podlahe ani priamo pod vodnými spojmi.

Samotný sklon podlahy ani otvor na odtok nie sú elektrickou ochranou. Konečné riešenie sieťovej časti musí zohľadniť skutočné vonkajšie vplyvy na mieste.

### Snímače a ochrany

Minimálna bezpečná zostava:

- plavákový snímač minimálnej hladiny v nádrži,
- lokálny snímač úniku vody pri nádrži/čerpadle,
- snímač teploty a relatívnej vlhkosti vzduchu,
- maximálny čas behu čerpadla v ESP32,
- hlásenie nedostupnosti zariadenia v Home Assistant.

Voliteľné merania:

- priebežná výška hladiny,
- prietok vody,
- teplota vody,
- kontrolné kapacitné snímače vlhkosti substrátu,
- intenzita svetla.

Snímače vlhkosti substrátu budú pomocným údajom, nie jediným spúšťačom. Textilné vrecká vysychajú nerovnomerne a jeden snímač nereprezentuje celý vertikálny záhon.

## Režimy

- **Automatika:** zavlažovanie samostatných vetiev podľa nastaveného plánu a kalibrovanej dávky.
- **Manuálne:** krátke spustenie z HA alebo tlačidla, stále so všetkými bezpečnostnými limitmi.
- **Dovolenka:** prísnejšie alarmy, kontrola dostupnosti a dostatočnej zásoby vody.
- **Servis:** samostatné testovanie čerpadla, ventilov a jednotlivých vetiev.
- **Porucha:** čerpadlo vypnuté; alarm pri úniku, nízkej hladine alebo prekročení času.

## Kamera a budúce ovládanie okien

Kamera je vhodná na vizuálnu kontrolu rastlín a prípadného úniku, ale nie je bezpečnostným prvkom zavlažovania. Pred zaobstaraním TP-Link kamery treba poznať presný model a overiť lokálny stream alebo podporu integrácie s Home Assistant.

Automatické ovládanie dvoch stredných tabúľ bude samostatný podsystém. Zavlažovanie už teraz môže poskytovať údaje o teplote a vlhkosti, ktoré sa neskôr využijú na vetranie.
