# 06 Angular Forms

--

## Wie werden Formulare genutzt?

- 2 Varianten
  - reactive
  - template-driven

--

## Template-driven Forms

- Logik in Template (HTML File)
- geeignet für einzelne Formular Felder

--

## Reactive Forms

- Logik in `.ts` File
- geeignet für
  - grössere Formulare
  - dynamische Formulare
- besser testbar

--

## ngModel Directive

- standalone oder innerhalb eines grösseren Formulares
- bindet Werte von HTML control-Elementen (`input`, `select`, `text-area`) an Daten des `.ts` Files
- one- oder two-way-binding
  - _one-way_: `[ngModel]` Änderung Model Input (.ts) -> Änderung in View (.html)
  - _two-way_: `[(ngModel)]` automatische Synchronisation Wert im UI mit domain model

--

## Static vs. dynamic Forms

- Formular & Attribute von vornherein bekannt -> static
- unbekannt bzw. veränderbar -> dynamic
  - `FormBuilder` um `FormGroup` bzw. `FormArray` zu erstellen/verändern

Note:
Bei Erstellung dynamischer Formulare ist die Verwendung des FormBuilders hilfreich.

--

## FormGroup vs. FormArray

- **FormGroup**:
  - Formular als Object
  - Verschachtelung (`FormGroup` of `FormGroups`) möglich
  - _Use Case_: v.a. wenn Anzahl Felder bekannt
- **FormArray**:
  - Formular als Array
  - Verschachtelung (`FormArray` of `FormGroups`) möglich
  - _Use Case_: v.a. wenn Anzahl Felder unbekannt

--

## Beispiel I: einzelnes Control-Element

(Template-driven)

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

--

## Beispiel II: statisches Formular

(Template-driven)

```html
<form #myForm="ngForm" (ngSubmit)="onSubmit(myForm)">
  <input name="first" type="text" ngModel
    required #first="ngModel" />
  <input name="last" type="text" ngModel />
  <button>Submit</button>
</form>
```

```typescript
  onSubmit(f: NgForm) {
    if (f.valid) {
        return this.dataService.storeInput(f.value)
    }
  }
```

--

## Beispiel II: statisches Formular

(reactive)

```html
<form [formGroup]="myForm" (ngSubmit)="onSubmit()">
  <input formControlName="first" type="text" />
  <input formControlName="last" type="text" />
  <button type="submit">Submit</button>
</form>
```

```typescript
  myForm: FormGroup;
  initForm() {
      this.myForm = new FormGroup({
        'first': new FormControl(null, Validators.required),
        'last': new FormControl(null)
       })
  }
  onSubmit() {
    if (this.myForm.valid) {
        return this.dataService.storeInput(this.myForm.value)
    }
  }
```

--

## Your turn :) --> Übung 6
