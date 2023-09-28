# 04 Parent-Child Verhalten

--

## Was sind Parent & Child?

- **Parent**: Komponente welche andere Komponente aufruft bzw. sich aus diesen aufbaut
- **Child**: Sub-Komponente welche durch Parent Komponente (ein/mehrhmalig) aufgerufen wird
- **Beispiel**: Parent Komponente ruft Header, Home-View und Footer Komponenten als Children auf

```html
<app-header></app-header>
<main>
  <app-home-view></app-home-view>
</main>
<app-footer></app-footer>
```

Note:
Parent ruft Child mit Selector auf.

--

## HTML in Parent

- Aufruf Child per Selektor
- Parameter Übergabe (an Attribut)
- `*ngIf` für Rendering nach Condition
- `*ngFor` für dynamische Darstellung

```html
<app-card
  *ngFor="let card of cards"
  [input]="card.content"
  (outputTrigger)="doSomethingInParent()"
></app-card>
```

Note:
card.content wird hier der app-card als input übergeben, bei trigger des "outputTrigger" wird doSomethingInParent() aufgerufen

--

## TS-File in Child

Decorators markieren Variablen als In-/Output

```typescript
@Input() input: string;
@Output() output: EventEmitter<boolean> = new EventEmitter();

triggerParentToAction() {
  this.output.emit(true);
}
```

Note:
bei Aufruf der "triggerParentToAction" Methode im Child wird ein Event emitted, welches im Parent wiederum eine Action triggered. Es können auch komplexere Daten als Event übergeben werden anstelle des Boolean.

--

## Lifecycle hooks

- Methoden, welche zu einem/mehreren Zeitpunkt(en) durch Angular aufgerufen werden
- nachfolgend wichtigste Methoden...

--

## ngOnInit()

- wird beim Initialisieren einer Komponente einmalig ausgeführt
- Use Case: Initialisieren von Daten (Komponenten Inputs) welche in der Komponente genutzt werden

--

## ngOnChanges()

- reagiert auf Änderungen der Daten welche in der Komponente verwendet werden
- Use Case: Berechnungen von Werten auf Basis von Komponenten Inputs, welche bei Veränderung der Inputs auch aktualisiert werden sollen

--

## ngAfterViewInit()

- wird nach der Initialisierung des DOM Elemente (HTML Elemente) ausgeführt
- Use Case: wenn DOM Elemente referenziert werden sollen

--

## ngOnDestroy()

- wird aufgerufen, nachdem eine Komponente aus dem UI entfernt wurde
- Use Case: für clean up (v.a. unsubscription von Observables), damit unbenutzte Variablen die App nicht unnötig verlangsamen

--

... weitere, siehe [Angular Doku](https://angular.io/guide/lifecycle-hooks)

--

## Your turn :) --> Übung 4
