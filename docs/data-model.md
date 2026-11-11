
# Modelul de date si API-ul – TogetherPlan

## 1. Descriere generala

Aplicatia TogetherPlan va utiliza o baza de date relationala SQLite pentru stocarea informatiilor despre utilizatori, grupuri, sarcini, liste de cumparaturi si cheltuieli.

Modelul de date este preliminar si poate fi ajustat in etapa de implementare.

## 2. Tabelele bazei de date

### 2.1 users

Stocheaza informatiile despre utilizatori.

| Camp | Tip | Descriere |
|---|---|---|
| id | INTEGER, PK | Identificator unic |
| name | TEXT | Numele utilizatorului |
| email | TEXT, UNIQUE | Adresa de email |
| password_hash | TEXT | Parola stocata securizat |
| created_at | TEXT | Data crearii contului |

### 2.2 groups

Stocheaza grupurile create de utilizatori.

| Camp | Tip | Descriere |
|---|---|---|
| id | INTEGER, PK | Identificator unic |
| name | TEXT | Numele grupului |
| created_by | INTEGER, FK | Utilizatorul care a creat grupul |
| created_at | TEXT | Data crearii grupului |

### 2.3 group_members

Stocheaza apartenenta utilizatorilor la grupuri.

| Camp | Tip | Descriere |
|---|---|---|
| group_id | INTEGER, FK | Identificatorul grupului |
| user_id | INTEGER, FK | Identificatorul utilizatorului |
| joined_at | TEXT | Data intrarii in grup |

Cheia primara este compusa din group_id si user_id.

### 2.4 tasks

Stocheaza sarcinile asociate grupurilor.

| Camp | Tip | Descriere |
|---|---|---|
| id | INTEGER, PK | Identificator unic |
| group_id | INTEGER, FK | Grupul caruia ii apartine sarcina |
| title | TEXT | Titlul sarcinii |
| description | TEXT | Descrierea sarcinii |
| assigned_to | INTEGER, FK | Utilizatorul responsabil |
| deadline | TEXT | Termenul-limita |
| status | TEXT | pending sau completed |
| created_by | INTEGER, FK | Utilizatorul care a creat sarcina |

Campul assigned_to poate fi NULL daca sarcina nu este atribuita.

## 2.5 shopping_lists

Stocheaza listele de cumparaturi ale grupurilor.

| Camp | Tip | Descriere |
|---|---|---|
| id | INTEGER, PK | Identificator unic |
| group_id | INTEGER, FK | Grupul asociat |
| name | TEXT | Denumirea listei |
| created_by | INTEGER, FK | Creatorul listei |

## 2.6 shopping_items

Stocheaza produsele din listele de cumparaturi.

| Camp | Tip | Descriere |
|---|---|---|
| id | INTEGER, PK | Identificator unic |
| list_id | INTEGER, FK | Lista de cumparaturi |
| name | TEXT | Denumirea produsului |
| quantity | INTEGER | Cantitatea |
| is_purchased | INTEGER | 0 = necumparat, 1 = cumparat |

## 2.7 expenses

Stocheaza cheltuielile comune ale grupurilor.

| Camp | Tip | Descriere |
|---|---|---|
| id | INTEGER, PK | Identificator unic |
| group_id | INTEGER, FK | Grupul asociat |
| description | TEXT | Descrierea cheltuielii |
| amount | REAL | Suma in RON |
| paid_by | INTEGER, FK | Utilizatorul care a platit |
| expense_date | TEXT | Data cheltuielii |

## 3. Diagrama relatiilor

<img width="1054" height="752" alt="image" src="https://github.com/user-attachments/assets/8033396a-2a79-44cb-9c71-2bfb3250292e" />

## 4. Relatii importante

- Un utilizator poate crea mai multe grupuri.
- Un grup poate avea mai multi membri.
- Un utilizator poate apartine mai multor grupuri.
- Un grup poate avea mai multe sarcini.
- O sarcina poate fi atribuita unui membru al grupului.
- Un grup poate avea mai multe liste de cumparaturi.
- O lista poate contine mai multe produse.
- Un grup poate avea mai multe cheltuieli.

## 5. Endpoint-uri API propuse

Backend-ul va expune un API REST care utilizeaza cereri HTTP si raspunsuri JSON.

### 5.1 Autentificare

| Metoda | Endpoint | Descriere |
|---|---|---|
| POST | /api/auth/register | Crearea unui cont |
| POST | /api/auth/login | Autentificare |
| POST | /api/auth/logout | Deconectare |

### 5.2 Grupuri

| Metoda | Endpoint | Descriere |
|---|---|---|
| GET | /api/groups | Lista grupurilor utilizatorului |
| POST | /api/groups | Crearea unui grup |
| GET | /api/groups/:id | Detaliile unui grup |
| POST | /api/groups/:id/members | Adaugarea unui membru |

### 5.3 Sarcini

| Metoda | Endpoint | Descriere |
|---|---|---|
| GET | /api/groups/:id/tasks | Sarcinile unui grup |
| POST | /api/groups/:id/tasks | Crearea unei sarcini |
| PUT | /api/tasks/:id | Modificarea unei sarcini |
| PATCH | /api/tasks/:id/status | Actualizarea statusului |
| DELETE | /api/tasks/:id | Stergerea unei sarcini |

### 5.4 Liste de cumparaturi

| Metoda | Endpoint | Descriere |
|---|---|---|
| GET | /api/groups/:id/shopping-lists | Listele grupului |
| POST | /api/groups/:id/shopping-lists | Crearea unei liste |
| GET | /api/shopping-lists/:id/items | Produsele unei liste |
| POST | /api/shopping-lists/:id/items | Adaugarea unui produs |
| PUT | /api/shopping-items/:id | Modificarea unui produs |
| DELETE | /api/shopping-items/:id | Stergerea unui produs |

### 5.5 Calendar si cheltuieli

| Metoda | Endpoint | Descriere |
|---|---|---|
| GET | /api/groups/:id/calendar | Sarcinile cu termene-limita |
| GET | /api/groups/:id/expenses | Cheltuielile grupului |
| POST | /api/groups/:id/expenses | Inregistrarea unei cheltuieli |

## 6. Exemplu de cerere API

Pentru crearea unei sarcini, frontend-ul poate trimite:

POST /api/groups/1/tasks

Exemplu de date JSON:

```json
{
  "title": "Curatenie bucatarie",
  "description": "Curatarea bucatariei",
  "assigned_to": 2,
  "deadline": "2026-11-20"
}
```

Backend-ul verifica daca utilizatorul este autentificat, daca apartine grupului si daca datele sunt valide.

Dupa salvare, returneaza un raspuns JSON care contine sarcina creata.

## 7. Reguli de validare si acces

- Emailul trebuie sa fie unic.
- Parolele nu sunt stocate in text simplu.
- Un utilizator poate consulta doar datele grupurilor din care face parte.
- Responsabilul unei sarcini trebuie sa fie membru al grupului.
- Cantitatea produselor trebuie sa fie pozitiva.
- Sumele cheltuielilor trebuie sa fie pozitive.
- Backend-ul verifica datele inainte de salvare.

## 8. Observatii

Modelul prezentat este preliminar.

Calendarul foloseste termenele-limita din tabelul tasks, fara a necesita un tabel separat.

Functionalitatile principale vor fi implementate cu prioritate, iar calendarul si cheltuielile pot fi dezvoltate ulterior.
