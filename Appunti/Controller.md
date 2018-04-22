# Azioni nel Controller
### Font per incolonnare i dati
Nel metodo `void initialize()` aggiungere:

	txtResult.setStyle("-fx-font-family: monospace");

Nelle stringhe in stampa invece usare `%-NUMEROs` per spaziare di più le scritte in colonna: numero è il numero di spazi che verranno occupati dalle parole. Esempio

	StringBuilder sb = new StringBuilder();
	for (Corso corso : corsi) {
		sb.append(String.format("%-8s ", corso.getCodins()));
		sb.append(String.format("%-4s ", corso.getCrediti()));
		sb.append(String.format("%-45s ", corso.getNome()));
		sb.append(String.format("%-4s ", corso.getPd()));
		sb.append("\n");
	}
	txtResult.appendText(sb.toString());

risulta così: 

![Logo](img/scritteInColonna.png)