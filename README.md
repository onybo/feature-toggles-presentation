# feature-toggles-presentation
Foredrag om Feature Toggles

## Hva er en feature toggle (1)
## Komponentene i en feature toggle (2)
- Toggle point
- Toggle router/strategy
- Toggle context
- Toggle configuration

## Hvordan feature toggles kan brukes 
- Release toggles (3)
<br/>Alternativ til feature branches.
- Experiment toggles (4)
<br/>A/B testing. Formål å se effekt av alternative løsninger
- Ops toggles (5)
<br/> Testing i prod, Kill switch, Performance
- Permission toggles (6)
<br/> Skru features av og på for forskjellige grupper av brukere.

## Dynamikk og levetid
- dynamikk (7)
<br/> statisk endre bare ved deploy, endre via konfigurasjonsendring, dynamisk av/på vurderes pr. request 
- levetid (8)
<br/> release toggles må fjernes, permission toggles kan leve evig

## Typer av toggle strategies/routers (fra unleash) Tror dette blir for mye, men bør kanskje nevne noen eksempler
- userWithId
- gradualRolloutUserId
- gradualRolloutSessionId
- gradualRolloutRandom
- remoteAddress
- applicationHostname

## Decoupling i kode (si noe om dette?)

## Konfigurasjons Management
- Hardkoding
- Parametrisert/command line argumenter
- Konfigurasjonsfil (web.config/app.config)
- Applikasjons Databasen
- Konfigurasjonssystem (Launchdarkly, Unleash, Consul, Etcd, Zookeeper)
- Overstyre konfigurasjon
<br/> sende av/på i en cookie, sikkerhet om en gjør det

## Dokumentasjon
- tjenester kan implementere API som sier noe om hvilke flags de bruker
- toggles som skal brukes av andre enn utviklerene f.eks. ops og permission toggles må dokumenteres

