# Önműködő növényöntöző rendszer
###### Kovács Martin Zoltán (K5UURM)
###### Hegedüs Róbert (B3Y5TF)

### Tartalomjegyzék
1. Projekt bemutatása	
2. Komponensek	
3. Kapcsolási ábra	
4. Kódsor
5. Működése

# A projekt
Témaválasztásunknál a főszempont az volt, hogy egy a hétköznapokban alapvetően rutin feladatot, amely könnyen elfelejthető hogyan tudnánk automatizálni. Maga az automatizáció napjainkban már széleskörben elterjedt otthonainkban (pl.: automatikus lámpakapcsoló, - garázsajtó, stb.), de az iparban is teret hódított magának elég csak az autóiparra gondolni. A munkáltatónak jobban megéri, hiszen kevesebbet kell fizetnie az erőforrások után, hiszen kisebb munkaerő szükséges egy automatizált gyártósor mellé, arról nem is beszélve, hogy az emberi forrásból származó hibalehetőségek jelentősen csökkenek.
Az emberek nagyrészének van otthon valamilyen fajta kis növénye, amelynek alapvető igénye, hogy folyadékra van szüksége, ugyan úgy, mint az embernek, erről azonban könnyen meg lehet feledkezni, ami nem szokott jól végződni. Ezt a problémát kívántuk megoldani egy autonóm locsoló rendszerrel, amely akkor locsol, amikor szükséges. Természetes a rendszert tetszőlegesen lehet méretezni, így a mezőgazdaságban is könnyen alkalmazni lehet például üvegházakban, így lehet megoldani az öntözés szervezését, amely egy nagyobb méretű gazdaságban komoly előnyt jelenthet.
A következő dokumentációval az a célunk, hogy az iránymutatások segítségével meg lehessen valósítani a projektünket vagy egy hozzá hasonló rendszer készíthető legyen.

### Komponensek
- Arduino UNO Rev3 (A000066)

![Alt Text](https://i.imgur.com/grbpmyf.jpg)
- DHT11 Páratartalom szenzor modul

![Alt Text](https://i.imgur.com/2lH2KSz.jpg)
- Talajnedvesség érzékelő higrométer szenzor modul

![Alt Text](https://i.imgur.com/Am2Mjxz.jpg)
- Karakteres LCD kijelző

![Alt Text](https://i.imgur.com/hHqOGsP.jpg?1)
- Relé modul (12V)

![Alt Text](https://i.imgur.com/qFKFAxo.jpg)
- Tápegység 12V/1A dugvillás – 12 Watt (PL90001)

![Alt Text](https://i.imgur.com/5v6nLeC.jpg)
- Breadboard (Dugaszolós próbapanel)

![Alt Text](https://i.imgur.com/D9MEpU4.jpg)
- Színes Breadboard Jumper kábel (anya-apa/anya-anya)

![Alt Text](https://i.imgur.com/xM3Muh0.jpg)
- Vízpumpa 12 V-os

![Alt Text](https://i.imgur.com/c61EAnh.jpg?1)

### Kapcsolási ábra
![Alt Text](https://i.imgur.com/a0c7IVJ.png)

### Kódsor


# Működése
A rendszer folyamatosan megy, minden másodpercben ellenőrzi a szenzorokat, hogy történt-e változás a beolvasott értékekben. A kapott értéktől függően 2 dolog történhet. 
1. Ha eddig száraz talajban volt a nedvesség szenzor, akkor jelet küld, hogy locsolni kéne. Aktiválja a relét, ezáltal pedig a szivattyú áramot kap és elindul a locsolás.
2. Ha már nedves a talaj, a szenzor deaktiválódik, kikapcsol a relé, lekapcsol a szivattyú, és megszűnik a locsolás.
A talajnedvesség mellett a rendszer folyamatosan nézi a levegő hőmérsékletét és páratartalmát. Ezeket az adatokat követhetjük a kis LCD kijelzőn, valamint az olvasott adatokat kimenti egy Excel táblázatba.

### Lehetőségek a jövőre nézve

A rendszert folyamatosan lehet bővíteni további modulokkal, mert többet is tud egyszerre kezelni, arról nem is beszélve, hogy a nap 24 órájában üzemképes a hét minden napján.

- A rendszert lehet optimalizálni több féle módon is, erre egy példa a mérés pontosítása érdekében, hogy a talaj nedvesség érzékelőt digitális jeladásról analógra állítjuk, amely lehetővé teszi pontos értékek folyamatos olvasását. Ezt a mért feszültség szint erősségéből lehet megfelelő módon kiolvasni. Az ebből származó adatokat pedig információ gyűjtés céljából dokumentálni lehet és egy adatbázisban eltárolni. A pontos adat lehetővé teszi azt is, hogy különböző igényű növényeket is lehessen kezelni vele, mert a megfelelő környezetet képesek vagyunk biztosítani a számukra. Például a paradicsomnak a nedvesebb talaj jobban kedvez, mint a száraz, viszont a kaktusz inkább a száraz talajt preferálja minimális locsolással.

- Másik lehetőség, hogy a szenzorok számát (talaj nedvesség mérő, víz pumpa, hőmérő) tetszőleges mértékben is lehet növelni, ez lehetővé teszi, hogy ha otthon van 4 féle különböző növény egymástól független cserépben őket is lehet egy időben a saját igényeik szerint menedzselni. Ezzel is időt és energiát tudunk megspórolni magunk számára.

- A megfelelő komponensek fejlesztésével könnyen az iparba is beépíthető rendszert kapunk. Ilyen fejlesztés például a víz pumpa lecserélése egy ipari környezetben is használhatóra, hogy el tudjon látni egy akár több hektárnyi területű üvegházat is. Ipari méretekben természetesen a kezelő eszközt (Arduino) célszerű egy ilyen célra alkalmas vezérlő egységre leváltani (pl.: PIC micro controller-e).

- Bővítési lehetőség a hőmérő passzív szerepét aktívvá váltani. A beolvasott adatok alapján megoldható, hogy a kapott értékeket email-ben, vagy telefonra a vezérlő eszköz elküldje, ha az értékek szélsőségesre változnak akkor javaslatot küldjön a felhasználónak, a termosztát megfelelő átállítására. Ha a háztartásban a termosztát újabb fejlesztésű és alkalmas az internetes csatlakozásra, annak vezérlésére is alkalmas lehet a rendszer, kiváltva ezzel az emberi beavatkozást.

- A rendszer bővíthető újabb szenzorok hozzáadásával is, például egy fényérzékelő szenzorral. Ezzel a bővítéssel megoldható lenne, hogy a növények felett elhelyezett lámpákat a fényviszony függvényében automatikusan fel illetve le kapcsolja az eszköz. Újabban kezdenek elterjedni az "okos" RGB-s LED lámpák, amik több szempontból is jók lehetnek. Wifi vagy bluetooth kapcsolat segítségével irányításuk könnyen megoldható, valamint színkód alapján akár pontos színt is megadhatunk, hogy milyen fényt kapjon a növény.

- Beltéri alkalmazás mellett hasznos lehet akár egy webkamera hozzáadása a rendszerhez. Ezek  könnyen csatlakoztathatóak az internetre, ezáltal lehetővé téve, hogy távolról ránézhessünk, hogy a rendszer épp mit csinál, minden rendeltetésszerűen működik-e.

