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

