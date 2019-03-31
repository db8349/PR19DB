# Napovednik recesije
V današnjem globalnem svetu je neprestana gospodarska rast in ekonimičen napredek potrebna za vzdrževanje našega vsakdanjega
življenja. Kaj pa se zgodi, ko nastane kriza v sistemu? Nenadoma se pojavi velika brezposelnost, pomankanje posla za podjetja
ter izguba zaupanja investitorjev v trg in s tem manjše investicije. Te krize imajo velik upliv na naše vsakdanje življenje in
pogled na prihodnost zato bi bilo dobro vedeti, če jo lahko napovemo, da bi se tako morda bolje pripravili nanjo oz. še bolje
napovedali kje bodo nastale težave iz katerih se bo razvila naslednja kriza.

Cilj tega projekta je ugotoviti, če se da napovedati recesije na podlagi podatkov iz prejšnjih let in če obstajajo očitni
znaki, da smo pred njenim pragom. Opazovali bi tudi kako tesno so povezani naši trgi z svetovnimi in kako na nas vplivajo krize
v drugih državah ter ali se res svetovna gospodarska rast upočasnjuje.

## Podatki
Podatke bom primarno vzel iz https://data.worldbank.org/.

Podatki o:
* BDP-ju držav: https://data.worldbank.org/indicator/NY.GDP.MKTP.CD
* Vrednosti izvozov: https://data.worldbank.org/indicator/bx.gsr.gnfs.cd
* Vrednosti uvozov: https://data.worldbank.org/indicator/NE.IMP.GNFS.CD
* Vrednosti investicij: https://data.worldbank.org/indicator/BX.KLT.DINV.CD.WD

Podatki predstavljajo vrednosti za vsako državo v ameriških dolarjih ter so v formatu `.csv`.

V projektu bom tudi vzel pomembnejše dogodke, ki so vplivali na svetoven trg (2007 Kriza hišnega trga v ZDA, 2016 Brexit, 2009 Grška finančna kriza itd.)

## Analiza globalne finančne krize leta 2008

Poročilo bom začel z začetno analizo globalne finančne krize leta 2008, saj je ta najbolj povdarna "svetovna" kriza, ki je imela velik vpliv na veliko večino prebivalstva. Beseda "svetovna" je namenoma podana v narekovajih ker ta kriza ni vplivala na vse trge/regije po svetu, ampak primarno samo na zahodne trge, ker pa so te tako veliki in vplivni pa hitro potegnemo črto na "svetovno" krizo.
![Map of country GDP growth in 2008](https://github.com/db8349/PR19DB/blob/master/img/country_growth_gdp_2008.png)
Mapa rasti BDP-ja v letu 2008 nam presenetljivo ne da občutka, da je sploh kaj narobe. Res vidimo da se je rast zahodnih ekonomij upočasnila, kar pa se ne zdi prav glede na katastrofalen učinek, ki ga je imela. Bolj zanimive podatke dobimo, ko pogledamo zemljevid za leto 2009.
![Map of country GDP growth in 2009](https://github.com/db8349/PR19DB/blob/master/img/country_growth_gdp_2009.png)
Tukaj vidimo kako kako močno se je gospodarstvo skrčilo leto po napovedu krize. Vidi se tudi kako so države, ki bolj povezani z zahodnim trgom, res najbolj občutile to krizo. Druge velike ekonomije kot so Kitajska in Indija pa  so močno rastle.

Za anžuriranje podatkov sem uporabil knjižnico `pandas`, za ustvarjanje teh zemljevidov pa `geopandas`. Programsko kodo sem razvijal v jupyter okolju in jo shranil v mapo `/src`, ter nakoncu pridobljene grafe izvozil kot slike formata `.png` v mapo `/img`.

## Problemi

* Pomankanje podatkov za nekatere države, kar pomeni da jih ni prikazalo na končnih grafih. To težavo sem na koncu rešil tako, da sem     vse države, za katere nisem imel podatkov, pobarval sivo in jih s tem lažje razločil od drugih. 
* Ko sem iskal barvno območje, ki bi predstavljalo rast oz. padec BDP-ja držav. Sem sem hotel barvno območje od zelene do rdeče,           `matplotlib` pa ima prevzeto na voljo le od zelene do rumene do rdeče. To pa je problem, ker je veliko držav brez očitne rasti oz.       padca BDP-ja, kar pa pomeni da so na zemljevidu kar nerazločne.
