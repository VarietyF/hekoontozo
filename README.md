# Önműködő növényöntöző rendszer
###### Kovács Martin Zoltán (K5UURM)
###### Hegedüs Róbert (B3Y5TF)

### Tartalomjegyzék
1. Projekt bemutatása	
2. Komponensek	
3. Kapcsolási ábra	
4. Kódsor
5. Működése

### Önműködő öntöző rendszer
Témaválasztásunknál a főszempont az volt, hogy egy a hétközna-pokban alapvetően rutin feladatot, amely könnyen elfelejthető hogyan tudnánk automatizálni. Maga az automatizáció napjainkban már széleskörben elterjedt otthonainkban (pl.: automatikus lámpakapcsoló, - garázsajtó, stb.), de az iparban is teret hódított magának elég csak az autóiparra gondolni. A munkáltatónak jobban megéri, hiszen kevesebbet kell fizetnie az erőforrások után, hiszen kisebb munkaerő szükséges egy automatizált gyártósor mellé, arról nem is beszélve, hogy az emberi forrásból származó hibalehetőségek jelentősen csökkenek.
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


### Kódsor
![Alt Text](https://i.imgur.com/a0c7IVJ.png)

### Működése
A rendszer folyamatosan megy, minden másodpercben ellenőrzi a szenzorokat, hogy történt-e változás a beolvasott értékekben. A kapott értéktől függően 2 dolog történhet. 
1. Ha eddig száraz talajban volt a nedvesség szenzor, akkor jelet küld, hogy locsolni kéne. Aktiválja a relét, ezáltal pedig a szivattyú áramot kap és elindul a locsolás.
2. Ha már nedves a talaj, a szenzor deaktiválódik, kikapcsol a relé, lekapcsol a szivattyú, és megszűnik a locsolás.
A talajnedvesség mellett a rendszer folyamatosan nézi a levegő hőmérsékletét és páratartalmát. Ezeket az adatokat követhetjük a kis LCD kijelzőn, valamint az olvasott adatokat kimenti egy Excel táblázatba.

### Lehetőségek a jövőre nézve

A felhasználó és az adott növény igényei szerint tetszőlegesen lehetne hangolni a rendszert, hogy a lehető leg optimálisabb működést érjük el.
