# MT5-Robot-Buy-Sell-Signals-1-Cluster
Analiză și detectare semnale (Spike Detection)

Folosește indicatori RSI, ATR și volume pentru a identifica mișcări bruște.

Detectează spike-uri bullish (de cumpărare) și bearish (de vânzare) în funcție de:

schimbări mari de preț,

spike în volum,

RSI în supracumpărare/supravânzare,

lumânări puternice (body > 60% din range),

breakout peste rezistență / sub suport.

Generare semnale de tranzacționare

Dacă apare un spike bullish → deschide un „cluster” de poziții pe două perechi configurate (ex: EURCAD și EURUSD).

Dacă apare un spike bearish → deschide un cluster de SELL pe perechile setate.

Se poate configura să ia doar BUY, doar SELL sau ambele direcții.

Clonare poziții (piramidare)

După un semnal principal, poate deschide poziții „clone” (maxim un număr setat) la un interval minim de timp (MinTimeBetweenClones).

Exemplu: la fiecare spike bullish nou, dacă există deja poziții BUY, adaugă încă un set de poziții („clonă”), dar nu mai des decât intervalul ales.

Gestionare poziții

Ține evidența pozițiilor principale și a clonelor (cu structuri dedicate).

Dacă apare un semnal opus (ex: bearish când există BUY deschise) → închide toate pozițiile în direcția opusă.

Monitorizează constant pozițiile și resetează variabilele dacă au fost închise manual.

Alerte și debug

Poate afișa în jurnal semnale identice cu cele din TradingView (inclusiv „Extreme Spike”).

Are opțiuni să arate niveluri de suport/rezistență și detalii de debug (RSI, volum, etc).

Configurare flexibilă

Perechile pe care deschide pozițiile pot fi diferite de perechea pe care se detectează spike-ul (ex: detectează pe USDCAD, dar tranzacționează EURCAD și EURUSD).

Tipul ordinului se poate seta BUY/SELL pentru fiecare pereche (inclusiv inversare).

Fiecare cluster are un Magic Number diferit pentru a nu se încurca cu alte EAs.
