# Proiect SGBD - Gestionare Spital

## Descriere
Acest proiect implementează o bază de date pentru gestionarea activităților unui spital. Include tabele, proceduri stocate, funcții și trigger-uri pentru a automatiza procesele legate de pacienți, medici, consultații, tratamente și investigații.

## Funcționalități
- Gestionarea pacienților, medicilor și consultațiilor.
- Evidența tratamentelor și investigațiilor medicale.
- Generarea rapoartelor detaliate despre pacienți și tratamente.
- Calcularea duratei medii a tratamentelor pentru afecțiuni specifice.
- Afișarea celor mai frecvente afecțiuni și tratamente asociate.
- Implementarea trigger-urilor pentru monitorizarea modificărilor în tabele.

## Structura bazei de date
### Tabele principale:
- **Medic**: Evidența medicilor (ID, nume, specializare, cod parafă).
- **Pacient**: Evidența pacienților (ID, nume, prenume, CNP, data nașterii).
- **Consultatie**: Consultațiile efectuate (ID, medic, pacient, data, ora).
- **Tratament**: Tratamentele prescrise (ID, denumire, descriere, date de început și sfârșit).
- **Investigatie**: Investigațiile efectuate (ID, denumire, descriere, preț, date de început și sfârșit).
- **Fisa_Medicala**: Informații despre pacienți (ID, investigație, pacient, adresă, telefon).

### Proceduri și funcții:
- `Raport_Activitate`: Generează un raport detaliat despre activitatea medicilor și pacienților.
- `Detalii_Tratament`: Returnează detalii despre pacienții care urmează un tratament specific.
- `Durata_Medie_Tratament`: Calculează durata medie a tratamentelor pentru o afecțiune.
- `Afisare_Pacienti`: Afișează pacienții care suferă de o anumită afecțiune.

### Trigger-uri:
- `LMD_Investigatie`: Monitorizează operațiile de `INSERT`, `UPDATE` și `DELETE` pe tabelul `Investigatie`.
- `Trg_LDD`: Înregistrează modificările de tip `CREATE`, `ALTER` sau `DROP` în tabele.

## Instalare
1. Clonați acest repository:
   ```bash
   git clone https://github.com/utilizator/proiect-sgbd.git
   ```
2. Importați scripturile SQL în baza de date Oracle folosind SQL*Plus sau un alt client compatibil:
   ```sql
   @Proiect1.sql
   ```

## Utilizare
- Rulați procedurile și funcțiile pentru a genera rapoarte sau pentru a efectua operații specifice:
   ```sql
   BEGIN
       Raport_Activitate;
   END;
   /
   ```
