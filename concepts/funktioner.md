# 4. Funktioner — Navngiven adfærd

Du kender funktioner fra Java som metoder. I JavaScript fungerer de på samme måde: du samler et stykke kode, giver det et navn, og kalder det når du har brug for det. Forskellen er at funktioner i JavaScript er mere fleksible — de kan gemmes i variabler og sendes som argumenter til andre funktioner.

## En funktion er genanvendelig kode

```javascript
function visBesked(tekst) {
    document.querySelector("#besked").textContent = tekst;
}

visBesked("Kladde gemt!");
visBesked("Fejl: prøv igen");
```

I stedet for at skrive den samme DOM-manipulation flere steder, samler du den i en funktion og kalder den med forskelligt input.

## Funktioner kan sendes som argumenter

Det er her JavaScript adskiller sig fra Java. En funktion kan gives som argument til en anden funktion — det gør du allerede med `addEventListener`:

```javascript
function håndterKlik() {
    console.log("klikket!");
}

knap.addEventListener("click", håndterKlik);
```

Her sendes `håndterKlik` som et argument — uden parenteser. Du sender selve funktionen, ikke resultatet af den.

## Returværdier

Ligesom i Java kan funktioner returnere en værdi:

```javascript
function hentKommentar() {
    return document.querySelector("textarea").value;
}

const tekst = hentKommentar();
```

## Vigtigste pointer

- Funktioner navngiver og samler adfærd — brug dem til at undgå gentagelse
- I JavaScript kan funktioner sendes som argumenter til andre funktioner
- Send funktionen uden parenteser når du sender den som argument — parenteser kalder den med det samme