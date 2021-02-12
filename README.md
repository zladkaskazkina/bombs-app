# bomb-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

## About project
Ukol na vytvoreni aplikaci pro spusteni bomb.
Pri nacteni muzete zvolit pocet bomb. Po potvrzeni tlacitkem Potvrdit se nacte zvoleny pocet bom. Kazdou bombu lze zvlast aktivovat - spusti se odpocet na 5 vterin, pak bomba zmizi. V pripade, ze stihnete aktivovat vsechny bomby najednou, zobrazi se vam tlacitko - Zneskodnit. Po je zmacknuti - zneaktivnite bomby. 

## Technicke reseni
Cela aplikace je psana ve VueJS. Sklada se z rodicovske komponenty Field a child komponenty BombSet. Pro nastaveni poctu bomb se pouziva komponenta BombAmount. Pro zneskodneni bomb pouzivame komponentu Deactivate.
