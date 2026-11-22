---
layout: post
title: mappatura dei rifugi climatici in Italia · mapping climate shelters in Italy
date: 2026-11-22
description: 187 comuni con un'iniziativa attiva, 70 in progettazione, 1776 luoghi · 187 municipalities with an active initiative, 70 in planning, 1776 places
tags: [climate-shelters]
categories: []
thumbnail: assets/img/blog/rifugi-climatici/comuni_it.png
---

<style>
  .lang-switch { display: inline-flex; border: 1px solid var(--global-theme-color, #b509ac); border-radius: 4px; overflow: hidden; margin-bottom: 1.5rem; }
  .lang-switch button { background: none; border: 0; padding: 0.25rem 0.9rem; font-size: 0.9rem; color: var(--global-theme-color, #b509ac); cursor: pointer; }
  .lang-switch button[aria-pressed="true"] { background: var(--global-theme-color, #b509ac); color: var(--global-bg-color, #fff); }
  html[data-lang="it"] .lang-en, html[data-lang="en"] .lang-it { display: none; }
  html:not([data-lang]) .lang-switch { display: none; }
</style>

<div class="lang-switch" role="group" aria-label="Lingua · Language">
  <button type="button" data-set-lang="it" aria-pressed="false">IT</button>
  <button type="button" data-set-lang="en" aria-pressed="false">EN</button>
</div>

<div class="lang-it" lang="it" markdown="1">

In collaborazione con ANCI (Associazione Nazionale dei Comuni Italiani), stiamo mappando le iniziative di rifugi climatici nei comuni italiani,
combinando la ricerca sui siti web comunali con un questionario.

## i comuni

Ad oggi abbiamo individuato 187 comuni con un'iniziativa di rifugi climatici attiva e 70 con un'iniziativa in progettazione.

<div class="row mt-3 justify-content-center">
<div class="col-md-10">
{% include figure.liquid loading="eager" path="assets/img/blog/rifugi-climatici/comuni_it.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Mappa dei comuni italiani con iniziative di rifugio climatico: 187 attive, 70 in progettazione" %}
</div>
</div>

## i luoghi

All'interno di queste iniziative abbiamo localizzato 1776 luoghi, inclusi i cold spot indicati da ATS/ASST in Lombardia.

<div class="row mt-3 justify-content-center">
<div class="col-md-10">
{% include figure.liquid path="assets/img/blog/rifugi-climatici/luoghi_it.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Mappa dei 1776 rifugi climatici in Italia, con i cold spot ATS/ASST in Lombardia" %}
</div>
</div>

## contatti

Contattami (catarina.midoes@cmcc.it) per segnalare l'iniziativa del tuo comune o ricevere aggiornamenti sulla mappatura. Altri progetti:
[rifugi climatici](/climate-shelters/it/).

</div>

<div class="lang-en" lang="en" markdown="1">

In collaboration with ANCI (Associazione Nazionale dei Comuni Italiani), we are mapping climate shelter initiatives in Italian municipalities,
combining a search of municipal websites with a survey.

## the municipalities

So far we have identified 187 municipalities with an active climate shelter initiative and 70 with one in planning.

<div class="row mt-3 justify-content-center">
<div class="col-md-10">
{% include figure.liquid loading="eager" path="assets/img/blog/rifugi-climatici/comuni_en.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Map of Italian municipalities with climate shelter initiatives: 187 active, 70 in planning" %}
</div>
</div>

## the places

Within these initiatives we have located 1776 places, including the cold spots designated by ATS/ASST in Lombardy.

<div class="row mt-3 justify-content-center">
<div class="col-md-10">
{% include figure.liquid path="assets/img/blog/rifugi-climatici/luoghi_en.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Map of 1776 climate shelters in Italy, with ATS/ASST cold spots in Lombardy" %}
</div>
</div>

## contact

Get in touch (catarina.midoes@cmcc.it) to tell us about your municipality's initiative or to receive updates on the mapping. More projects:
[climate shelters](/climate-shelters/).

</div>

<script>
  (function () {
    var titles = { it: "mappatura dei rifugi climatici in Italia", en: "mapping climate shelters in Italy" };
    var root = document.documentElement;
    function setLang(lang, save) {
      root.setAttribute("data-lang", lang);
      document.querySelectorAll("[data-set-lang]").forEach(function (b) {
        b.setAttribute("aria-pressed", b.getAttribute("data-set-lang") === lang ? "true" : "false");
      });
      var h1 = document.querySelector(".post-title");
      if (h1) h1.textContent = titles[lang];
      document.title = document.title.replace(/^[^|]*/, titles[lang] + " ");
      if (save) {
        try { localStorage.setItem("post-lang", lang); } catch (e) {}
        try { history.replaceState(null, "", "?lang=" + lang); } catch (e) {}
      }
    }
    var fromUrl = new URLSearchParams(location.search).get("lang");
    var saved = null;
    try { saved = localStorage.getItem("post-lang"); } catch (e) {}
    var browser = (navigator.language || "").toLowerCase().indexOf("it") === 0 ? "it" : "en";
    var lang = fromUrl === "it" || fromUrl === "en" ? fromUrl : saved === "it" || saved === "en" ? saved : browser;
    setLang(lang, false);
    document.querySelectorAll("[data-set-lang]").forEach(function (b) {
      b.addEventListener("click", function () { setLang(b.getAttribute("data-set-lang"), true); });
    });
  })();
</script>
