# 1. DOM — Document Object Model

Når en browser indlæser en HTML-side, omdanner den al markup til et træ af objekter i hukommelsen. Det træ kaldes DOM'en. 
JavaScript arbejder ikke direkte med HTML-tekst — det arbejder med dette træ.

## HTML bliver til et træ

```html
<body>
  <h1>Hej</h1>
  <p id="besked">Velkommen</p>
</body>
```

Browseren læser dette og skaber objekter der repræsenterer hvert element. `body` er forælder til `h1` og `p`. Hvert element er en knude i træet.

## Tilgå elementer med JavaScript

For at arbejde med et element skal du først finde det i DOM'en:

```javascript
const besked = document.querySelector("#besked");
```

`document` er selve siden. `querySelector` finder det første element der matcher en CSS-selector.

## Læs og ændr indhold

Når du har fat i et element, kan du læse eller ændre det:

```javascript
console.log(besked.textContent);       // læs teksten
besked.textContent = "God dag!";       // skift teksten
besked.style.color = "red";            // skift udseende
```



## querySelector — Find elementer i DOM'en

`querySelector` er den primære måde at finde elementer på i moderne JavaScript. Den bruger CSS-selektorer — så hvis du kender CSS, kender du allerede syntaksen.

```javascript
document.querySelector("#mit-id");        // finder element med id
document.querySelector(".min-klasse");    // finder første element med klassen
document.querySelector("h1");            // finder første h1-element
document.querySelector("input[type='text']"); // finder første tekstfelt
```

### querySelector vs querySelectorAll

`querySelector` returnerer **ét element** — det første der matcher. Hvis du vil have alle der matcher, bruges `querySelectorAll`:

```javascript
const alleKnapper = document.querySelectorAll("button");
```

`querySelectorAll` returnerer en liste af elementer som du kan løbe igennem.

### Søg inden for et element

Du behøver ikke altid søge fra `document`. Du kan også søge inden for et specifikt element:

```javascript
const formular = document.querySelector("form");
const knap = formular.querySelector("button"); // finder knap inden for formularen
```

## Ændr indhold i et element

Når du har fundet et element, er der tre egenskaber du typisk bruger til at læse eller ændre dets indhold:

### textContent

Sætter eller henter ren tekst. HTML-tags behandles som almindelig tekst:

```javascript
const titel = document.querySelector("h1");
titel.textContent = "Hej verden";
```

### innerHTML

Sætter eller henter indhold inkl. HTML-tags. Brug denne når du vil bygge dynamisk HTML:

```javascript
const liste = document.querySelector("ul");
liste.innerHTML = "<li>Æble</li><li>Banan</li>";
```

Du vil ofte se `innerHTML` kombineret med `.map()` når du vil vise et array som en liste:

```javascript
const frugter = ["Æble", "Banan", "Citron"];
liste.innerHTML = frugter.map(f => `<li>${f}</li>`).join("");
```

### value

Bruges til at hente eller sætte værdien i formularfelter — `input`, `textarea` og `select`:

```javascript
const tekst = document.querySelector("textarea").value;
const valgt = document.querySelector("select").value;
```

### Hvornår bruger du hvad?

| Egenskab | Brug når |
|----------|---------|
| `textContent` | Du vil vise ren tekst |
| `innerHTML` | Du vil indsætte HTML-elementer dynamisk |
| `value` | Du vil læse input fra en bruger |

---

### Almindelige fejl

Hvis `querySelector` ikke finder noget, returnerer den `null` — og forsøger du at tilgå `.textContent` på `null`, får du en fejl. Tjek altid at elementet findes, eller at dit id/klasse-navn er stavet korrekt.

```javascript
const el = document.querySelector("#mit-id");
if (el) {
    el.textContent = "Fundet!";
}
```
## Vigtigste pointer

- DOM'en er browserens repræsentation af din HTML — ikke selve filen
- JavaScript manipulerer DOM'en, ikke HTML-teksten


[læs mere om DOM](https://www.w3schools.com/js/js_htmldom.asp) 