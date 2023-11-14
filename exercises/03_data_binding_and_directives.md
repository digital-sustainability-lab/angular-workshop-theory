# 03 - Data binding and Directives

## [3.1 Looping](/slides/presentation/content/03-data-binding-directives.md#structural-directives---ngfor)

Füge den untenstehenden Datensatz als statischen Array im `.ts` der erstellen Overview Kompnenten ein.
Iteriere mit Hilfe von `ngFor` über den Datensatz und erstelle eine `mat-card` mit beliebigem `mat-card-content` (bspw. "Ich bin eine Karte") für jedes Datenobjekt. Der Toggle kann wieder entfernt werden

```typescript
// Beispieldaten
[
  {
    title: "Fancy first blog post",
    description: "Hello world! Here I am!",
    color: "blue",
    class: "special",
    show: true,
  },
  {
    title: "Fancy second blog post",
    description: "Hello world! Here I am!",
    color: "black",
    class: "special",
    show: true,
  },
  {
    title: "Fancy third blog post",
    description: "Hello world! Here I am!",
    color: "green",
    class: "normal",
    show: false,
  },
  {
    title: "Fancy fourth blog post",
    description: "Hello world! Here I am!",
    color: "green",
    class: "normal",
    show: true,
  },
];
```

Tipp: Wenn du den mat-card loop in ein div mit der Klasse `.container` verschiebst und folgendes css in `overview.component.css` einfügst sieht alles ein wenig übersichtlicher aus

```css
mat-card {
  margin: 10px;
  width: 400px;
  height: 400px;
}
.container {
  width: 100%;
  display: flex;
  flex-direction: row;
}
```

## 3.2 [\*ngIf/else](/slides/presentation/content/03-data-binding-directives.md#structural-directives---ngif)

Erstelle eine Kondition dass `mat-card-content` nur angezeigt wird, wenn `show` true ist (Inhalt der mat-card ist nicht relevant)

## 3.3 Styling

Füge die folgenden Angaben in deinem Style Sheet ein.

```css
.normal {
  font-size: 16px;
  font-weight: 400;
  line-height: 28px;
}

.special {
  font-size: 16px;
  font-weight: 400;
  line-height: 28px;
  font-style: oblique;
  text-decoration: underline overline;
}
```

Definiere danach das Styling und die Class der jeweiligen `mat-card` durch die gegebenen style Attribute des Datenobjekts (color respektive class)

---

### Zusatzaufgabe

Versuche anstelle des des Karteninhaltes, die Karte selbst je nach Wert von Show ein- oder auszublenden. Was muss dabei beachtet werden?

Probiere jeder Karte ein `mat-select` hinzuzufügen, mithilfe dessen die gewünschte Schriftfarbe für die Karte ausgewählt werden kann (Hinweis: verwende two-way-binding)
