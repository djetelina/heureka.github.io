---
layout: post
title: "#MěnímeHeureku - chystáme mezinárodní #OnePlatform"
permalink: /menimeheureku-chystame-mezinarodni-oneplatform/
date: 2019-08-04 8:21:10 +0200
author: Lukáš Putna
tags: [MěnímeHeureku, OnePlatform, microservices, architektura, backend, okr]
categories: [blog, kod]
imageUrl: /assets/menimeheureku-chystame-mezinarodni-oneplatform/oneplatform1.jpg
---

Poslední dva roky máme na vývoji Heureky hodně napilno. Zkoušíme různé technologie v rámci nové architektury, měníme způsob řízení produktové i technologické inovace,… A to vše zapadá do toho, jak vymýšlíme nové varianty spolupráce nás všech ve firmě. Postupně se nám to daří a nyní je před námi velký úkol: **Povýšit Heureku na mezinárodní laťku.**

## Vypořádání se s monolitem

Heureka letos oslaví 12 let. Zatímco pro uživatele a e-shopy to je skvělá zpráva, pro nás na vývoji je to spíš důvod k pláči. Proč? Protože stejnou dobu existují některé klíčové části našeho kódu. Ještě relativně nedávno byla Heureka čistě monolitická aplikace, skrývající v sobě spoustu zamotaného kódu. Zkuste si pak dělat rychlé technologické nebo produktové inovace. Nemožné. Vlastně se nám jejich vývoj prodlužoval natolik, že jsme je nestíhali efektivně dostávat do produkce. S tím jsme se nemohli jen tak smířit. 

Když jsme se s týmem na celou situaci před dvěma roky koukali, říkali jsme si, že by bylo ideální přepsat celou Heureku znovu na zelené louce. Ukázalo se, že naše oblíbené tvrzení, že náš produkt nemůže nikdo zkopírovat, protože je v této fázi již nereprodukovatelný, je limitem i pro nás samotné. Ani my sami totiž nedokážeme Heureku jen tak celou přepsat. Jedním z reálných řešení byla postupná změna architektury na něco, co je dlouhodobě škálovatelné a robustní v různých ohledech.

Když se v dnešní době rozhodujete, jak změnit architekturu vaší služby, není vůbec těžké **zvolit si architekturu mikroservis.** Často je to jasná volba při cestě od monolitu. O to horší to ale bylo s realizací. Nevěděli jsme, jak na to. Nedokázali jsme definovat priority, nevěděli jsme, co přesně to přinese… A už vůbec jsme nevěděli, jak rozdělit monolitický kód na oblasti, které by pak dostaly na starosti konkrétní týmy. Prostě jsme nevěděli, jak to poskládat tak, aby různé týmy nemusely jako doposud řešit každý měsíc jiný projekt a s ním tedy i jinou část kódu.

## OKR v pravý čas

Naštěstí zhruba před rokem a půl přišel nový šéf produktu Marek s představou, jak by chtěl řídit produktový rozvoj. Znamenalo to mimo jiné i zrušení roadmap a termínů, jak jsme je do té doby znali. Na to, jak velké změny přinesl, to neměl s přesvědčováním ostatních vůbec těžké. Jeho představa totiž přesně zapadala do potřeb a představ vývoje o technologickém pokroku.

A tak se stalo, že už více než rok řídíme a prioritizujeme produktový i technologický rozvoj na Česko zatím celkem netradičně: Bez komplexních roadmap a definování konkrétních projektů a termínů managementem. To rovnou přeskakujeme. A přitom se řídíme jinak vlastně jednoduchou a geniální myšlenkou. Rozhodujeme se čistě jen na základě metrik, co nám která iniciativa přinese. V praxi to pak vypadá tak, že víme, v jaké oblasti potřebujeme něco vylepšit. Například chceme zlepšit konverzní poměr nabídek v produktovém detailu. Ale jak na to půjdeme, co se musí změnit a kolik času tomu chceme věnovat, s tím si už musí kompletně poradit tým. Jediným zadáním je výsledek. Součástí celého úkolu je i discovery fáze, kde do hloubky prověřujeme navrhovaná řešení. Díky tomu programujeme jen to, co dává opravdu smysl a má největší přínos. 

Tahle naše cesta není nic nového, námi vymyšleného. Jmenuje se to [OKR](https://en.wikipedia.org/wiki/OKR) - Objectives and Key Results - a používají je ty nejúspěšnější světové online firmy jako Google, Netflix nebo Twitter. Nejen vývojové týmy díky OKR přístupu přirozeně vlastní stabilní produktové i technické oblasti, skrze které pak dlouhodobě přispívají k realizaci společné předem definované firemní vize. Zároveň to velmi úzce souvisí se stabilním rozdělením mikroslužeb na vývojové týmy.

Pro celý systém používání OKR je klíčová samostatnost a autonomie týmů. Nikdo týmům neříká, co přesně mají udělat. Důležitá rozhodnutí často dělají právě lidé v týmech. Oni jsou dané oblasti nejblíže a mají v ní často větší expertízu a prostor pro discovery, než manažeři vysedávající po schůzkách v zasedačkách. Ti díky OKR získávají čas na řešení vize a budoucnosti nejen svých týmů, ale především celé firmy.

##  Stavíme mezinárodní #OnePlatform

Pod Heureka Group v tuto chvíli spadá celkem 9 srovnávačů a nákupních rádců ve střední a východní Evropě. Naše jednoznačná příležitost je spojení těchto platforem v jednu. Slibujeme si od toho nejen nové byznysové možnosti, ale také mnohem rychlejší produktové inovace do budoucna. Díky #OnePlatform dokážeme výrazně rozšířit naši produktovou nabídku ve všech těchto zemích. Jen si představte to množství recenzí, které budeme moci sdílet. Nebo to, jak jednoduše budou moct e-shopy prodávat své zboží v zahraničí pomocí mezinárodního marketplace (aktuálně Heureka Košík). A o tom, jak rozšíříme naše datové možnosti, se snad nemusím ani zmiňovat.

Abychom se k této vizi posunuli, aktuálně rozšiřujeme architekturu mikroservis, stanovování cílů pomocí OKR a týmy vlastnící ucelené oblasti rozšiřujeme na mezinárodní úroveň. Tento framework je totiž skvěle škálovatelný a máme s ním už spoustu zkušeností (ať pozitivních nebo negativních). Určitě se můžete těšit na další podrobnosti. Prozatím nám držte palce!

![Heureka Group, 3 platformy, 9 států](/assets/menimeheureku-chystame-mezinarodni-oneplatform/heureka-group.jpg)

![Oneplatform workshop, Vranov nad Dyjí 2019](/assets/menimeheureku-chystame-mezinarodni-oneplatform/oneplatform1.jpg)