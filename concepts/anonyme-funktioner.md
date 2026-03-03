# Anonyme funktioner

Når du kalder en funktion, sender du normalt værdier som argumenter:

```javascript
console.log("hello");
```

Men i JavaScript er funktioner også værdier – så du kan sagtens sende en funktion som argument til en anden funktion.

## Navngiven funktion som argument

```javascript
function sigHej() {
    console.log("hej");
}

setTimeout(sigHej, 1000);
```

Her definerer vi funktionen et sted, og sender dens navn som argument til `setTimeout`.

## Anonym funktion som argument

```javascript
setTimeout(function() {
    console.log("hej");
}, 1000);
```

De to eksempler gør **præcis det samme**. Den anonyme version er bare en genvej – vi springer navngivningen over fordi funktionen kun bruges ét sted, og vi aldrig får brug for at referere til den igen.

## Med arrow syntax

I moderne JavaScript skrives anonyme funktioner typisk med arrow syntax:

```javascript
setTimeout(() => {
    console.log("hej");
}, 1000);
```

Arrow syntax er kortere og er blevet standarden i moderne JavaScript.

## Hvornår bruger man anonyme funktioner?

Anonyme funktioner er særligt nyttige ved **event listeners**, hvor vi kun har brug for funktionen ét sted:

```javascript
button.addEventListener('click', function() {
    console.log("knappen blev klikket");
});

// Eller med arrow syntax:
button.addEventListener('click', () => {
    console.log("knappen blev klikket");
});
```

Hvis den samme logik skulle bruges flere steder, ville det give mere mening at give funktionen et navn og referere til det.
