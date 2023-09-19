# 01 - Getting Started

## 1.1 App aufsetzen

In diesem ersten Schritt geht es darum den Angular CLI zu installieren und ein neues Projekt aufzusetzen.
Wähle dabei Routing yes (erleichtert spätere Übungen) und das Stylesheet deiner Wahl (üblicherweise CSS/SCSS)
Benutze dazu folgende commands:

```bash
npm install -g @angular/cli

ng new my-app

# teste nun ob die Applikation läuft mit, es sollte automatisch ein Browserfenster geöffnet werden
# falls nicht öffne http://localhost:4200
cd my-app
ng serve --open
```

siehe auch die offizielle Angular Dokumentation [hier](https://angular.io/guide/setup-local)

## 1.2 Template mit eigenem Komponenten ersetzen

Im `app.component.html` befindet sich ein Platzhalter template lösche dieses.
Erstelle danach einen eigenen Komponenten, den du im `app.component.html` einfügst (hint: `router-outlet` kann für den Moment noch ignoriert werden)

## 1.3 Zustand des DOM dynamisch modifizieren & Angular Material

Installiere Angular Material in deiner App (welches theme gewählt wird spielt keine Rolle)

```bash
ng add @angular/material
```

Füge nun ein slide-toggle in das template deines neuen Komponenten ein. Dazu musst du den Material Component im App Module registrieren, siehe auch unter `display a component` in der [offiziellen Dokumentation](https://material.angular.io/guide/getting-started)

Wenn dein Toggle nun angezeigt wird, versuche den angezeigten String je nach Toggle Zustand anzupassen. Bspw. wenn der Toggle an ist zeigt es an `true` und wenn er aus ist wird `false` angezeigt.

Nun sollte deine App anstelle des Templates einen neuen Komponenten anzeigen. Innerhalb dieses Komponenten sollte ein mat-slide-toggle angezeigt werden, dessen Zustand den Zustand des DOM beeinflusst (angezeigter string)

---

### Zusatzaufgabe

Definiere default Zustand und Farbe des Toggles, versuche sonst auch noch die Position des Labels zu verändern (siehe [API](https://material.angular.io/components/slide-toggle/api) des slide toggles für mehr Informationen)
