# JavaScript Opgaver

---

## 0. Opsætning

### Opgave 0.1 — Forbind JavaScript til HTML

Opret to filer: `index.html` og `js/script.js`. Forbind dem korrekt med et `<script>`-tag. I script-filen, skriv en linje der udskriver `"script indlæst"` i konsollen. Åbn siden i browseren og bekræft at beskeden vises i konsollen.

<details>
<summary>Hint</summary>

Brug `<script src="..." defer></script>` i `<head>`. `defer` sikrer at scriptet køres efter HTML er indlæst.

</details>

<details>
<summary>Løsning</summary>

```html
<head>
  <script src="js/script.js" defer></script>
</head>
```

```javascript
console.log("script indlæst");
```

</details>

---

### Opgave 0.2 — Find fejlen

Følgende HTML indlæser ikke scriptet korrekt. Find og ret fejlen.

```html
<head>
  <link rel="javascript" href="js/script.js">
</head>
```

<details>
<summary>Hint</summary>

`<link>` bruges til CSS. JavaScript indlæses med et andet tag.

</details>

<details>
<summary>Løsning</summary>

```html
<head>
  <script src="js/script.js" defer></script>
</head>
```

</details>

---

I det følgende kan du skrive javascript koden direkte i din script-fil. defer i dit <script>-tag sørger for at den kører efter siden er indlæst.

## 1. DOM — Document Object Model

### Opgave 1.1 — Find og vis

Du har denne HTML:

```html
<p id="besked">Hej verden</p>
```

Skriv JavaScript der henter elementet med id `besked` og udskriver dets tekstindhold i konsollen.

<details>
<summary>Hint</summary>

`document.querySelector()` kan finde et element via dets id — brug `#` foran id-navnet, ligesom i CSS.

</details>

<details>
<summary>Løsning</summary>

```javascript
const besked = document.querySelector("#besked");
console.log(besked.textContent);
```

</details>

---

### Opgave 1.2 — Skift indhold

Du har denne HTML:

```html
<h1 id="titel">Velkommen</h1>
```

Skriv JavaScript der ændrer tekstindholdet til `"Hej fra JavaScript"`.

<details>
<summary>Hint</summary>

Brug `.textContent` til at læse og skrive tekst i et element.

</details>

<details>
<summary>Løsning</summary>

```javascript
const titel = document.querySelector("#titel");
titel.textContent = "Hej fra JavaScript";
```

</details>

---

### Opgave 1.3 — Skift stil

Udvid opgave 1.2 så titlen også får farven rød når siden indlæses.

<details>
<summary>Hint</summary>

Brug `.style.color` på elementet.

</details>

<details>
<summary>Løsning</summary>

```javascript
const titel = document.querySelector("#titel");
titel.textContent = "Hej fra JavaScript";
titel.style.color = "red";
```

</details>

---

## 2. Events — Hændelsesdrevet programmering

### Opgave 2.1 — Klik på en knap

Du har denne HTML:

```html
<button id="klik-knap">Klik mig</button>
```

Skriv JavaScript der udskriver `"knappen blev klikket"` i konsollen når brugeren klikker på knappen.

<details>
<summary>Hint</summary>

Brug `addEventListener("click", ...)` på elementet.

</details>

<details>
<summary>Løsning</summary>

```javascript
const knap = document.querySelector("#klik-knap");
knap.addEventListener("click", () => {
    console.log("knappen blev klikket");
});
```

</details>

---

### Opgave 2.2 — Skift tekst ved klik

Du har denne HTML:

```html
<p id="status">Ikke klikket</p>
<button id="skift-knap">Skift</button>
```

Skriv JavaScript der ændrer teksten i `#status` til `"Klikket!"` når brugeren klikker på knappen.

<details>
<summary>Hint</summary>

Kombinér `addEventListener` med `textContent` fra opgave 1.2.

</details>

<details>
<summary>Løsning</summary>

```javascript
const knap = document.querySelector("#skift-knap");
const status = document.querySelector("#status");

knap.addEventListener("click", () => {
    status.textContent = "Klikket!";
});
```

</details>

---

### Opgave 2.3 — Reagér på input

Du har denne HTML:

```html
<input type="text" id="navn-felt">
<p id="hilsen"></p>
```

Skriv JavaScript der opdaterer `#hilsen` med teksten `"Hej, [navn]!"` mens brugeren skriver i feltet.

<details>
<summary>Hint</summary>

Brug eventet `input` på tekstfeltet. Hent værdien med `.value`.

</details>

<details>
<summary>Løsning</summary>

```javascript
const felt = document.querySelector("#navn-felt");
const hilsen = document.querySelector("#hilsen");

felt.addEventListener("input", () => {
    hilsen.textContent = "Hej, " + felt.value + "!";
});
```

</details>

---

## 3. Data og State — Tilstand i en applikation

### Opgave 3.1 — Tæller

Du har denne HTML:

```html
<p id="antal">0</p>
<button id="plus">+1</button>
```

