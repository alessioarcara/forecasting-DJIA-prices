# Forecasting DJIA Prices
Progetto A.A 2020-2021 del corso di Programmazione di Applicazioni Data Intensive<br>
Alessio Arcara

## Dataset

Il dataset scelto è composto da due file *csv* :
1. <strong>Stocks data</strong>: Indice Dow Jones Industrial Average (DJIA) composto dalle trenta imprese industriali statunitensi più redditizie del mercato. <br>*(Range: 2008-08-08 to 2016-07-01)*
2. <strong>News data</strong>: i titoli dei post dal canale Reddit WorldNews (<a href="https://www.reddit.com/r/worldnews/">/r/worldnews</a>). Sono classificate con i voti degli utenti reddit, e solo i 25 migliori titoli sono considerati per singolo giorno. <br>*(Range: 2008-06-08 to 2016-07-01)*

Le <strong>32</strong> colonne considerate sono le seguenti:
- "Date" (*intervallo*): data giornaliera di scambio del titolo azionario,
- "Open, High, Low, Close, Adj Close" (*numerica*): prezzo di apertura, chiusura e prezzo minimo, massimo giornaliero del titolo azionario.
- "Volume" (*ratio*): quantità scambiata giornalmente del titolo azionario.
- "Top1,...,Top25" (*testo*): i titoli dei migliori 25 post giornalieri del canale Reddit WorldNews.

Le istanze fornite sono <strong>1989</strong> e la variabile da predire "Label", che verrà creata e spiegata nel dettaglio nelle seguenti sezioni, è una variabile discreta multiclasse (-1, 0, 1). 

## Obiettivo: È possibile prevedere il mercato?

Una "passeggiata aleatoria" è un fenomeno statistico in cui una variabile non segue un andamento distinguibile e si muove apparentemente in modo casuale. La teoria del <strong>random walk</strong>, applicata ai mercati finanziari, delineata più chiaramente da Burton Malkiel, postula che il prezzo dei titoli si muove casualmente, e che, quindi, ogni tentativo di prevedere il movimento futuro dei prezzi, attraverso l'analisi fondamentale o tecnica, è inutile.

L'obiettivo è generare modelli in grado di prevedere se l'indice DJIA avrà al giorno $t$ un movimento rialzista o ribassista, in modo da generare un profitto investendo in un fondo che si basi su tale indice.

Il progetto è suddiviso in due parti:<br>

1. Nella prima parte verranno utilizzati <strong>solo</strong> i dati storici sull'andamento dell'indice DJIA per generare una predizione al tempo <i>t</i> sul movimento rialzista (1) o ribassista (-1);
2. Nella seconda parte si utilizzerà il testo dei titoli dei post per cercare una correlazione tra l'andamento dell'indice DJIA e notizie generiche attraverso il <strong>Natural Language Process</strong> (NLP) e dunque, migliorare i risultati precedentemente ottenuti;
