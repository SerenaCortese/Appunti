# Istruzioni GitHub
## Creazione nuovo Progetto
* Creo nuovo progetto su Eclipse normalmente: 
  * `File` 
  * `New` 
  * `Java Project`

* Creo repository locale: 
  * tasto dx sul progetto
  * `Team`
  * `Share Project`
  * Scelgo cartella da disco o la metto dentro a quella nel workspace cliccando su `Use or Create repository in parent folder of project`
  * Metto il tic sulla cartella
  * `Create Repository`
  * `Finish`

* Salvo versione del progetto nel repository che è ancora vuoto (i file sono nel workingspace), **PRIMO COMMIT DEL PROGETTO**:
  * `Team`
  * `Commit`
  * Aggiungo i file cambiati da `Unstaged Changes` a `Staged Changed` con il tasto ++ 
  * Aggiungo un messaggio di Commit in `Commit Message`
  * `Commit`

* Creo progetto nell'area personale su GitHub:
  * cliccando su `New Repository`
  * Assegno al progetto un nome e una descrizione
  * `Create Repository` (*NON METTERE README*)
  * Copio il link del repository

* **Push del progetto** da Eclipse:
  * `Team`
  * `Push Branch Master`
  * copio link nel campo `URL`
  * `Next`
  * `Finish`
  * `Close`.
* **Risoluzione di Push Rejected** : avviene quando si è modificato in remoto qualcosa e non si è fatto pull
  * Osservare con `Fetch` le modifiche effettuate
  * Fare `Pull` con opzione `Merge`così da fondere in un solo file le modifiche in locale e remoto
  * Selezionare `Push to Upstream` che dovrebbe funzionare senza problemi.
  
## Lavorare su progetto presente in GitHub
Se repository remoto in cui c'è progetto non è nella mia area GitHub, devo farne una copia cliccando su `Fork`, prima di eseguire i passaggi seguenti.
* Su Github nella repository della _MIA_ area clicco su `Clone or Download` e copio il link che appare
* Su Eclipse clicco su `Import`, `Git`, `Project from Git`, `Next`
* `Clone URL`, incollo il link se Eclipse non lo fa automaticamente, `Next`
* Scelgo i branch che voglio copiare, `Next` per due volte e poi `Finish`.

## Lavorare su Branch diversi del progetto
Partendo da un progetto con più rami in modo da avere versioni separate dello stesso progetto così da poter testarlo e salvarlo solo quando si è sicuri.
* **Accedere ad un branch** In Eclipse nel menù `Team` ,cliccando su `Switch to` si può accedere ad un altro ramo del progetto.
* **Creare un nuovo branch** In Eclipse nel menù `Team`, selezionare `Switch to` e poi `New Branch`, scegliere un nome da assegnare al branch e il branch di Origine da cui fare il nuovo ramo, selezionare `Configure upstream to push and pull` così che salvi anche in remoto, cliccare `Check out new branch` per iniziare a lavorare sul branch nuovo appena creato e poi `Finish`.
* **Unire due rami** In Eclipse tramite il comando `Merge` che fonde le modifiche fatte in un branch (Branch2) con quelle del branch precedente (Branch1)che voglio far andare avanti, così da poter eliminare poi Branch2: 
  * Faccio `Switch to` Branch 1
  * Clicco `Team`, `Merge` e scelgo dalla lista il ramo che voglio fondere a questo (Branch2), seleziono `Finish`. _Il Merge avviene solo le modifiche sono compatibili, altrimenti Git lascia il progetto in uno stato da unire manualmente_ Ora i due branch sono allineati, puntano allo stesso punto.
  * Seleziono `Push to Upstream` in modo da salvare le modifiche in remoto.

Differenza tra `Merge` e `Rebase`:
- **Merge** riporta tutti i commit del branch secondario nel primo, quindi si vedono tutti i passaggi intermedi
- **Rebase** prende l'ultima versione del branch secondario e la copia sul branch primario collassando in un commit solo tutto il lavoro svolto nel secondo branch.
