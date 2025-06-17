# Dokumentacija izvedenih lastnosti

Ta dokument zajema podrobnosti o implementaciji posameznih funkcionalnosti (taskov), kot so bile opisane in vodene v sistemu JIRA, skupaj z načinom uporabe za končne uporabnike.

---

## ROCK-109 – Prijava, registracija, odjava, shranjevanje JWT
**Namen**: Omogočiti varno prijavo in registracijo uporabnikov s pomočjo žetonov JWT.  
**Način implementacije**:
- Zaledni sistem (backend) generira in preverja JWT ob prijavi.
- Čelni del shranjuje JWT v `localStorage`. 

**Način uporabe**: Uporabnik se registrira ali prijavi prek obrazca, sistem si zapomni prijavo, dokler se uporabnik ne odjavi.

---

## ROCK-110 – Prikaz seznama plezališč in ustvarjanje novih
**Namen**: Uporabniku omogočiti pregled in dodajanje novih plezališč.  
**Način implementacije**:
- Seznam je pridobljen s klicem Zaledni del in prikazan v tabeli.
- Dodajanje preko obrazca.  

**Način uporabe**: Uporabnik vidi seznam plezališč in z gumbom "Dodaj plezališče" lahko vnese novo.

---

## ROCK-111 – Prikaz plezališč na zemljevidu Slovenije
**Namen**: Vizualna predstavitev lokacij plezališč.  
**Način implementacije**:
- Uporaba OpenStreetMap s knjižnico Leaflet.
- Markerji predstavljajo posamezna plezališča.

---

## ROCK-112 – Prikaz posameznega plezališča in seznama smeri
**Namen**: Prikaz podrobnosti o plezališču skupaj z njegovimi smermi.  
**Način implementacije**:
- Zaledni del za pridobivanje podatkov o plezališču in njegovih smereh.
- Na čelnem delu nova stran, ki to prikazuje (zgoraj informacije in spodaj smeri).

**Način uporabe**: Klik na plezališče odpre stran z informacijami in vsemi smermi.

---

## ROCK-114 – Dodajanje notranjih plezalnih centrov
**Namen**: Uporabnikom omogočiti dodajanje in prikaz plezalnih centrov.  
**Način implementacije**:
- Obrazec z vnosom podatkov in zemljevid, na katerem izberemo lokacijo.
- Prikaz na zemljevidu z ločenimi ikonami (plezalni centri in zunanja plezališča posebej).  

**Način uporabe**: Uporabnik lahko doda nove centre.

---

## ROCK-115 – Uporabniški profil
**Namen**: Omogočiti uporabnikom, da pogledajo število preplezanih smeri ter povprečno število poizkusov.
**Način implementacije**:
- Zaledni del za pridobivanje informacij.
- Prikaz na profilu.  

**Način uporabe**: Uporabnik klikne na svojo ikono, ter klikne na profil, tam se mu prikažejo te informacije.

---

## ROCK-116 – Uporabniške skupine
**Namen**: Uporabniki lahko dodajajo in upravljajo skupine.  
**Način implementacije**:
- Ob kreiranju skupine se kliče zaledni del, ki podatke shrani.
- Posebej stran za prikaz skupin.  

**Način uporabe**: Uporabnik ustvari skupino ali se ji pridruži.

---

## ROCK-117 – Dogodki
**Namen**: Dodajanje dogodkov 
**Način implementacije**:
- Obrazec za vnos podrobnosti o dogodku.
- Prikaz na strani moji dogodki.  

**Način uporabe**: Uporabniki lahko ustvarijo dogodke. Če je dogodek privaten, potem lahko druge uporabnike doda samo lastnik, v nasprotnem primeru pa se lahko na dogodek prijavijo sami.

---

## ROCK-140 – Izbiranje lokacije preko zemljevida
**Namen**: Uporabniku poenostaviti vnos geolokacije.  
**Način implementacije**:
- Klik na zemljevidu zabeleži lokacijo.
 
**Način uporabe**: Uporabnik pri dodajanju plezališča klikne na želeno točko na zemljevidu.

---

## ROCK-154 – Filtriranje v bližini na zemljevidu
**Namen**: Prikaz plezališč v bližini lokacije uporabnika.  
**Način implementacije**:
- Uporaba knjižnjice "haversine-distance".
- Filtriranje rezultatov glede na radij.  

**Način uporabe**: Uporabnik lahko izbere koordinate na zemljevidu razdaljo pa izbere z drsnikom. Prikažejo se mu plezališča v tem obsegu.

---

## ROCK-175 – Geo prostorske poizvedbe za večkotnike
**Namen**: Prikaz plezališč v nekem območju, ki ni krog  
**Način implementacije**:
- Na zalednem delu uporaba knjižnjice "point-in-polygon".
- Prikaz plezališč v večkotniku.
- Dodatni gumbi za izbiro načina filtriranja.

**Način uporabe**: Uporabnik klikne na gumb z ikono večkotnika. Nato izbere poljubno število točk, katere se povežejo. Na zemljevidu se prikažejo plezališča na tem območju.

---

## ROCK-180 – Dodajanje zaznamkov notranjim centrom
**Namen**: Uporabniku omogočiti označevanje priljubljenih centrov.  
**Način implementacije**:
- Zaledni del shrani uporabniški zaznamek v bazo.
- Čelni del: ikona za dodajanje/odstranjevanje.  

**Način uporabe**: Uporabnik klikne na ikono zvezdice in spremlja svoje najljubše centre.

---
## ROCK-107 – Animirana težavnost smeri skozi čas
**Namen**: Boljši pregled nad zgodovino težavnosti poti.
**Način implementacije**
- Zaledni del pošlje podatke v seznamih (koliko katerih ocen je za posamezen mesec).
- Čelni del prikaže graf z animacijo skozi čas.
- Uporaba knjižnjice "Recharts".

**Način uporabe**: Ko uporabnik odpre stran plezalne poti se mu predvaja animacija težavnosti skozi čas. Animacijo si lahko s klikom na gumb ponovno predvaja.

## ROCK-204 – Dodajanje drsnika za graf na smereh
**Namen**: Boljši pregled težavnosti poti skozi čas.  
**Način implementacije**:
- Drsnik pod grafom omogoča prikaz težavnosti po mesecih.
- Dodaten gumb za preklapljanje med pogledom za posamezne mesece ali pa za vse do izbranega meseca.
- Uporaba knjižnjice "Recharts".

**Način uporabe**: Uporabnik premika drsnik in vidi, kako se težavnost smeri spreminja skozi čas.

---

## ROCK-220 – Unit testi za plezališča in plezalne centre
**Namen**: Zagotoviti stabilnost in pravilno delovanje zalednih funkcij.  
**Način implementacije**:
- Jest unit testi za modele in storitve.
- CI cevovodi za preverjanje ob prošnji za potisk na vejo 'develop'. 


