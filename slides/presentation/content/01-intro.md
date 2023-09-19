# Hands-on Angular Workshop

Rowing Sessions Fincon 28.09.23

Aaron Sägesser, Kerrie Stauffer

Digital Sustainability Lab

--

## Programm

## 💻️ .. 🤔 .. ⭐

---

## 01 Getting started

#### Angular im Allgemeinen ist...

- open source
- man hat schnell mal was
- component based
- scalabe
- typescript based
- gibt bereits viele libraries /features (router, forms, anomations), testing...

--

## Components

- Angular Applikationen sind auf Komponenten aufgebaut
- Jede Komponente beinhaltet
  - Typescript class
  - HTML template
  - styles

--

## Beispiel Komponent

```typescript [1-12|4]
import { Component } from "@angular/core";

@Component({
  selector: "hello-world",
  template: `
    <h2>Hello World</h2>
    <p>This is my first component!</p>
  `,
})
export class HelloWorldComponent {
  // The code in this class drives the component's behavior.
}
```

Der oben definierte Komponent kann schliesslich via selector (`hello-world`) in anderen HTML templates aufgerufen werden

--

## Beispiel Komponent

```html
<hello-world></hello-world>
```

<!-- alle Inhalte, die im Template des `hello-world` Komponenten definiert wurden, werden als children von
`<hello-world></hello-world>` angezeigt sprich: -->

```html
<hello-world>
  <h2>Hello World</h2>
  <p>This is my first component!</p>
</hello-world>
```

--

## HTML-Templates

Entweder direkt im `.ts` definiert

```typescript [5-8]
import { Component } from "@angular/core";

@Component({
  selector: "hello-world",
  template: `
    <h2>Hello World</h2>
    <p>This is my first component!</p>
  `,
})
export class HelloWorldComponent {
  // define behavior
}
```

<!-- how to be rendered, can be defined inline or by file path, Syntax {{}} für dynamisches rendering DOM wird
aktualisiert sobald state von component angepasst wird -->

--

## HTML-Templates

oder als eigene `.html` Datei

```typescript [5]
import { Component } from "@angular/core";

@Component({
  selector: "hello-world",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.css"],
})
export class HelloWorldComponent {
  //define behavior
}
```

--

## Dynamisches DOM Rendering

DOM wird Veränderungen des component state automatisch angepasst

```html
<h2>Hello World</h2>
<p>This is my first component! {{my_var}}</p>
```

  <!-- Syntax {{}} für dynamisches rendering DOM wird
  aktualisiert sobald state von component angepasst wird -->

--

## Angular Material

- Material Design für Angular
- Vorgefertigte Komponenten

--

## Your turn :) --> Übung 1
