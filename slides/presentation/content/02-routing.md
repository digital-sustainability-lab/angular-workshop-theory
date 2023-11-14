# 02 Angular Routing

--

## Routing Module

- zuständig für das Verhalten der Routes
  - Mapping der Pfade auf die Komponenten (und Guards)
  - Redirects
  - Wildcard `**` und URL Parameter `:parameterName`

--

## 2.1 Beispiel Routing Module

```typescript
const routes: Routes = [
  { path: 'default-route', component: OverviewComponent },
  { path: 'second-route/:id', component: DetailComponent },
  { path: '**', redirectTo: 'default-route' },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

Note:
Oben Routes definiert, dem RouterModule mit .forRoot() zugewiesen

--

## 2.2 Router Outlet

- stellt die im Routing Module zugewiesene Komponente des aktiven Route Pfades dar
- wird im HTML File der App Komponente

```html
<router-outlet></router-outlet>
```

--

## 2.3 Arten der Navigation...

--

### ...über RouterLink in HTML Files

```html
<a
  routerLink="/navigate/here"
  routerLinkActive="['active','other-css-class']"
></a>
```

```html
<button
  [routerLink]="'/navigate/here'"
  routerLinkActive="['active','other-css-class']"
></button>
```

--

### ...über Angular Router in Methoden in `.ts` Files der Komponenten

```html
<button (click)="navigateWithCustomBehavior(id)">
  navigate by id
</button>
```

```typescript
constructor(private router: Router) {}

navigateWithCustomBehavior(id: number) {
    // custom logic...
    this.router.navigate([`navigate/by/${id}`])
}
```

--

## Abrufen von URL Paramentern

mit ActivatedRoute

```typescript
id: string;
constructor(private route: ActivatedRoute) {
  this.id = this.route.snapshot.paramMap.get("id");
}

```

--

## Your turn :) --> Übung 2
