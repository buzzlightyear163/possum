# $POSSUM · CAM 02 · BACKYARD

En billig viltkamera fastspänd på en staketstolpe, en bakgård klockan 03:14. Possumen ligger på rygg och spelar död.

Statisk sajt, en fil. Ingen build, inga API-nycklar.

## Delar

- **Ingång:** `▶ PLAY TAPE`. Bruset slår på och ljudet startar (syrsor, vind, bandbrus).
- **Live-kameran:** bakgården med possumen, REC, tidsstämpel och rörelsesensor. Klicka på possumen för att peta på honom. Var femte gång öppnar han ett öga.
- **Akten:** viltvårdens incidentrapport på en clipboard, med din teckning som vittnesskiss.
- **SD-kortet:** 13 bilder från kameran. Öppna en bild för att se den större och spara den med kamerans infofält inbränt.
- **End of tape:** VCR-blå slutskärm med CA som bevislapp, Buy, X, TG och Rewind.

## Fyll i vid launch

Överst i `<script>` i `index.html`:

```js
const CONFIG = {
  ca: "",          // mint-adressen
  x: "",           // https://x.com/...
  telegram: "",    // https://t.me/...
  awakeAbove: 3,
  deadBelow: -3,
  refreshSeconds: 25
};
```

- **`ca`** är ifylld: `6MAMveFSkF7syYWy8Nf8xscUsZsTaX8VKqcJZgnepump`
- **Med `ca`:** BUY går till pump.fun och CA-knappen och bevislappen dyker upp. Rörelsesensorn följer 1h-förändringen från Dexscreener:
  - över +3 % hoppar han upp (MOTION DETECTED)
  - under −3 % ligger han död (NO MOTION)
  - däremellan har han ett öga öppet
- **Tom X eller TG:** knappen döljs.

## Filer

- `img/plate.webp`: bakgården (tom)
- `img/dead|peek|alive|back.webp`: possumens fyra lägen, frilagda
- `img/sketch.webp`: din teckning
- `caps/01–13.webp` och `-sm`-versioner: kamerabilderna
- `og.jpg`: delningsbild för X

## Deploy

GitHub → Vercel med Framework Preset **Other**, inget build-kommando.

## Kolla efter deploy

- Typsnitten VT323, Bagel Fat One, Special Elite och Reenie Beanie laddas från Google Fonts.
- Ljudet startar när du trycker PLAY TAPE och kan stängas av med SND.
- Save i bildvisaren laddar ner en jpg med infofältet.
- X-förhandsvisningen använder https://www.thefoolpossum.fun/og.jpg.
