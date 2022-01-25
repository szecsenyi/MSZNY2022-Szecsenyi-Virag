# Az ige helyhatározói bővítményeinek megkülönböztetése és az argumentumszerkezeti variánsok korpusz alapú szétválasztása
## A kutatáshoz tartozó korpuszadatok
Szécsényi Tibor - Virág Nándor 2022: *Az ige helyhatározói bővítményeinek megkülönböztetése és az argumentumszerkezeti variánsok korpusz alapú szétválasztása*. In MSZNY 2022. Szeged, Szegedi Tudományegyetem.

A depozitórium a kutatáshoz használt és a feldolgozás során nyert adatokat tartalmazza, az adatokat szolgáltató programokat nem.

### A könyvtár tartalma:
A `Szecsenyi-Virag-MSZNY2022.pdf` a tanulmány preprint változata.  
A `szeged-stat.xlsx` fájl a [Szeged Treebank](https://rgai.inf.u-szeged.hu/node/113) adatai alapján nyert tagmondatonkénti bővítménytípus-előfordulási számokat tartamazza.  
A `locatives` könyvtár a *3. Helyhatározói esetragok eloszlási mintázatai* fejezet adatait tartalmazza.   
Az `argszerkvar` könyvtár a *4. Argumentumszerkezeti variánsok elkülönítése* fejezet adatait tartalmazza.

### szeged-stat.xlsx
A táblázat sorai az adott igekötő+igét fejként tartalmazó mondatokban előforduló bővítménytípusok előfordulási számait tartalmazzák. 

Az első oszlop tartalmazza az igekötőt (0, ha igekötő nélküli), a második oszlop az (igekötőtlen) lemmát, a harmadik az igekötő+lemmát.  
Az elváló és tapadó igekötők egyaránt szerepelnek. A lemmákról le vannak vágva a műveltető (*-tat*) és ható (*-hat*) képzők, ezeket a *cau* és a *pot* oszlopok jelzik.  
A *mood* oszlop az ige/tagmondat alakját/módját jelöli: *ind*:kijelentő, *imp*:felszólító, *cnd*:feltételes, *inf*:főnévi igenév  
Az *n*(G) oszlop az adott igekötő+ige előfordulási számait tartalmazza.  
Az ettől jobbra található oszlopok az egyes argumentumtípusok előfordulási számait tartalmazzák.  

Az első sor a *mood=ind* kijelentő módú sorok összesített értékeit tartalmazzák: összesen 132.951 kijelentő módú ige (ill. ilyen fejű tagmondat) van a korpuszban, ezekben 74.353 alany esetű maximális bővítmény stb. A második sor az ezen értékekből számított előfordulási gyakoriságot: a G1 cella értékével való osztás eredményét.


### locatives
A `locatives` könyvtár alkönyvtárai a vizsgált igékhez tartozó adatokat tartalmazzák. Az egyes könyvtárakban a következő fájlok találhatók (a fájlok felsorolása a feldolgozási lépéseket követik):
* `*.txt` - a [Magyar Nemzeti Szövegtárból](http://clara.nytud.hu/mnsz2-dev/) lekért szűretlen mondatok listája; az adatok igekötős igéket is tartalmaznak 
* `*.tsv` - a duplikátumok kiszűrése után maradt mondatok [magyarlánccal](https://rgai.inf.u-szeged.hu/magyarlanc) elemzett változata
* `*.2.xml` - a magyarláncos elemzés xml fájllá alakított változata, az igék leírása kiegészítve az igekötőkapcsolási és kiterjesztett lemma információkkal
* `*.elv.xlsx` - az elváló igekötőt tartalmazó mondatok kézi szűrése: ha a vizsgált igéhez tartozik elváló igekötő, a mondatot töröltük (-1), a többi hibás elemzést javítottuk (0: nem igekötő lett igekötőnek elemezve, 2: rossz igéhez lett kapcsolva egy elváló igekötő) (1: jó elemzés)
* `*.cplist.xml` - a magyarlánc függőségi elemzője alapján megállapított tagmondatleíró fájl: jelölve a tagmondat eleje és vége, a tagmondat fejének fontosabb tulajdonságai, a tagmondatban levő maximális XP-k (bővítmények) fontosabb tulajdonságai
* `*.args2.tsv` - a tagmondatok (igék) mellett megjelenő bővítménytípusok tagmondatonkénti felsorolása (csak a vizsgált ige vizsgált argumentumszerkezeti variánsait tartalmazza, azokból is csak a vizsgált bővítménytípusokat; csak kijelentő módú igék)


### argszerkvar
Az `argszerkvar` könyvtár alkönyvtárai a vizsgált igékhez tartozó adatokat tartalmazzák. Az egyes könyvtárakban a következő fájlok találhatók (a fájlok felsorolása a feldolgozási lépéseket követik):
* `*.txt` - a Magyar Nemzeti Szövegtárból [mazsolával](http://corpus.nytud.hu/mazsola/) lekért szűretlen mondatok listája
* `*.tsv` - a duplikátumok és a nem nagy betűvel kezdődő mondatok kiszűrése után maradt mondatok [magyarlánccal](https://rgai.inf.u-szeged.hu/magyarlanc) elemzett változata
* `*.2.xml` - a magyarláncos elemzés xml fájllá alakított változata, az igék leírása kiegészítve az igekötőkapcsolási és kiterjesztett lemma információkkal
* `*.cplist.xml` - a magyarlánc függőségi elemzője alapján megállapított tagmondatleíró fájl: jelölve a tagmondat eleje és vége, a tagmondat fejének fontosabb tulajdonságai, a tagmondatban levő maximális XP-k (bővítmények) fontosabb tulajdonságai
* `*.xlsx` - kézi argumentumszerkezet-egyértelműsítő fájl: 1, 2... az argumentumszerkezeti variáns azonosítója; 0 egyéb, nem kell figyelembe venni
* `*.args2.tsv` - a tagmondatok (igék) mellett megjelenő bővítménytípusok tagmondatonkénti felsorolása (csak a vizsgált ige vizsgált argumentumszerkezeti variánsait tartalmazza, azokból is csak a vizsgált bővítménytípusokat; csak kijelentő módú igék)
* `*.freqs.tsv` - Az argumentumszerekezeti variánsok mellett a bővítmények összesített előfordulási számai, és azok megjelenési gyakoriságai: a tanulmányban ezek az adatok lettek kiértékelve