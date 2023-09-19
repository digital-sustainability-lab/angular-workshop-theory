# 05 Service und HTTP-Requests

--

## Services

- helfen mit Übersichtlichkeit
- haben in der Regel eine spezifische Aufgabe
- Funktionalität unabhängig von DOM (?) im Gegensatz zu Komponenten selbst
- bspw. data fetching, validation etc.

--

## Dependency Injection

- Service muss @Injectable decorator besitzen
- Registration in Modul ??

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

## Providing Dependency ????

- Service muss @Injectable decorator besitzen

```typescript
@Injectable()
class HeroService {}
```

- in Komponenten
- Bei jeder Instanierung des Komponenten wird ein neuer Service erstellt

--

## HTTP-Requests

Observables? https://angular.io/guide/observables
https://angular.io/guide/http-server-communication
--

## Your turn :) --> Übung 5
