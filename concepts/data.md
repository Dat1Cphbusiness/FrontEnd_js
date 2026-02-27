# 3. Data og State — Tilstand i en applikation

Alle interaktive applikationer har en tilstand — en beskrivelse af hvordan tingene ser ud lige nu. Når noget ændrer sig, ændrer tilstanden sig, og brugergrænsefladen bør afspejle det.

## Hvad er state?

Tænk på en indkøbskurv. Den har en tilstand: hvilke varer er i kurven, og hvor mange? Når brugeren tilføjer en vare, ændres tilstanden, og siden opdateres.

I JavaScript gemmer vi tilstand i variabler:

```javascript
let antalVarer = 0;

document.querySelector("#tilfoej").addEventListener("click", () => {
    antalVarer++;
    document.querySelector("#antal").textContent = antalVarer;
});
```

Her er `antalVarer` applikationens tilstand. Eventen ændrer den, og DOM'en opdateres til at vise den nye værdi.

## Den grundlæggende løkke

De fleste interaktive apps følger samme mønster:

```
Bruger gør noget → State ændres → UI opdateres
```

Det er den løkke du skal have i hovedet når du læser eller skriver JavaScript.

## State kan også komme udefra

State behøver ikke kun at komme fra brugerinteraktion. Den kan også komme fra en server — f.eks. en liste af køreture hentet fra en database. 
Men princippet er det samme: data gemmes i variabler, og UI'en viser hvad variablerne indeholder.

## Vigtigste pointer

- State er applikationens hukommelse om hvordan tingene ser ud lige nu
- Når state ændres, skal UI'en opdateres manuelt i vanilla JavaScript
- Forstår du state-begrebet, forstår du logikken bag næsten al frontend-kode

**Læs mere**  
[datatyper i javaScript](https://www.w3schools.com/js/js_datatypes.asp)  
[variable i javaScript](https://www.w3schools.com/js/js_variables.asp)  
[array i javaScript](https://www.w3schools.com/js/js_arrays.asp)  
