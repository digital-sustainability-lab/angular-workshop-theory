# 01 - Getting Started

## 1.1 App aufsetzen

In diesem ersten Schritt geht es darum den Angular CLI zu installieren und ein neues Projekt aufzusetzen.
Wähle dabei Routing yes (erleichtert spätere Übungen) und das Stylesheet deiner Wahl (üblicherweise CSS/SCSS)
Benutze dazu folgende commands:

```bash
npm install -g @angular/cli

# generiere neue angular app struktur
# da wir in diesem tutorial mit dem app.module.ts file
# arbeiten, benötigen wir die zusätzlichen konfigurationen
# welche mit --no-standalone --routing und --ssr=false
# festgelegt werden
ng new my-app --no-standalone --routing --ssr=false

# teste nun ob die Applikation läuft, es sollte automatisch ein Browserfenster geöffnet werden
# falls nicht öffne http://localhost:4200
cd my-app
ng serve --open
```

siehe auch die offizielle Angular Dokumentation [hier](https://angular.io/guide/setup-local). Die zusätz

## 1.2 Template mit eigenem Komponenten ersetzen

In `app.component.html` befindet sich ein Platzhalter Template lösche dieses.
Erstelle danach eine eigene Komponente namens `overview` (manuell oder via Angular Cli), die du im `app.component.html` einfügst (Hinweis: `router-outlet` kann für den Moment noch ignoriert werden)

## 1.3 Zustand des DOM dynamisch modifizieren & Angular Material

Installiere Angular Material in deiner App (Theme frei wählbar)

```bash
ng add @angular/material
```

Füge nun ein `slide-toggle` in das Template deiner neuen Komponente ein. Dazu musst du den Material Component im App Module registrieren, siehe auch unter `display a component` in der [offiziellen Dokumentation](https://material.angular.io/guide/getting-started)

Versuche das Label des toggles so zu ändern, dass es dem Wert einer im `.ts` definierten Variabel entspricht. Dazu kann das `[checked]` Attribut im html verwendet werden, welches jeweils einen `Boolean` zurückgibt, basierend auf dem State des Toggles. Dieser Wert kann danach einer frei wählbaren Variable zugewiesen werden, welche im `.ts` File definiert ist und jeweils aktualisiert wird, sobald das Toggle verwändert wird. Näheres zu diesem sogenanten "data binding" werden wir im Kapitel 3 behandeln. Nutze folgende Snippets, um dem Toggle die Funktionalität zu geben.

<details>
  <summary>Test expand...</summary>
  It works :D
</details>

Im `.html`:
```html
<mat-slide-toggle [checked]="checked" color="warning" labelPosition="before">{{
  label
}}</mat-slide-toggle>
```

Im `.component.ts`:
```typescript
checked: boolean = true;
```


Nun sollte deine App also anstelle des Default Templates eine neue Komponente anzeigen. Innerhalb dieser Komponente sollte ein `mat-slide-toggle` angezeigt werden, dessen Label im `.ts` definiert ist.

---

### Zusatzaufgabe

Definiere den Default Zustand und Farbe des Toggles, versuche sonst auch noch die Position des Labels zu verändern (siehe [API](https://material.angular.io/components/slide-toggle/api) des slide toggles für mehr Informationen)
