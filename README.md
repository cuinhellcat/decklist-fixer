# 🃏 Decklist Fixer

Kleines Web-Tool, das Set-Code und Kartennummer aus MTG-Decklisten entfernt —
damit Listen z. B. bei **tcg-arena.fr** direkt importiert werden können.

Aus:

```
1 Island (J25) 85
4 Lightning Bolt (STA) 42
```

wird:

```
1 Island
4 Lightning Bolt
```

## Nutzung

Einfach die gehostete Seite öffnen, Deckliste links einfügen, Ergebnis rechts
kopieren. Nichts wird hochgeladen — alles läuft im Browser.

**Live:** _(Link nach dem Deploy hier eintragen)_

## Funktionen

- Entfernt Set-Codes `(J25)`, Kartennummern (auch Promo wie `264p`),
  Foil-/Etch-Marker (`*F*`, `*E*`) und Moxfield-Tags (`#…`)
- Wandelt `2x Sol Ring` → `2 Sol Ring`
- Checkbox: Abschnitts-Überschriften (Deck, Sideboard, Commander …) behalten
  oder entfernen
- Zählt Karten in Ein- und Ausgabe
- Funktioniert auch offline als lokale Datei (`index.html` doppelklicken)

## Aufbau

Alles steckt in einer einzigen `index.html` (Inline-CSS + Inline-JS, keine
Abhängigkeiten). Die Parsing-Logik ist als eigenständige Funktion
`fixDecklist(text, keepSections)` gekapselt, damit sie z. B. von einem
Discord-Bot wiederverwendet werden kann.
