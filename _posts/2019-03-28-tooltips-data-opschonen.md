---
title:  "Data opschonen"
excerpt_separator: <!--more-->
categories: [tooltips]
---

# Mijn favoriete tools om data op te schonen
### Zoeken en vervangen
Relatief simpele rommeligheden in data kun je opschonen met zoeken en vervangen, bijvoorbeeld in Excel. Letters met accenten die raar doen, gekke afbreekstreepjes, cijfers waar een punt in plaats van een komma in staat kun je met Zoeken en vervangen simpel oplossen.

### Regular Expressions
Iets geavanceerder zoeken en vervangen doe je met *Regular Expressions*, oftewel Regex. Met Regex kun je zoekopdrachten doen als *'vier cijfers, dan eventueel een spatie, en dan twee letters'*, als je bijvoorbeeld probeert om postcodes te pakken te krijgen. Een goede site is [RegExr.com](https://regexr.com/). Werkt ook als je bijvoorbeeld per se een adres moet achterhalen om een moordenaar te pakken te krijgen:

![XKCD-strip over Regular Expressions](https://imgs.xkcd.com/comics/regular_expressions.png)

### Google Refine
Google Refine (vroeger Open Refine) is gemaakt om te werken met rommelige data. Een heel handige functie is om waarden die op elkaar lijken, met elkaar te matchen. Bijvoorbeeld:
- Bergen (L.)
- Bergen (Limburg)
- Bergen (L)
- Bergen L

Dit zijn allemaal manieren om dezelfde gemeente te schrijven, maar het maakt het lastig om mee te werken. Google Refine kan helpen om dit soort rommel op te schonen.