Skriv JavaScript der holder styr på et tal og øger det med 1 hver gang brugeren klikker på knappen. Siden skal vise det opdaterede tal.

<details>
<summary>Hint</summary>

Gem tallet i en variabel med `let`. Opdatér variablen i event listeneren, og opdatér derefter DOM'en.

</details>

<details>
<summary>Løsning</summary>

```javascript
let antal = 0;
const antalEl = document.querySelector("#antal");
const knap = document.querySelector("#plus");

knap.addEventListener("click", () => {
    antal++;
    antalEl.textContent = antal;
});
```

</details>

---

### Opgave 3.2 — Gem og vis input

Du har denne HTML:

```html
<input type="text" id="kommentar-felt">
<button id="gem-knap">Gem</button>
<p id="gemt-kommentar"></p>
```

Skriv JavaScript der gemmer værdien fra inputfeltet i en variabel når brugeren klikker "Gem", og viser den i `#gemt-kommentar`.

<details>
<summary>Hint</summary>

Hent værdien med `.value` inde i event listeneren — ikke udenfor. Ellers læses værdien kun én gang når siden indlæses.

</details>

<details>
<summary>Løsning</summary>

```javascript
const felt = document.querySelector("#kommentar-felt");
const knap = document.querySelector("#gem-knap");
const visning = document.querySelector("#gemt-kommentar");

knap.addEventListener("click", () => {
    const kommentar = felt.value;
    visning.textContent = kommentar;
});
```

</details>

---

### Opgave 3.3 — Liste af kommentarer

Udvid opgave 3.2 så hver gemt kommentar tilføjes til en liste i stedet for at erstatte den forrige. Brug et array til at holde styr på alle kommentarer.

```html
<input type="text" id="kommentar-felt">
<button id="gem-knap">Gem</button>
<ul id="kommentar-liste"></ul>
```

<details>
<summary>Hint</summary>

Gem kommentarerne i et array med `push()`. Byg listen op ved at sætte `innerHTML` på `<ul>` — spørg AI om hvordan du laver en `<li>` for hvert element i et array.

</details>

<details>
<summary>Løsning</summary>

```javascript
const felt = document.querySelector("#kommentar-felt");
const knap = document.querySelector("#gem-knap");
const liste = document.querySelector("#kommentar-liste");
const kommentarer = [];

knap.addEventListener("click", () => {
    kommentarer.push(felt.value);
    felt.value = "";
    liste.innerHTML = kommentarer
        .map(k => `<li>${k}</li>`)
        .join("");
});
```

</details>

---

## 4. Funktioner — Navngiven adfærd

### Opgave 4.1 — Udpak til en funktion

Tag din løsning fra opgave 3.2 og flyt logikken ind i en navngiven funktion kaldet `gemKommentar()`. Kald funktionen fra event listeneren.

<details>
<summary>Hint</summary>

Erstat den anonyme arrow function i `addEventListener` med et kald til `gemKommentar`. Husk: send funktionen uden parenteser hvis du sender den som argument.

</details>

<details>
<summary>Løsning</summary>

```javascript
const felt = document.querySelector("#kommentar-felt");
const visning = document.querySelector("#gemt-kommentar");

function gemKommentar() {
    visning.textContent = felt.value;
}

document.querySelector("#gem-knap").addEventListener("click", gemKommentar);
```

</details>

---

### Opgave 4.2 — Funktion med returværdi

Skriv en funktion `hentKommentar()` der returnerer den aktuelle værdi fra et `<textarea>` element. Kald funktionen og udskriv resultatet i konsollen.

```html
<textarea id="tekst-felt"></textarea>
<button id="hent-knap">Hent</button>
```

<details>
<summary>Hint</summary>

Brug `return` i funktionen. Gem returværdien i en variabel når du kalder den.

</details>

<details>
<summary>Løsning</summary>

```javascript
function hentKommentar() {
    return document.querySelector("#tekst-felt").value;
}

document.querySelector("#hent-knap").addEventListener("click", () => {
    const tekst = hentKommentar();
    console.log(tekst);
});
```

</details>

---

### Opgave 4.3 — Funktion med parameter

Skriv en funktion `visBesked(tekst)` der sætter tekstindholdet i et element med id `#besked`. Kald funktionen to steder i din kode med forskelligt input.

```html
<p id="besked"></p>
<button id="knap-1">Besked 1</button>
<button id="knap-2">Besked 2</button>
```

<details>
<summary>Hint</summary>

Funktionen tager `tekst` som parameter og bruger den til at sætte `.textContent`. Kald den fra to forskellige event listeners.

</details>

<details>
<summary>Løsning</summary>

```javascript
function visBesked(tekst) {
    document.querySelector("#besked").textContent = tekst;
}

document.querySelector("#knap-1").addEventListener("click", () => {
    visBesked("Du klikkede knap 1");
});

document.querySelector("#knap-2").addEventListener("click", () => {
    visBesked("Du klikkede knap 2");
});
```

</details>
