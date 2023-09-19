## 06 Angular Forms

--

## Wie werden Formulare genutzt?

- 2 Varianten
  - reactive
  - template-driven

--

## Reactive Forms

--

## Template-driven Forms

--

## ngModel Directive

- wird standalone oder innerhalb eines grösseren Formulares genutzt
- bindet die Werte von HTML control-Elementen (input, select, text-area) an die Daten des .ts Files der entsprechendend Komponente
- kann mit one- oder two-way-binding genutzt werden
  - one-way: `[ngModel]` Änderung Model Input (.ts) -> Änderung in View (.html)
  - two-way: `[(ngModel)]` automatische Synchronisation des Wertes im UI mit dem domain model (zugrunde liegenden Daten)

--

## Static vs. dynamic Forms

- wenn das Formular und dessen Attribute von vornherein bekannt -> static
- wenn unbekannt bzw. veränderbar -> dynamic
  - FormBuilder

--

## FormGroup vs. FormArray

- FormGroup:
  - Formular als Object
  - Verschachtelung (FormGroup of FormGroups) möglich
  - Use Case: v.a. wenn Anzahl Felder bekannt
- FormArray:
  - Formular als Array
  - Verschachtelung (FormArray of FormGroups) möglich
  - Use Case: v.a. wenn Anzahl Felder unbekannt

--

## Beispiel I: einzelnes Control-Element

```html
<input [(ngModel)]="name" #ctrl="ngModel" required />

<p>Value: {{ name }}</p>
<p>Valid: {{ ctrl.valid }}</p>

<button (click)="setValue()">Set value</button>
```

```typescript
  name: string = '';

  setValue() {
    this.name = 'Nancy';
  }
```

## Beispiel II: statisches Formular

```html
<form #myForm="ngForm" (ngSubmit)="onSubmit(myForm)">
  <input name="first" ngModel required #first="ngModel" />
  <input name="last" ngModel />
  <button>Submit</button>
</form>

<p>First name value: {{ first.value }}</p>
<p>First name valid: {{ first.valid }}</p>
<p>Form value: {{ f.value | json }}</p>
<p>Form valid: {{ f.valid }}</p>
```

```typescript
  onSubmit(f: NgForm) {
    if (f.valid) {
        return this.dataService.storeInput(f.value)
    }
  }
```

[Quelle](https://angular.io/api/forms/NgModel)

--

## Your turn :) --> Übung 6
