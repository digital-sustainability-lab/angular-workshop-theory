# Hands-On Workshop Angular

Rowing Sessions Fincons 28.09.23

Aaron Sägesser, Kerrie Stauffer

Digital Sustainability Lab

--

## Programm

- Einführung
- Routing
- Data Binding & Directives
- Parent Child Interaktionen
- Services & HTTP-Requests
- Forms

---

## 01 Getting started

#### Angular im Allgemeinen ist...

- Open Source
- basierend auf Komponenten
- skalierbar
- typescript

Note:
gibt bereits vieles out of the box bspw libraries / features (router, forms, anomations), testing...

--

## Komponenten

- Angular Applikationen sind auf Komponenten aufgebaut
- Jede Komponente beinhaltet
  - Typescript class
  - HTML template
  - styles

--

## Beispiel Komponente

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
  // define behavior
}
```

Note:
Die oben definierte Komponente kann schliesslich via selector (hier `hello-world`) in anderen HTML Templates aufgerufen werden

--

## Beispiel Komponente

```html
<hello-world></hello-world>
```



```html
<hello-world>
  <h2>Hello World</h2>
  <p>This is my first component!</p>
</hello-world>
```
Note:
alle Inhalte, die im Template des `hello-world` Komponenten definiert wurden, werden als children von
`<hello-world></hello-world>` angezeigt sprich:
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
Note:
how to be rendered, can be defined inline or by file path, Syntax {{}} für dynamisches rendering DOM wird
aktualisiert sobald state von component angepasst wird

--

## HTML-Templates

oder als eigene `.html` Datei

```typescript [5,6]
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

Note:
evt. erwähnen dass doctype etc. nicht noch definiert werden muss, wird alles von Angular gehandhabt

--

## Dynamisches DOM Rendering

DOM wird bei Veränderungen des Zustands der Komponente automatisch angepasst

```html
<h2>Hello World</h2>
<p>This is my first component! {{my_var}}</p>
```

Note:
Syntax {{}} für dynamisches rendering DOM wird
  aktualisiert sobald state von component angepasst wird, aber dazu später mehr

--

## Modules

```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';
import { OverviewComponent } from './overview/overview.component';

@NgModule({
  declarations: [AppComponent, OverviewComponent],
  imports: [
    BrowserModule,
  ],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

--

## Angular Material

- Material Design für Angular
- Sammlung vorgefertigter UI Komponenten

--

## Your turn :) --> Übung 1

Übungen & slides findet ihr unter:
https://github.com/digital-sustainability-lab/angular-workshop-theory