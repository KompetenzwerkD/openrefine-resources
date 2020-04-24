### Abgleich von Daten mit Wikidata

Use-Case: Wir haben ein lokales Datenset und wollen überprüfen, ob sich darin enthaltene Informationen von den auf Wikidata eingetragenen Daten unterscheiden.


1. Lade eine Datenset in OpenRefine

![](https://github.com/KompetenzwerkD/openrefine-resources/blob/master/tutorials/wikidata_abgleich/images/openrefine_wikidata1.png)

2. Reconcile das Datenset mit Wikidata
3. Importiere die aktuellen neuen Daten aus Wikidata
4. Erstelle eine Neue Spalte die die alten und neuen Daten vergleicht

```python
try:
    original = row.record.cells["date_of_birth"].value[0].strip()
except:
    original = ""

new = row.record.cells["date of birth"].value[0].strip()

if new != original:
    return new
else:
    return ""
```