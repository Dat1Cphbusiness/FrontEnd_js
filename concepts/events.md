# 2. Events — Hændelsesdrevet programmering

I Java skriver du ofte programmer der kører fra top til bund. JavaScript i browseren fungerer anderledes — kode kører **i reaktion på noget**. Det kalder vi hændelsesdrevet programmering.

## Hvad er en event?

En event er noget der sker i browseren — brugeren klikker, siden indlæses, en tekstboks ændres. JavaScript kan lytte efter disse hændelser og reagere på dem.

Du kender princippet fra Java: tænk på det som en metode der kaldes automatisk når noget sker — i stedet for at du kalder den selv.

## Tilføj en event listener

```javascript
const knap = document.querySelector("#gem-knap");

knap.addEventListener("click", () => {
    console.log("knappen blev klikket");
});
```

`addEventListener` tager to argumenter: hvilken event der lyttes efter, og hvilken funktion der skal køre når den sker.

## Almindelige events

| Event | Hvornår |
|-------|---------|
| `click` | Brugeren klikker på et element |
| `DOMContentLoaded` | Siden er færdig med at indlæse |
| `input` | Tekst i et felt ændres |
| `submit` | En formular indsendes |

## Vigtigste pointer

- JavaScript i browseren er hændelsesdrevet — kode venter og reagerer
- Du bestemmer hvilke events der lyttes efter og hvad der sker
- Funktionen der gives til `addEventListener` kaldes først når eventen sker — ikke med det samme

[læs mere om Events](https://www.w3schools.com/js/js_events.asp) 