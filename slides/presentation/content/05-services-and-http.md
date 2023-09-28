# 05 Services und HTTP-Requests

--

## Services

- helfen mit Übersichtlichkeit
- haben in der Regel eine spezifische Aufgabe
- Funktionalität unabhängig von GUI im Gegensatz zu Komponenten selbst
- bspw. data fetching, validation etc.

--

## Providing Dependency

Service muss @Injectable decorator besitzen

```typescript
@Injectable()
class HeroService {}
```

--

## Providing Dependency - Komponente

Um den Service in einer Komponente zu verwenden kann er zu den providers im `.ts` hinzugefügt werden

```typescript
@Component({
  selector: "hero-list",
  template: "...",
  providers: [HeroService],
})
class HeroListComponent {}
```

--

## Providing Dependency - Modul

```typescript
@NgModule({
  declarations: [HeroListComponent]
  providers: [HeroService]
})
class HeroListModule {}
```

--

## Providing Dependency - ganze App

```typescript
@Injectable({
  providedIn: "root",
})
class HeroService {}
```

--

## Dependency Injection

- im constructor
- nur jeweils eine Instanz pro Service

```typescript
@Component({ … })
class HeroListComponent {
  constructor(private service: HeroService) {}
}
```

--

## HTTP-Requests

HTTP Requests können mithilfe des HTTP Clients gemacht werden

```typescript [9]
// app.module.ts
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { HttpClientModule } from "@angular/common/http";

@NgModule({
  imports: [
    BrowserModule,
    HttpClientModule,// import after BrowserModule.
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

--

## HTTP-Requests

```typescript
import { Injectable } from "@angular/core";
import { HttpClient } from "@angular/common/http";

@Injectable()
export class MyService {
  constructor(private http: HttpClient) {}

  getData(): Observable<Data> {
    return this.http.get<Data>("your-url.com");
  }
}
```
--

## HTTP-Requests

```typescript
this.myService.getData()
  .subscribe((data: Data) => (this.serviceData = data));
```
Subscription & Observables sind Teil von [RxJS](https://rxjs.dev/)

Note:
wichtig: wenn keine subscription vorhanden ist-> kein request gesendet

--

## Your turn :) --> Übung 5
