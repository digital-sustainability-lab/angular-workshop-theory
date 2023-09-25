# 03 - Data binding and Directives

## 3.1 Looping

Füge den untenstehenden Datensatz als statischen Array im `.ts` der erstellen Overview Kompnenten ein.
Iteriere mit Hilfe von `ngFor` über den Datensatz und erstelle eine `mat-card` für jedes Datenobjekt

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

## 3.2 \*ngIf/else

Erstelle ein div innerhalb des loops der angezeigt wird, wenn `show` true ist (Inhalt des divs kann fri definiert werden, bspw. "ich werde ngezeigt")

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

Two-way binding mit mat-select????
