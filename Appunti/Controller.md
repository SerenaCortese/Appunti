# Azioni nel Controller
### Font per incolonnare i dati
Nel metodo `void initialize()` aggiungere:

	txtResult.setStyle("-fx-font-family: monospace");

Nelle stringhe in stampa invece usare `%-NUMEROs` per spaziare di pi� le scritte in colonna: numero � il numero di spazi che verranno occupati dalle parole. Esempio

	StringBuilder sb = new StringBuilder();
	for (Corso corso : corsi) {
		sb.append(String.format("%-8s ", corso.getCodins()));
		sb.append(String.format("%-4s ", corso.getCrediti()));
		sb.append(String.format("%-45s ", corso.getNome()));
		sb.append(String.format("%-4s ", corso.getPd()));
		sb.append("\n");
	}
	txtResult.appendText(sb.toString());

risulta cos�: 

![Logo](img/scritteInColonna.png)