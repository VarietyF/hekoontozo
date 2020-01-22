Kod formazasa!

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

fenyerzekelo, webkamera, 

A rendszer bővíthető újabb szenzorok hozzáadásával is, például egy fényérzékelő szenzorral. Ezzel a bővítéssel megoldható lenne, hogy a növények felett elhelyezett lámpákat a fényviszony függvényében automatikusan fel illetve le kapcsolja az eszköz. Újabban kezdenek elterjedni az "okos" RGB-s LED lámpák, amik több szempontból is jók lehetnek. Wifi vagy bluetooth kapcsolat segítségével irányításuk könnyen megoldható, valamint színkód alapján akár pontos színt is megadhatunk, hogy milyen fényt kapjon a növény.

Beltéri alkalmazás mellett hasznos lehet akár egy webkamera hozzáadása a rendszerhez. Ezek  könnyen csatlakoztathatóak az internetre, ezáltal lehetővé téve, hogy távolról ránézhessünk, hogy a rendszer épp mit csinál, minden rendeltetésszerűen működik-e.


homerseklet

Bővítési lehetőség a hőmérő passzív szerepét aktívvá váltani. A beolvasott adatok alapján megoldható, hogy a kapott értékeket email-ben, vagy telefonra a vezérlő eszköz elküldje, ha az értékek szélsőségesre változnak akkor javaslatot küldjön a felhasználónak, a termosztát megfelelő átállítására. Ha a háztartásban a termosztát újabb fejlesztésű és alkalmas az internetes csatlakozásra, annak vezérlésére is alkalmas lehet a rendszer, kiváltva ezzel az emberi beavatkozáat.