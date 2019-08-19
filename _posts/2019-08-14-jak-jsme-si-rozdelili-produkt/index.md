---
layout: post
title: "#MěnímeHeureku - Jak jsme si rozdělili produktové oblasti do týmů?"
permalink: /menimeheureku-jak-jsme-si-rozdelili-produktove-oblasti-do-tymu/
date: 2019-08-19 13:00:00 +0200
author: Pavel Škoda
tags: [MěnímeHeureku, OnePlatform, microservices, architektura, vývoj, produkt]
categories: [blog]
imageUrl: /assets/jak-jsme-si-rozdelili-produkt/workshop.jpg
---
Před nějakou dobou jsme v Heurece přestavěli rozložení týmů tak, aby každý spravoval nějakou produktovou oblast. Do té doby jsme totiž měli v každém městě (tehdy Praha a Liberec) jeden frontendový a jeden backendový tým. Místo toho jsme se rozhodli postavit týmy okolo jednotlivých produktů, takže si každý vývojář mohl vybrat, která část Heureky ho nejvíce zajímá a vytvořit okolo ní společně s dalšími tým.

Náš tým si například vybral oblast, kterou jsme pojmenovali “Cesta k produktu” a naší odpovědností se tedy stalo provést uživatele na Heurece výběrem toho správného produktu pro jeho potřeby.

Pro představu, existuje další tým, jehož produktová oblast se nazývá “Nákup produktu”. Tento tým se stará o to, aby uživatel, který již tuší jaký produkt by si chtěl koupit, dostal informace o nejlepší ceně, recenzích a eshopech kde se daný produkt dá koupit.


## Jak to funguje v praxi?

V praxi to funguje tak, že náš tým vyvíjí landing page Heureky a výpis kategorie či vyhledávání spolu s různými filtry, tak aby dovedl uživatele na detail produktu.

Zde si uživatele převezme další tým a snaží se ho provést přes výpis jednotlivých nabídek od obchodů až k samotnému nákupu.

Další tým má na starosti katalog a stará se o naši ohromnou databázi nabídek, produktů, kategorií a relací mezi nimi. Také řeší zpracování feedů od obchodů a plní jimi tento katalog. Data z katalogu pak přes různá API poskytuje ostatním týmům, abychom je mohli zobrazit.

Takhle bych mohl pokračovat ještě dlouho. Máme tým na získávání a zpracování recenzí, tým na aplikace pro komunikaci s eshopy, tým který se stará o mobilní aplikaci a v neposlední řadě infrastrukturní tým, který všemu tomu buduje základy.


## V čem nám to nejvíce pomáhá?

Tohle rozdělení nám pomohlo předcházet mnoha problémům. Hned zprvu je jasně daná odpovědnost za jednotlivé části produktu, a tak každý hned ví, za kým jít, pokud má například nápad na konkrétní vylepšení, nebo pokud něco nefunguje.

Velkou výhodu to má také pro produkťáky, kteří se mohou soustředit jen na jednu svou doménu, a nemusí pořád přepínat kontext mezi několika projekty.

Navíc se produkťák stal pevnou součástí týmu. Do té doby to totiž leckdy vypadalo tak, že v produktovém oddělení se něco uvařilo a pak se to poslalo do vývojového oddělení, kde nikdo neměl sůl na dochucení, ani příbory aby to mohl sníst.

Naše týmy už tedy nejsou čistě frontendové a backendové, ale pokrývají vždy celou oblast. Proto se snažíme, aby tým jako celek byl univerzální.

Není nutné, aby každý člen rozuměl od operations přes databáze, backend frontend až po nejnovější trendy v Javascriptu. Takové lidi bychom nejspíš ani nenašli. Snažíme se však, abychom v rámci většiny týmů měli tyto oblasti pokryté. Takže se pak skládají z vývojářů kteří mají blíž k tomu jaká je zrovna teplota v serverovně i z těch, které víc zajímá, jak svítí pixely u uživatele na obrazovce.


## Straší nám tu monolit

Samozřejmě není vše jen růžové. Bylo například potřeba, aby si nové týmy navzájem předali služby a aplikace, které předtím v mnoha případech vůbec nevyvíjeli. Navíc nám tu pořád straší jedna velká monolitická aplikace, která pokrývá více oblastí, takže takřka všechny týmy sdílí jednu legacy codebase a někdy si sahají pod ruce.

Už to ale praktikujeme více než rok, a po té co si vše sedlo můžeme s jistotou říct, že není potřeba zavírat frontenďáky do jedné a backenďáky do druhé místnosti. Oni sice většinou každý vládnou jiným jazykem, ale nakonec se vždycky domluví.


![Workshop, Liberec 2018](/assets/jak-jsme-si-rozdelili-produkt/workshop.jpg)