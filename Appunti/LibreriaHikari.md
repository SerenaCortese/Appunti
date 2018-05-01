# Realizzazione della ConnectionPooling: HikariCP
## Scaricare la Libreria Hikari DataSource

* Andare su Google e digitare `hikaricp maven` (Maven è il repository con tutte le librerie Java)
* Seleziono il primo risultato `Maven Repository: com.zaxxer>>HikariCP` 

oppure [link diretto](https://mvnrepository.com/artifact/com.zaxxer/HikariCP)

* Seleziono la versione 3.1 e clicco su `Bundle` che mi permette di scaricare il file`jar`.

HikariCP per funzionare necessita di un'altra libreria, **SLF4J** ( [scaricabile qui (scegliere il primo zip)](https://www.slf4j.org/download.html) ) che è una libreria di logging ovvero che serve per stampare ciò che sta succedendo secondo diverse priorità: es. log(= stampe) relative al debug, ad errori, a criticità ecc.

## Importare la libreria nel progetto Java

Nella cartella `lib` del progetto 
* copiamo il file jar di `HikariCP.jar`
* estriamo i file jar dallo zip di slf4j
* copiamo `slf4j-api-sources.jar` e `alf4j-jdk-sources.jar` 
* Selezioniamo i tre file appena aggiunti, tasto destro, `Build Path > Add To Build Path`
* Le importo nel progetto