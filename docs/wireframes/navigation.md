# Wireframe-uri – TogetherPlan

## 1. Descriere

Acest folder conține wireframe-urile principalelor ecrane ale aplicației TogetherPlan.

Wireframe-urile sunt realizate în HTML și CSS și prezintă structura interfeței, poziționarea elementelor și navigarea propusă.

Acestea reprezintă schițe ale aplicației, nu pagini complet funcționale. Datele afișate sunt exemple.

## 2. Ecranele aplicației

| Ecran | Descriere |
|---|---|
| [Autentificare](login.html) | Introducerea emailului și parolei. |
| [Înregistrare](register.html) | Crearea unui cont nou. |
| [Pagina principală](dashboard.html) | Prezentarea grupurilor și sarcinilor recente. |
| [Grupuri](groups.html) | Crearea și vizualizarea grupurilor. |
| [Sarcini](tasks.html) | Adăugarea, atribuirea și gestionarea sarcinilor. |
| [Cumpărături](shopping.html) | Gestionarea listelor comune de cumpărături. |
| [Calendar](calendar.html) | Vizualizarea activităților și termenelor-limită. |
| [Cheltuieli](expenses.html) | Înregistrarea și consultarea cheltuielilor comune. |

## 3. Fluxurile de navigare

### Fluxul 1 – Autentificare

1. Utilizatorul accesează pagina de autentificare.
2. Introduce emailul și parola.
3. După autentificarea reușită, este redirecționat către pagina principală.
4. Dacă nu are cont, poate accesa pagina de înregistrare.

Flux propus:

login.html → dashboard.html

Alternativ:

login.html → register.html → dashboard.html

### Fluxul 2 – Crearea unui grup

1. Utilizatorul accesează pagina principală.
2. Selectează secțiunea „Grupuri”.
3. Completează numele unui grup nou.
4. Apasă „Creează grup”.
5. După salvare, grupul apare în lista grupurilor existente.

Flux propus:

dashboard.html → groups.html

### Fluxul 3 – Gestionarea sarcinilor

1. Utilizatorul accesează secțiunea „Sarcini”.
2. Selectează grupul.
3. Completează informațiile despre sarcină.
4. Selectează responsabilul.
5. Salvează sarcina.
6. Sarcina apare în lista grupului și poate fi ulterior finalizată, modificată sau ștearsă.

Flux propus:

dashboard.html → tasks.html

Alternativ:

groups.html → tasks.html

### Fluxul 4 – Liste colaborative

1. Utilizatorul accesează secțiunea „Cumpărături”.
2. Selectează grupul și creează o listă.
3. Adaugă produse și cantități.
4. Alți membri ai grupului pot consulta și modifica lista.
5. Produsele cumpărate pot fi marcate ca finalizate.

Flux propus:

dashboard.html → shopping.html

### Fluxul 5 – Calendar și cheltuieli

Utilizatorul poate accesa calendarul pentru a consulta termenele-limită ale sarcinilor.

De asemenea, poate accesa secțiunea „Cheltuieli” pentru a consulta sau înregistra cheltuieli comune.

Fluxuri propuse:

dashboard.html → calendar.html

dashboard.html → expenses.html

## 4. Meniul de navigare

După autentificare, utilizatorul va avea acces la un meniu lateral cu următoarele secțiuni:

- Acasă
- Grupuri
- Sarcini
- Cumpărături
- Calendar
- Cheltuieli
- Deconectare

Meniul permite trecerea între paginile principale ale aplicației.

## 5. Limitări

Wireframe-urile nu sunt conectate la o bază de date și nu realizează operații reale de autentificare sau salvare.

Unele linkuri permit simularea navigării între pagini, însă butoanele pentru crearea și modificarea datelor sunt doar reprezentative.

Funcționalitățile vor fi dezvoltate în etapa de implementare a aplicației.
