---
theme : "white"
highlightTheme: "vs"
customTheme : "novanet-theme"
---

<img src="https://julekalender.novanet.no/images/NN_Logo_Liten_RGB.svg" alt="novanet-logo" class="logo">

## Feature toggles

Olav Nybø

---

## Hva er en feature toggle?
<br/>

```cs
  if( MyAwesomeNewFeature.IsEnabled ) 
  {
      // Do the new awesome thing
  }
  else
  {
      // Keep doing the old stuff
  }
``` 

---

## Hva bruker vi dem til?

<ul>
    <li>release toggles </li>
    <ul class="subitem"> <li >styre hva som inkluderes i en release</li> </ul>
    <li>experiment toggles</li>
    <ul class="subitem"> <li >teste ut effekten av features</li> </ul>
    <li>ops toggles</li>
    <ul class="subitem"> <li >black friday</li> </ul>
    <ul class="subitem"> <li >gradvis utrulling</li> </ul>
    <li>permission toggles</li>
    <ul class="subitem"> <li >styre tilgang features</li> </ul>
</ul>

---

##### Release toggles - Trunk based development Vs Feature branching

<img src="images/feature-branch.png" alt="feature branches" >

--

## Trunk based development

<img src="images/trunk-based.png" alt="trunk based image" >

---

## Konfigurasjon av toggles

- Hardkoding
- Command line
- Konfigurasjonsfil 
- Applikasjons Databasen
- Konfigurasjonssystem (Launchdarkly, Unleash, Consul, Etcd, Zookeeper)
- Overstyre konfigurasjon 

--

## Hardkoding

```console

  const bool EnableFeatureA = true;

  if (EnableFeatureA)
  {
      //do it
  } 
``` 

--

## Command line

```console
  $ my_application.exe --enableFeatureA 
``` 

--

## Konfigurasjonsfil

appsettings.json
```json
  {
    "FeatureToggle": {
        "FeatureA": "true",
        "FeatureB": "false"
    },
  }
``` 

--

## Release toggles
Statisk konfigurasjon - appsettings.json

## Andre toggles
Konfigurasjonssystem

--

## Konfigurasjonssystem (Launchdarkly, Unleash, KV-store)

<img src="images/unleash.png" alt="unleash" >

--

Hva skal jeg bruke da?

<img src="https://media.giphy.com/media/3o7aTskHEUdgCQAXde/giphy.gif" alt="question" >

It depends <!-- .element: class="fragment current-visible" -->

--

<img src="images/feature-toggles.jpg" alt="feature toggles" >

<aside class="notes">
- Uferdig kode som deployes til produksjon
- Ikke testet
- Må ikke aktiveres før den er godkjent
</aside>

--

<img src="images/unleash.png" alt="unleash" width="400" style="margin-right: 40px;">
<img src="images/minesweeper.gif" alt="feature branches" width="200"> 

---

## Bruk med måte

<div style="font-size: 40%;"> 
    <span>FeatureA(on/off)</span>
    <span style="font-weight: bold;"> X </span>
    <span>FeatureB(on/off)</span>
    <span style="font-weight: bold;"> X </span>
    <span>FeatureC(on/off)</span>
    <span style="font-weight: bold;"> X </span>
    <span>FeatureD(on/off) ..... </span>
</div>

<img src="images/exponential.png" alt="exponential growth" height="400">

---

## Teknisk gjeld
<img src="https://media.giphy.com/media/GVQ7PkscQwk3S/giphy.gif" alt="teknisk gjeld"> 

Rydding av gamle toggles blir en kontinuerlig prosess

---

## Oppsummering

- Et av flere verktøy for å kunne gjøre kontinuerligleveranse med Trunk based development
- Muliggjør frikobling av deploy og aktivering av features
- Ingen silver bullet

