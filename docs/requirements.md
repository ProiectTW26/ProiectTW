# Cerințele aplicației TogetherPlan

## 1. Scop

TogetherPlan este o aplicație web destinată organizării activităților cotidiene în grup. Utilizatorii pot gestiona sarcini, liste de cumpărături, evenimente și cheltuieli comune.

## 2. Cerințe funcționale

| Cod | Cerință | Prioritate |
|---|---|---|
| CF1 | Utilizatorul poate crea un cont și se poate autentifica. | Obligatorie |
| CF2 | Utilizatorul poate crea și gestiona un grup. | Obligatorie |
| CF3 | Utilizatorul poate adăuga, modifica și șterge sarcini. | Obligatorie |
| CF4 | Utilizatorul poate atribui sarcini membrilor grupului. | Obligatorie |
| CF5 | Utilizatorul poate marca sarcinile ca finalizate. | Obligatorie |
| CF6 | Membrii grupului pot crea și modifica liste comune de cumpărături. | Obligatorie |
| CF7 | Utilizatorul poate vizualiza activitățile într-un calendar. | Secundară |
| CF8 | Utilizatorul poate înregistra și consulta cheltuielile comune. | Secundară |

## 3. Cerințe nefuncționale

| Cod | Cerință | Prioritate |
|---|---|---|
| CNF1 | Interfața trebuie să fie simplă și ușor de utilizat. | Obligatorie |
| CNF2 | Aplicația trebuie să poată fi utilizată pe calculator și telefon. | Obligatorie |
| CNF3 | Parolele trebuie stocate securizat, folosind hashing. | Obligatorie |
| CNF4 | Utilizatorii trebuie să poată accesa doar datele grupurilor din care fac parte. | Obligatorie |
| CNF5 | Datele trebuie păstrate într-o bază de date. | Obligatorie |
| CNF6 | Operațiile obișnuite trebuie să ofere un răspuns în maximum 3 secunde, în condiții normale de testare. | Secundară |

## 4. Prioritizarea cerințelor

Cerințele obligatorii vor fi implementate în prima versiune funcțională a aplicației (prototip).

Acestea includ autentificarea, gestionarea grupurilor, sarcinilor și listelor colaborative.

Cerințele secundare, precum calendarul și evidența cheltuielilor, vor fi implementate ulterior, dacă timpul permite.

## 5. Delimitarea proiectului

Aplicația este destinată grupurilor mici, precum studenți, colegi de apartament și familii.

Prima versiune nu va include:
- Plăți online.
- Integrare cu aplicații bancare.
- Rezervări online.
- Notificări prin SMS.
- Integrare cu servicii externe de calendar.

Aceste funcționalități pot fi analizate pentru versiuni viitoare.
