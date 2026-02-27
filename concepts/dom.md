# 1. DOM — Document Object Model

Når en browser indlæser en HTML-side, omdanner den al markup til et træ af objekter i hukommelsen. Det træ kaldes DOM'en. JavaScript arbejder ikke direkte med HTML-tekst — det arbejder med dette træ.

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

## Vigtigste pointer

- DOM'en er browserens repræsentation af din HTML — ikke selve filen
- JavaScript manipulerer DOM'en, ikke HTML-teksten
- Uden forståelse for DOM'en er AI-genereret kode uforståelig magi