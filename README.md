Prima aplicație Docker

Scop

Aceasta lucrare de laborator familiarizează cu elementele de bază ale containerizării și pregătește spațiul de lucru pentru următoarele lucrări de laborator.

Sarcina

Instalarea Docker Desktop și verificarea funcționării acestuia.

Descărcam și instalam Docker Desktop.

![418359231-e5f388a4-5a82-47a0-82b7-f5ff04c79407](https://github.com/user-attachments/assets/7fd268e7-accb-4e57-aaba-8b75ec16a773)

Executare

Creaam un repozitoriu containers02 și il clonam pe computerul nostru.

Creaam în directorul containers02 fișierul Dockerfile cu următorul conținut:

FROM debian:latest

COPY ./site/ /var/www/html/

CMD ["sh", "-c", "echo hello from $HOSTNAME"]

![418359386-8ea84619-5166-4944-9737-5d8f0b3c4e1d](https://github.com/user-attachments/assets/2d757d5c-8d2d-496f-b5bc-a16e96db343e)

În aceeași director de proiect creaam directorul site. În noul director creaan fișierul index.html cu conținut arbitrar.

![418359405-05c65dc9-2d45-4aa5-bb15-5bc6ac2e9924](https://github.com/user-attachments/assets/88599393-7f70-4c59-8a0e-a946e6d2fcfb)

Pornire și testare

Deschidem terminalul în directorul containers02 și executam comanda:

docker build -t containers02 .

![418359449-238f3167-54e6-4fb6-98a4-0f186fb09675](https://github.com/user-attachments/assets/62d73d2b-aa1d-4d24-80dc-c42c47979ad9)

Cât timp a durat crearea imaginii?

Crearea imaginii a durat 4.9 secunde.

Executam comanda pentru a porni containerul:

docker run --name containers03 containers02

![418359516-e1cfa963-59a9-4cf0-a8d5-ec437a979d59](https://github.com/user-attachments/assets/9199f3a7-c635-407a-962a-0df834633417)

Ce a fost afișat în consolă?

In consola a fost afisat mesajul: hello from 2F3566403ec4

Ștergem containerul și il pornim din nou, executând comenzile:

docker rm containers02

docker run -ti --name containers02 containers02 bash

![418359769-b878ea9c-eab5-458a-9d01-da51a50d66e3](https://github.com/user-attachments/assets/c969178c-1fcd-4982-88de-dd59f263ffbf)

În fereastra deschisă, executam comenzile:

cd /var/www/html/

ls -l

Ce este afișat pe ecran?

Pe ecran este afisat fisierul index.html cat si permisinulie acestuia si dimensiunea totală a fișierelor din director

Închidem fereastra cu comanda exit.

Concluzii

Am învățat cum să instalăm și să configurăm Docker Desktop.

Am creat și rulat un container simplu bazat pe Debian.

Am folosit un Dockerfile pentru a copia fișiere într-un container.

Am verificat conținutul containerului și am confirmat că fișierele au fost copiate corect.

Această experiență ne oferă o bază solidă pentru lucrări ulterioare legate de containerizare.

Bibliografie

Docker Documentation

