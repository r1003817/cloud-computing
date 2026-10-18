# Storingsmelder R1003817

##Een klein meldingensysteem voor storingen. Je meldt een storing via een
formulier, je ziet de openstaande meldingen in een lijst, en je sluit ze af als
ze opgelost zijn.


## Benodigdheden

##Om de applicatie te kunnen starten heb je nodig:

- Docker Desktop (met Docker Compose)
- Git

##Zorg dat Docker Desktop aanstaat voordat je begint.

## Installatie

### 1. Repository downloaden

##Open PowerShell en voer uit:

commando --> git clone https://github.com/r1003817/cloud-computing.git
commando --> cd cloud-computing


### 2. Database instellen

##aak een `.env`-bestand met de inhoud van `.env.example`:

##Open het bestand en vul de gegevens in:

POSTGRES_DB="storingen"
POSTGRES_USER="storing"
POSTGRES_PASSWORD=

##Kies zelf een wachtwoord en vul het in achter `POSTGRES_PASSWORD`. Sla het bestand daarna op.

### 3. Applicatie starten

##Start de applicatie en de database met:

commando --> docker compose up -d --build


##Controleer of beide containers draaien:

commando --> docker compose ps


##Open daarna in je browser:

http://localhost:8000

##Je kan nu storingen melden, bekijken en afsluiten.

## Controleren

##Om te controleren of de applicatie en database werken, ga naar:

http://localhost:8000/health

##Als alles werkt, krijg je `"status": "ok"`.

## Stoppen en opnieuw starten

##De containers stoppen:

commando --> docker compose down

##Opnieuw starten:

commando --> docker compose up -d --build

##De meldingen blijven bewaard in een Docker-volume voor PostgreSQL, ook wanneer de containers opnieuw aangemaakt worden.

##Gebruik geen `docker compose down -v` als je de gegevens wilt behouden, want daarmee verwijder je ook het volume.