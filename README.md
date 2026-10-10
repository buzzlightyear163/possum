# $POSSUM · Plays dead every dip

Statisk sajt i en fil. Ingen build, inga API-nycklar.

## Filer

- `index.html`: hela sajten (HTML, CSS och JS i samma fil)
- `img/`: possumen i fyra lägen (frilagda), bannern och pfp
- `og.jpg`: delningsbild för X (1200×630)
- `favicon.png`, `apple-touch-icon.png`

## Fyll i vid launch

Öppna `index.html` och leta upp `CONFIG` längst upp i `<script>`:

```js
const CONFIG = {
  ca: "",          // mint-adressen
  x: "",           // https://x.com/...
  telegram: "",    // https://t.me/...
  site: "",        // https://din-doman.xyz (läggs till i delningstexten)
  awakeAbove: 3,   // 1h-förändring över +3 % = vaken
  deadBelow: -3,   // 1h-förändring under −3 % = spelar död
  refreshSeconds: 30
};
```

- **Tom `ca`:** CA-rutorna visar "Posted here and on X at launch", Buy-knapparna scrollar till token-sektionen och possumen ligger med ett öga öppet (PREVIEW).
- **Med `ca`:** Buy går till `pump.fun/coin/<ca>`, Chart-knappen visas, och possumen följer den riktiga 1h-charten från Dexscreener var 30:e sekund (LIVE).
- **Tom X eller Telegram:** den knappen döljs. Är båda tomma döljs hela raden.

## Deploy (GitHub → Vercel)

1. Lägg mappen i ett nytt GitHub-repo.
2. Vercel → Add New Project → välj repot → Framework Preset: **Other**, inget build-kommando, output-mapp: roten.
3. Deploy.

## Kolla efter deploy

- Bagel Fat One, Gabarito och Special Elite laddas från Google Fonts (rubriken ska vara tjock och rundad).
- Rainbow-spiralen rör sig och blir mörk när du trycker **Dump it**.
- Toe tag: ändra handle eller dip, ladda ner PNG och kolla att texten sitter på lappen.
- Reaction pack: alla sex bilderna syns och **Save** laddar ner dem.
- X-förhandsvisning: klistra in länken i en tweet-draft. Om bilden inte syns, byt `/og.jpg` i meta-taggarna mot den fullständiga adressen, t.ex. `https://din-doman.xyz/og.jpg`.
- Med CA ifylld: status-chippet ska säga **LIVE** med en grön lampa.

## Vad som är på riktigt och vad som är exempel

- Hero-statusen är live först när CA:n är ifylld och paret finns på Dexscreener.
- **Dump it** och **Pump it** är simuleringar och märks SIMULATED.
- Candle-charten i "The reflex" är ett exempel och märks som det.
