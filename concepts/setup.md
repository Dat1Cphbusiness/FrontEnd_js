# 0. Opsætning — Forbind JavaScript til en webside

Før du skriver JavaScript, skal du forbinde det til dit HTML.

## Script-tagget

JavaScript lever i sin egen fil (f.eks. `script.js`) og linkes fra HTML med et `<script>`-tag:

```html
<head>
  <script src="js/script.js" defer></script>
</head>
```

`src`-attributten peger på filen. `defer` fortæller browseren om at vente med at køre scriptet til al HTML er indlæst — uden det kan din kode forsøge at tilgå elementer der endnu ikke findes.

## Tre filer, tre ansvarsområder

Et velstruktureret webprojekt adskiller ansvar:

| Fil | Ansvar |
|-----|--------|
| `index.html` | Struktur |
| `styles.css` | Udseende |
| `script.js` | Adfærd |

## Dit første debugging-værktøj

Browserkonsollen viser output og fejl fra dit script. Åbn den med `F12` (Windows) eller `Cmd + Option + J` (Mac) for at åbne konsollen direkte. Test at din fil er forbundet korrekt:

```javascript
console.log("script indlæst");
```

Hvis du ser beskeden i konsollen, er alt forbundet korrekt.

## Vigtigste pointer

- JavaScript er adfærd — hold det i sin egen fil
- Brug `defer` så scriptet kører efter siden er klar
- Konsollen er dit vigtigste værktøj når noget går galt