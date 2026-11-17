# Aktivitetsaksjonen

Repository for kildekode og resultater fra aktivitetsaksjonen 2.0 i Helsedirektoratet.

## Akvtivitetsaksjonen 2.0

### Kravspesifikasjon

Behov og krav for løsningen.

* Bør kunne sortere resultatlister på tid og distanse  
* Bør støtte opprettelse av lag og lagkonkurranser i appen  
* Bør integrere med de vanligste appene og treningsdingsene som de ansatte bruker til å registrere trening og aktivitet  
  * Garmin
  * Polar
  * Wahoo
  * Apple Watch  

### Forslag til løsning

Benytte [OpenAthlete](https://openathlete.org/) som grunnleggende plattform. Lage en lokal løsning for resultatlister som benytter OpenAthlete sitt API for å hente data, organisere lag(?) og sette opp resultatlister. Open Athlete integrerer mot Garmin, Polar, Corus, Suunto og Strava (men mangler Wahoo). Det er også egen app for Android (IOS kommer).

* Bruke [Club API](https://api.openathlete.org/docs#/Clubs) for å hente data til resultatlister?
* Bruke [Coach API](https://api.openathlete.org/docs#/Coach) for å hente data til resultatlister?
* Bruke [Groups API](https://api.openathlete.org/docs#/Athlete%20groups) for å håndtere grupper i klubben?

### Noen begrensninger

PROBLEM: Coacher i klubben kan tilsynelatende ikke også være atleter i klubben og blir derfor ikke med i coach-dashboard for klubben.

* Mulig løsning: ha en egen OpenAthlete bruker som coach i klubben.
* Mulig løsning: Sjekke om man kan legge til coacher til grupper via API'et.

PROBLEM: Det er ikke noe felles klubb dashboard tilgjengelig for klubbens medlemmer, dette må vi bygge selv.

* Lage et eget klubb dashboard på Github

PROBLEM: Det er ikke noen høydemeter med i club-dashboard statistikken.

* Mulig løsning, se på hver enkelt aktivitet den gjeldende uken for å regne sammen metrics (høydemeter).

PROBLEM: Ingen gruppeadministrasjon som fungerer for medlemmer i en klubb

* Knytte gruppeadministrasjon til en ekstern applikasjon?
