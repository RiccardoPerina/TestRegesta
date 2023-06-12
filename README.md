# TestRegesta
Progetto "TestRegesta" di Riccardo Perina. 

TestRegesta.sql

Descrzione:
Questo è il dump della struttura e dei dati di un database chiamato TestRegesta. 
Il database contiene quattro tabelle: Fornitore, Prodotto, Sconto e Giacenza. 

Configurazione:
La tabella Fornitore contiene informazioni sui fornitori di prodotti, come il nome dell'azienda, la città in cui si trovano, l'indirizzo e i giorni di evasione degli ordini. 

La tabella Prodotto contiene informazioni sui prodotti disponibili, come il nome e un ID univoco. 

La tabella Sconto contiene informazioni sugli sconti applicati dai fornitori, tra cui il tipo di sconto (quantità, totale o data), quando lo sconto è applicabile, la percentuale di sconto e l'ID del fornitore corrispondente. 

La tabella Giacenza tiene traccia della quantità e del prezzo dei prodotti in magazzino per ogni combinazione Fornitore/Prodotto. Previsto per uso futuro, un fornitore potrebbe voler applicare uno sconto anche all'articolo.

Il dump include anche gli indici e i vincoli di chiave esterna tra le varie tabelle. 

Questo dump è stato creato con il motore per il salvataggio dati InnoDB e con il set di caratteri latin1.


ConnessioneDatabase.php

Descrizione:
Il file ConnessioneDatabase.php contiene il codice necessario per stabilire la connessione con il server localhost e con il database TestRegesta utilizzando la classe mysqli di PHP.

Configurazione:
Nel file sono state cofnigurate queste costanti:

SERVER: indica il nome del server MySQL a cui ci si vuole connettere, in questo caso localhost
UTENTE: indica l'username per accedere al server MySQL, in questo caso root
PASSWORD: indica la password per accedere al server MySQL
DATABASE: indica il nome del database a cui ci si vuole connettere, in questo caso TestRegesta


Index.php

Descrzione:

Questa pagina PHP si occupa di visualizzare i fornitori disponibili per un prodotto scelto dall'utente, insieme ai relativi prezzi e tempi di spedizione. Inoltre, se l'utente inserisce una quantità di prodotto, la pagina mostra anche eventuali sconti applicabili e il prezzo totale scontato.

Configurazione:

Il codice inizia importando il file "ConnessioneDatabase.php", che si occupa di stabilire la connessione al database.

Successivamente, viene creata la pagina HTML. In questa pagina è presente un form in cui l'utente può selezionare il prodotto e inserire una quantità. Una volta premuto il tasto "Cerca", vengono eseguite le query necessarie per ottenere l'elenco dei fornitori disponibili per il prodotto scelto dall'utente e vengono stampati i relativi dati.

Il primo blocco di codice legge dal database tutti i prodotti disponibili e li stampa in un menu a tendina. Il secondo blocco, eseguito dopo che l'utente ha premuto il tasto "Cerca", legge dalla POST i valori inseriti dall'utente e seleziona i fornitori con disponibilità del prodotto scelto. Per ogni fornitore, viene stampato il nome, il prezzo unitario, il prezzo totale con eventuali sconti applicati e i giorni di evasione dell'ordine. Inoltre, viene creato un array contenente i prezzi totali scontati, utile per trovare il prezzo migliore.

Dopo aver stampato i fornitori disponibili, viene eseguita una seconda query per selezionare i fornitori che non hanno disponibilità per il prodotto scelto. Anche questi fornitori vengono stampati a schermo.

Infine, se ci sono fornitori disponibili, viene trovato il prezzo totale minimo degli ordini e viene evidenziato il fornitore corrispondente.

In sintesi, questa pagina si occupa di fornire all'utente un elenco completo dei fornitori disponibili per un prodotto, insieme ai relativi prezzi e tempi di spedizione, permettendo anche di valutare eventuali sconti applicabili e trovare il prezzo più conveniente.

Stile.css

Descrizione:
Il file CSS definisce lo stile della pagina HTML.

Configurazione:
La prima regola applica un padding di 10px a tutto il contenuto del body della pagina.
La seconda regola definisce il colore del testo degli elementi h1.
La terza regola applica un'immagine di sfondo alla pagina HTML utilizzando l'url dell'immagine (Sfondo_TestRegesta.jpg) presente nella cartella "Immagine" e la definizione di alcune proprietà relative alla visualizzazione dell'immagine. Inoltre, viene specificata la famiglia del font utilizzata nella pagina.



