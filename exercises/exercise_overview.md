# 1 Getting started (0.5h)

- angular aufsetzen
  - routing aktivieren
  - standard template löschen
- angular material importieren
- componente erstellen
  - component referenz in html erstellen
- string variable definieren
- in html anzeigen ({{}})
- evtl. show/hide mit \*ngIf
  - mat-toggle nutzen
- ng build und node serving nutzen
  - reminder in späteren exercises

# 2 Routing (0.75h) - A

- neue route für component
- wildcard route mit redirect erstellen
- 2 neue component
  - für navbar erstellen
  - weitere anzeige
- router-outlet nutzen für navbar
  - routerlink benutzen
  - zusatz: routerlinkactive nutzen
- link in einer component zu anderer component mit variable mitgeben
- show/this in nav

# 3 Data binding & directive (0.5h)

- loop für mat-select mit welchen styling verändert weden kann
  (evlt. stylesheet für transition)
- zusatzaufgabe: passende mat-icons, two-way binding

# 4 Parent & Child Relation (0.75h) - A

- neue component erstellen für card (mit blog-beiträgen, galerie, o.ä.)
- loop in der parent componente für card erstellen
- Output() nutzen sobald aus detail ansicht oder "read" / "not read" ngStyle (ausgegraut wenn read)
- zusatz: ngOnInit()

# 5 Services & Backend Communication (0.5h)

- service erstellen
- in component aufrufen
- httpClient importieren
- get request machen (mat-card data von backend fetchen)
- zusatz: delet request um cards zu löschen

# 6 Forms (0.75h) - A

- statisches formular erstellen (neue blogs)
- daten mit post request speichern
- zusatz:
  - neue component für update erstellen
  - formulardaten laden
  - put request an backend bei update

# 7 Guards & Authentication (0.5h)

- entweder login component oder login button (oauth)
- guard welcher login state prüft
- zusatz: role guard

- authorization über github as oauth provider
