---
tags:
  - kosten
---

When $a \ne 0$, there are two solutions to $(ax^2 + bx + c = 0)$ and they are 
$$ x = {-b \pm \sqrt{b^2-4ac} \over 2a} $$

$$
\displaystyle
\left( \sum_{k=1}^n a_k b_k \right)^2
\leq
\left( \sum_{k=1}^n a_k^2 \right)
\left( \sum_{k=1}^n b_k^2 \right)
$$
``math 1+1``
```math
formula= sqrt(100)
```

[Rechner](https://www.finanzfluss.de/rechner/kreditlaufzeit-berechnen/)
Maximaler Betrag
Rate = 1000€
Restschuld = 0€

|Zinssatz| 5 a. 60k€ |10 a. 120k€| 15 a. 180k€| 20 a. 240k€ | 25 a. 300k€ | 30 a. 360k€|
|-|-|-|-|-|-|-|
|1|58.501€|114.150€|167.086€|217.441€|265.342€|310.907€|
|2|57.052€|108.680€|155.398€|197.674€|235.930€|270.549€|
|3|55.652€|103.562€|144.805€|180.311€|210.876€|237.189€|
|4|54.299€|98.770€|135.192€|165.022€|189.452€|209.461€|
|5|52.991€|94.281€|126.455€|151.525€|171.060€|186.282€|
|6|51.726€|90.073€|118.504€|139.581€|155.207€|166.792€|


[Rate:: 250]
[Zinssatz:: 6]
[Monate:: 48]
`$=dv.current().Rate/(dv.current().Zinssatz/1200)*(1-Math.pow((1+(dv.current().Zinssatz/1200)),-dv.current().Monate))`

```dataviewjs
function kredit(rate, zinssatz, monate){
	return rate/(zinssatz/1200)*(1-Math.pow((1+(zinssatz/1200)),-monate))
}
dv.span(kredit(250,6,48))
dv.table(
    ["Col1", "Col2", "Col3"],
        [
            ["Row1", "Dummy", "Dummy"],
            ["Row2", 
                ["Bullet1",
                 "Bullet2",
                 "Bullet3"],
             "Dummy"],
            ["Row3", "Dummy", "Dummy"]
        ]
    );

const table = dv.markdownTable(["File", "Genre", "Time Read", "Rating"], dv.pages("#book")
    .sort(b => b.rating)
    .map(b => [b.file.link, b.genre, b["time-read"], b.rating]))

dv.paragraph(table);

```

