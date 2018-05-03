# Operazioni su Database
## Importare un DB
* Scaricare il database in formato `.sql`
* Avviare il database locale `XAMPP`
* Lanciare il programma `HeidiSQL` e selezionare `File > Carica file SQL` e selezionare il file del database e cliccare su `Esegui > Aggiorna`.
* Se non aggiorna, chiude e riaprire `HeidiSQL`.

## Aggiungere dati a un DB esistente

Esempio ( preso da [Lab04_SegreteriaStudenti](https://github.com/SerenaCortese/Lab04) ) :

	/*
	 * Data una matricola ed il codice insegnamento, iscrivi lo studente al corso.
	 */
	public boolean inscriviStudenteACorso(Studente studente, Corso corso) {
		String sql = "INSERT IGNORE INTO `iscritticorsi`.`iscrizione` (`matricola`, `codins`) VALUES(?,?)";
		boolean returnValue = false;
		try {
			Connection conn = ConnectDB.getConnection();
			PreparedStatement st = conn.prepareStatement(sql);
			st.setInt(1, studente.getMatricola());
			st.setString(2, corso.getCodins());
			int res = st.executeUpdate();	
			if (res == 1)
				returnValue = true;
			conn.close();
		} catch (SQLException e) {
			e.printStackTrace();
			throw new RuntimeException("Errore Db");
		}
		return returnValue;
	}
