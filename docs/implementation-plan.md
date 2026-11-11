# Plan de implementare – TogetherPlan

## 1. Scop

Acest document prezinta planul propus pentru implementarea aplicatiei TogetherPlan.

Dezvoltarea va fi realizata incremental, incepand cu functionalitatile principale si continuand cu cele secundare.

## 2. Etapele implementarii

### Etapa 1 – Pregatirea proiectului

Activitati:
- Organizarea structurii proiectului.
- Configurarea mediului Node.js si Express.
- Pregatirea fisierelor HTML, CSS si JavaScript.
- Configurarea bazei de date SQLite.
- Stabilirea regulilor de colaborare pe GitHub.

Rezultat: structura initiala a aplicatiei.

### Etapa 2 – Autentificare si grupuri

Activitati:
- Implementarea inregistrarii utilizatorilor.
- Implementarea autentificarii.
- Stocarea securizata a parolelor.
- Crearea si afisarea grupurilor.
- Gestionarea membrilor grupurilor.

Rezultat: utilizatorii pot avea conturi si pot organiza grupuri.

### Etapa 3 – Gestionarea sarcinilor

Activitati:
- Crearea sarcinilor.
- Afisarea sarcinilor unui grup.
- Atribuirea sarcinilor membrilor.
- Modificarea si stergerea sarcinilor.
- Marcarea sarcinilor ca finalizate.

Rezultat: membrii grupului pot gestiona sarcinile comune.

### Etapa 4 – Liste de cumparaturi

Activitati:
- Crearea listelor de cumparaturi.
- Adaugarea produselor si cantitatilor.
- Modificarea si stergerea produselor.
- Marcarea produselor cumparate.
- Afisarea modificarilor pentru membrii grupului.

Rezultat: liste de cumparaturi colaborative.

### Etapa 5 – Functionalitati secundare

Activitati:
- Afisarea sarcinilor intr-un calendar.
- Inregistrarea cheltuielilor comune.
- Calcularea totalului cheltuielilor.

Aceste functionalitati vor fi dezvoltate dupa finalizarea celor principale, in functie de timpul disponibil.

### Etapa 6 – Testare si finalizare

Activitati:
- Testarea autentificarii.
- Testarea grupurilor si sarcinilor.
- Testarea listelor de cumparaturi.
- Verificarea drepturilor de acces.
- Verificarea afisarii pe dispozitive diferite.
- Corectarea erorilor.
- Actualizarea documentatiei.

Rezultat: o versiune functionala si testata a aplicatiei.

## 3. Prioritizarea functionalitatilor

| Prioritate | Functionalitate |
|---|---|
| Ridicata | Inregistrare si autentificare |
| Ridicata | Crearea si gestionarea grupurilor |
| Ridicata | Gestionarea si atribuirea sarcinilor |
| Ridicata | Liste de cumparaturi colaborative |
| Secundara | Calendar |
| Secundara | Cheltuieli comune |

## 4. Organizarea echipei

Proiectul va fi dezvoltat de o echipa de trei membri.

Responsabilitatile vor fi distribuite intre:
- Dezvoltarea interfetei frontend.
- Implementarea backend-ului si a API-ului REST.
- Proiectarea si integrarea bazei de date.
- Testarea si documentarea aplicatiei.

Membrii echipei vor colabora la integrarea componentelor si la verificarea functionalitatilor.

Distribuirea exacta a responsabilitatilor va fi stabilita de comun acord.

## 5. Versionare si colaborare

Pentru gestionarea codului sursa va fi utilizat GitHub.

Modul de lucru propus:

1. Proiectul este pastrat intr-un repository comun.
2. Fiecare membru lucreaza pe un branch separat.
3. Modificarile sunt salvate prin commit-uri descriptive.
4. Pentru integrarea modificarilor se creeaza pull request-uri.
5. Modificarile sunt verificate inainte de integrarea in branch-ul principal.

Exemple de branch-uri:
- feature/auth
- feature/groups
- feature/tasks
- feature/shopping

## 6. Testarea aplicatiei

Vor fi verificate urmatoarele scenarii:

| Test | Rezultat asteptat |
|---|---|
| Inregistrare cu email valid | Contul este creat |
| Inregistrare cu email existent | Este afisata o eroare |
| Autentificare cu parola gresita | Accesul este refuzat |
| Crearea unui grup | Grupul apare in lista |
| Adaugarea unei sarcini | Sarcina este salvata |
| Atribuirea unei sarcini | Responsabilul este asociat |
| Finalizarea unei sarcini | Statusul este actualizat |
| Adaugarea unui produs | Produsul apare in lista |
| Marcarea unui produs cumparat | Statusul produsului este actualizat |
| Accesarea unui grup strain | Accesul este refuzat |

## 7. Riscuri si solutii

| Risc | Solutie propusa |
|---|---|
| Timp insuficient | Prioritizarea functionalitatilor principale |
| Probleme la integrarea componentelor | Testare si integrare treptata |
| Conflicte Git | Branch-uri separate si pull request-uri |
| Erori in baza de date | Validarea datelor si testarea operatiilor |
| Probleme de securitate | Verificarea autentificarii si permisiunilor |

## 8. Rezultatul asteptat

La finalul implementarii, TogetherPlan va permite utilizatorilor sa creeze conturi, sa organizeze grupuri, sa atribuie sarcini si sa gestioneze liste comune de cumparaturi.

Calendarul si evidenta cheltuielilor reprezinta functionalitati secundare, care pot completa aplicatia daca timpul permite.
