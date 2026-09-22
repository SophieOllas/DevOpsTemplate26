## Steg 1

1. FROM python:3.12-slim

2. För att försnabba processen när docker byggs upp. Den måste inte bygga om requirements.txt varje gång.

3. Nej

Testa portet:
![](m3_steg1.1.png)
![](m3_steg1.2.png)

## Steg 3

Vi körde appen med docker compose och öppna den på port 8080 på webbläsaren.

![](m3_steg3.1.png)

Tjänsterna visa 200 OK i terminalen under docker compose up.

![](m3_steg3.2.png)


## Steg 4

Sophie gjorde för backenden en .dockerignore fil, som bl.a. ignorer cache filer. Före .dockerignore filen:

![](m3_steg4_findbefore_so.png)

Efter .dockerignore filen:

![](m3_steg4_findafter_so.png)

Samma för Willem:

![](m3_steg4_findbefore_wg.png)
![](m3_steg4_findafter_wg.png)

## Steg 5

Vi generera en token enligt instruktionerna och logga in med commandon:

export CR_PAT=<er-token>
echo $CR_PAT | docker login ghcr.io -u <ert-användarnamn> --password-stdin

Och så gjorde vi docker compose build. Här ser man på Package fliken det som pushades:

![](m3_steg5_so.png)