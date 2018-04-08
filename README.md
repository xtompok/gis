# Základy geoinformatiky

[Co se dělalo na cvičeních](prubeh.md)

## Zdroje dat
 * [OpenStreetMap(GeoFabrik)](http://download.geofabrik.de/europe/czech-republic.html)
 * [IPR Praha](http://www.geoportalpraha.cz/cs/opendata)

## Výběr podle atributů
 * `"` - uvozovky - používají se okolo názvu atributu, např. `"ZAS_JMENO"`
 * `'` - apostrofy - používají se okolo řetězců, např. `'xN'`

### Operátory
 * `=`, `<>` - rovnost resp. nerovnost (funguje i na stringy)
 * `<`, `<=`, `>=`, `>` - porovnání
 * `AND`, `OR` - musí být splněny obě strany současně resp. alespoň jedna strana
 * `NOT` - negace následujícího výrazu
 * `LIKE` 
   * pokročilejší výběr textu
   * `%` - zástupný znak za libovolný počet znaků
   * `_` - zástupný znak za jeden jakýkoli znak
   * `"NAZEV" LIKE '_a%'` vybere všechny řetězce, které mají na 2. místě `a`
 * `IS IN`
   * porovnávání s množinou
   * `"LINKA_CISLO" IS IN (1,2,3)` vybere všechny linky, jejichž číslo je 1, 2 nebo 3 
 * `NULL`
   * reprezentuje chybějící hodnotu
   * liší se od `''`
   * `"DATA" IS NULL` vybere všechny řádky s chybějícími daty
   * `"DATA" IS NOT NULL` se hodí pro filtrování řádků s chybějícími daty

## Topologie
 * všechna data musí být v geodatabázi ve stejné `Feature Database`
   * abychom je tam mohli přidat, musí mít všechna data stejný souřadnicový systém
 * nová topologie přes `Catalog -> <najít feature class> -> <pravý klik> -> New -> Topology`
 * vytvořenou topologii najdeme pak v katalogu jako součást `Feature Database`
   * pravým klikem a `Validate` spustíme validaci
 * pokud přidáme topologii přes `Add Data`, přidá se nám vrstva s chybami v topologii

### Práce s topologií
 * správnost se kontroluje pouze při spuštění `Validate`, při editaci nikoli
 * po doběhnutí validace je potřeba
   * zavřít okno, které je na pozadí (tudíž minimalizovat ArcMap, zavřít okno, obnovit ArcMap) 
   * změnit přiblížení, aby se aktualizovala vrstva s chybami
 * v katalogu můžu kliknout na topologii pravým a `Properties` a pak mohu:
   * přidávat / odebírat vrstvy do/z topologie
   * měnit pravidla (je jich málo, viz [cheatsheet](http://help.arcgis.com/en/arcgisdesktop/10.0/help/001t/pdf/topology_rules_poster.pdf) )
 * pokud mám toolbar (`Customize -> Toolbars`) `Topology`, tak mohu dělat pár věcí s topologií
   * nejprve je třeba zapnout editaci vrstvy, která je v topolgii, toolbar se aktivuje
   * topologická editace - hýbu s vrcholem a všechny navázané polygony se mění, ne jen ten, co je nejvýš
   * kontrola chyb - tlačítko vpravo, otevře dialog `Error Inspector` dole, `Search now` najde chyby topologie v aktuální zobrazené části mapy a popíše je
     * pravým klikem na chybu můžu zvolit některé ze (semi-)automatických řešení
 * pokud mám zapnutou editaci některé z vrstev topologie, nelze provést validaci
  
