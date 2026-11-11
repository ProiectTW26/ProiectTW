# Scenarii de utilizare – TogetherPlan

## UC1 – Crearea unui grup

**Cerință asociată:** CF2

**Actor principal:** Utilizator autentificat.

**Scop:** Crearea unui grup pentru organizarea activităților comune.

**Precondiții:**
- Utilizatorul are un cont.
- Utilizatorul este autentificat.

**Flux principal:**
1. Utilizatorul accesează secțiunea „Grupurile mele”.
2. Apasă butonul „Creează grup”.
3. Introduce numele grupului.
4. Apasă butonul „Salvează”.
5. Aplicația verifică datele introduse.
6. Aplicația salvează grupul în baza de date.
7. Noul grup apare în lista utilizatorului.

**Flux alternativ:**
- Dacă numele grupului este gol, aplicația afișează un mesaj de eroare și solicită completarea acestuia.

**Postcondiții:**
- Grupul este creat.
- Utilizatorul devine membru al grupului.

**Criteriu de verificare:**
- După salvarea unui nume valid, grupul apare în „Grupurile mele”.
- Dacă numele este gol, grupul nu este creat.

---

## UC2 – Adăugarea și atribuirea unei sarcini

**Cerințe asociate:** CF3, CF4, CF5

**Actor principal:** Membru al unui grup.

**Scop:** Crearea unei sarcini și atribuirea acesteia unui membru.

**Precondiții:**
- Utilizatorul este autentificat.
- Utilizatorul face parte dintr-un grup.

**Flux principal:**
1. Utilizatorul selectează un grup.
2. Accesează secțiunea „Sarcini”.
3. Apasă butonul „Adaugă sarcină”.
4. Completează titlul, descrierea și termenul-limită.
5. Selectează un membru al grupului responsabil de sarcină.
6. Apasă butonul „Salvează”.
7. Aplicația verifică datele și salvează sarcina.
8. Sarcina apare în lista grupului cu statusul „De făcut”.
9. Membrul responsabil poate marca ulterior sarcina drept „Finalizată”.

**Fluxuri alternative:**
- Dacă titlul este gol, aplicația afișează un mesaj de eroare.
- Dacă persoana selectată nu aparține grupului, aplicația respinge atribuirea.

**Postcondiții:**
- Sarcina este salvată și asociată grupului.
- Sarcina are un responsabil și un status.

**Criteriu de verificare:**
- Sarcina creată apare în lista grupului.
- Responsabilul afișat este cel selectat.
- Modificarea statusului în „Finalizată” este salvată.
- Datele invalide nu sunt acceptate.

---

## UC3 – Gestionarea unei liste comune de cumpărături

**Cerință asociată:** CF6

**Actori principali:** Membrii unui grup.

**Scop:** Organizarea cumpărăturilor printr-o listă comună.

**Precondiții:**
- Utilizatorii sunt autentificați.
- Utilizatorii aparțin aceluiași grup.

**Flux principal:**
1. Primul utilizator selectează grupul.
2. Accesează secțiunea „Liste de cumpărături”.
3. Creează o listă nouă cu numele „Cumpărături săptămânale”.
4. Adaugă produsul „Lapte” și cantitatea „2”.
5. Aplicația salvează lista și produsul.
6. Al doilea membru accesează aceeași listă.
7. Al doilea membru adaugă produsul „Pâine”.
8. Aplicația salvează modificarea.
9. Primul utilizator reîncarcă lista și vede ambele produse.
10. Un membru marchează produsul „Lapte” ca fiind cumpărat.

**Fluxuri alternative:**
- Dacă denumirea produsului este goală, aplicația afișează un mesaj de eroare.
- Dacă utilizatorul nu aparține grupului, accesul la listă este refuzat.

**Postcondiții:**
- Lista conține produsele adăugate de ambii membri.
- Produsele cumpărate sunt marcate corespunzător.

**Criteriu de verificare:**
- Ambii membri pot vedea produsele după reîncărcarea listei.
- Marcarea unui produs ca fiind cumpărat este păstrată.
- Utilizatorii din afara grupului nu pot accesa lista.

---

## Concluzie

Cele trei scenarii descriu funcționalități prioritare ale aplicației TogetherPlan: crearea grupurilor, gestionarea sarcinilor și colaborarea prin liste comune.