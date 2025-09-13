# 📈 Analisi di Serie Temporali

Le serie temporali rappresentano un insieme di osservazioni ordinate nel tempo. Non si tratta semplicemente di dati numerici, ma di sequenze che riflettono l’evoluzione di un fenomeno. Un esempio molto comune è l’andamento mensile della produzione di birra in Australia, che costituisce il dataset analizzato in questo progetto. Ogni punto della serie è influenzato dal suo passato e spesso risente di componenti cicliche o stagionali: in questo senso una serie temporale non può essere studiata come un semplice campione indipendente di dati.

Un concetto fondamentale è la **stazionarietà**. Una serie si dice stazionaria quando le sue proprietà statistiche (media, varianza, autocorrelazione) non cambiano nel tempo. La stazionarietà è cruciale perché molti modelli predittivi si basano su questa ipotesi. Per verificarla si utilizzano metodi come il test di Dickey-Fuller aumentato (ADF), che permette di stabilire se una serie ha una radice unitaria e dunque se presenta un trend o una stagionalità persistente. Quando una serie non è stazionaria, si possono applicare trasformazioni come la differenziazione o la detrendizzazione per stabilizzarla.

![Testo alternativo](/IMG/1.png)


Un altro passaggio essenziale è la **decomposizione della serie temporale**, che permette di distinguere tre componenti principali: il trend, ossia l’andamento di lungo periodo; la stagionalità, ovvero i pattern che si ripetono con una certa regolarità (ad esempio mensile o annuale); e il residuo, che rappresenta la parte non spiegata, il rumore casuale. Questa scomposizione aiuta a comprendere meglio la natura dei dati e a costruire modelli predittivi più accurati.

![Testo alternativo](/IMG/2.png)

Sul fronte della modellistica, esistono approcci diversi. I modelli autoregressivi (**AR**) si basano sul legame tra il valore attuale e i valori passati della serie. I modelli a media mobile (**MA**) invece utilizzano le correlazioni degli errori passati per migliorare la previsione. L’integrazione di entrambi porta al modello **ARIMA**, che diventa uno degli strumenti più potenti e flessibili per analizzare serie stazionarie o rese tali mediante differenziazione. Per includere la stagionalità si estende il modello a **SARIMA** o **SARIMAX**, che può anche inglobare variabili esogene. Un approccio alternativo e molto usato in pratica è quello delle medie esponenziali: dai metodi semplici (SES) fino all’**Holt-Winters Exponential Smoothing (HWES)**, capace di gestire trend e stagionalità in modo elegante e intuitivo. Questi modelli, pur basandosi su formule relativamente semplici, riescono a catturare buona parte della dinamica delle serie reali.

![Testo alternativo](/IMG/3.png)


---

## 📝 Struttura degli script

Il notebook incluso in questo repository si concentra sulla serie temporale della produzione mensile di birra in Australia. La prima parte dello script si dedica al caricamento e all’esplorazione del dataset, con grafici descrittivi che mostrano immediatamente la presenza di stagionalità e tendenze di lungo periodo. Successivamente si affronta la verifica della stazionarietà mediante test statistici e trasformazioni della serie, mostrando come le differenze possano stabilizzare la varianza e la media.

Segue la sezione di decomposizione, in cui la serie viene separata nelle tre componenti principali: trend, stagionalità e residuo. Questo passaggio non è solo teorico, ma diventa visivamente chiaro grazie ai grafici generati, che permettono di apprezzare quanto la stagionalità incida sull’andamento complessivo.

La parte successiva riguarda i modelli previsivi. Vengono applicati e confrontati diversi approcci: AR, MA, ARIMA e le loro varianti stagionali, fino al metodo Holt-Winters. Lo script non si limita a fornire previsioni, ma ne valuta la bontà tramite metriche di errore e confronto grafico con i dati reali. Questa scelta metodologica consente di evidenziare come ogni modello reagisca a trend e stagionalità differenti.

Dal punto di vista strutturale, il notebook è pensato per essere modulare: le funzioni implementate per il caricamento, la verifica di stazionarietà, la decomposizione e la modellizzazione possono essere riutilizzate con facilità anche su altri dataset temporali. Questo rende il progetto non solo un caso di studio specifico, ma una piccola libreria di strumenti applicabili a molte situazioni simili.

Infine, un aspetto curioso riguarda la natura del dataset scelto. La produzione di birra è influenzata da fattori culturali e stagionali (consumo maggiore nei mesi caldi, cali nei mesi invernali), il che lo rende un esempio didattico ideale per osservare come trend e stagionalità emergano con chiarezza in una serie temporale reale. La combinazione tra rigore matematico e interpretazione intuitiva rende lo script non solo utile per scopi accademici, ma anche facilmente comprensibile a un pubblico più ampio.

---
