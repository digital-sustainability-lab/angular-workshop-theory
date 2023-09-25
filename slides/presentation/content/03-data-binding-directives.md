## 03 Data Binding & Directives

--

### Data Binding

- hilft Ansicht aktuell zu halten
- bspw. für Zustand eines Buttons oder Userdaten

--

### Data Binding mit Angular - Interpolation & Attribut

source (`.ts`) -> view (`.html`)

- interpolation

```html
<div>Wert von my_var ist: {{my_var}}</div>
```

- Attribut

```html
<mat-slide-toggle [checked]="isToggleChecked"> Slide me! </mat-slide-toggle>
```

--

### Data Binding mit Angular - Event

source (`.ts`) -> view (`.html`)

Event

```html
<button mat-button (click)="myClickFunctionality()"></button>
```

--

### Data Binding mit Angular - Two-way binding

source (`.ts`) <-> view (`.html`)

```html
<eg-element [(target)]="expression"></eg-element>
```

--

### Directives

- Klassen
- helfen das Verhalten von Elementen zu definieren
- Angular besitzt built-in directives
- attribute vs. structural directives

--

### Structural Directives

- NgIf
- NgFor
- NgSwitch

--

### Structural Directives - NgIf

- Element wird hinzugefügt / entfernt

```html
<div *ngIf="currentCustomer">Hello, {{currentCustomer.name}}</div>
```

- else

```html
<div *ngIf="currentCustomer; else noCustomer">
  Hello, {{currentCustomer.name}}
</div>
<ng-template #noCustomer>No customer found</ng-template>
```

--

### Structural Directives - NgFor

- Elemente auflisten (loop)

```html
<div *ngFor="let item of items">{{item.name}}</div>
```

--

### Structural Directives - NgSwitch

- Zeigt eines von mehreren Elementen an, basierend auf der switch Kondition

```html
<div [ngSwitch]="currentItem.color">
  <app-red-item *ngSwitchCase="'red'" [item]="currentItem"></app-red-item>
  <app-green-item *ngSwitchCase="'green'" [item]="currentItem"></app-green-item>
  <!-- . . . -->
  <app-unknown-item *ngSwitchDefault [item]="currentItem"></app-unknown-item>
</div>
```

--

### Attribute Directives

- NgClass
- NgStyle
- NgModel (erst relevant für Forms)

--

### Attribute Directives - NgClass

Dynamische Definition von Klassen

```html
<div [ngClass]="isSpecial ? 'special' : ''">This div is special</div>
```

--

### Attribute Directives - NgStyle

Dynamische Definition von Style Attributen

```html
<div [ngStyle]="{'max-width.px': widthExp}">some content</div>
```

--

## Your turn :) --> Übung 3
