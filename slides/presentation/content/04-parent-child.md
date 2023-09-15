## 04 Parent-Child Verhalten

--

## HTML

- Aufruf Child per Tag (Selektor)
- Parameter Übergabe
- \*ngIf für Rendering nach Condition
- \*ngFor für dynamische Darstellung

```html
<app-card
  *ngFor="let card of cards"
  [input]="card.content"
  (outputTrigger)="doSomethingInParent()"
></app-card>
```

--

## Klasse

- Decorators markieren Variable als In-/Output

```typescript
@Input() input: string;
@Output() outputTrigger: EventEmitter<boolean> = new EventEmitter();
```

--

## Life-cycles

- ngOnInit(), ngAfterViewInit(), ngOnDestroy(), ngOnChanges()
