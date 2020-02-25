---
layout: post
title: "Rozjezd provozního cechu, aneb obratnější než spajdrmen"
permalink: /rozjezd-provozniho-cechu/
date: 2020-02-26 12:00:00 +0200
author: David Jetelina
tags: agile guild operations spotify devops
categories: [blog]
imageUrl: /assets/rozjezd-provozniho-cechu/topics.jpg
---

Před půl rokem (a kousek) jsme se rozhodli inspirovat u Spotify a z velké části 
zkopírovat jejich organizační strukturu. 

S Triby moc problém nemáme, ty se hezky rozjíždí a do všeho nám zapadají. 
Vtipnější to je s námi vymyšlenými “technickými skupinkami” (někteří z nás je 
prostě nazývají guildami). Je to takový náš hybrid chapterů a guild. Což je 
kombinace dvou ne až tak kompatibilních uskupení. Například chapter u Spotify 
sídlí na stejném místě a jejich vedoucí jsou přímí nadřízení lidí uvnitř 
chapteru. Naopak guilda je spíš zájmová skupina, která si děla například 
konference a má jen koordinátory. 

Na chaptery, tak jak mají být podle Spotify, jsme zatím ještě moc malí, takže 
jsme se agilně dostali ke vzniku skupinek, které rozjíždíme Praha-Liberec-Plzeň 
(v budoucnu je výhled přibrat kolegy z Budapeště a Lublaně). 
A co jsme od nich čekali? Podrobně nespecifikované posouvání Heureky 
ve své oblasti. Což pro vybudování úvodní vlny nadšení a motivace stačilo. 
Jako vedoucí jednoho z těchto uskupení, kouzelně nazvaného operations, 
musím přiznat, že tento agilní přistup – vykopnout uskupení a nikdy mu 
nedefinovat pravomoce a zodpovědnost, ani dedikovaný čas – způsobuje jistou 
míru frustrace. Na druhou stranu nám to umožňuje pokusit se ušít řešení na 
míru našim problémům.

## Výkop – jednodenní workshop – HYPE
Začali jsme workshopem: místnost plná vývojářů a pět papírů na stolech. 
Kroužili jsme, bavili se o smyslu různých skupin a jejich náplni, 
dokud jsme se někde neusadili.

Nadefinovali jsme si čemu se budeme věnovat; naše pole expertízy v ideálním 
světě. Za operations to je:

* Víme, jak se aplikace chová (monitoring, logging, tracing...)
* Výpadek není překvapením (alerting, incident management, disaster recovery)
* Nasazování je pohoda (CI/CD, rollbacky, autoscaling)

Domluvili jsme se, že na začátku každého kvartálu přijdeme za produktovými 
týmy, odkud máme naše členy a vysvětlíme kolik, na co a proč potřebujeme 
kapacity vývojářů). 

## První iterace – 2020Q2 – a plav

Naše guilda měla hezky ambiciózní (tak jak to má být) plán OKR, tedy 
konkrétních cílů na následující kvartál. 

* Chtěli jsme připravit půdu pro vznik nástroje, který by nám byl schopný říct, 
kolik nás stojí výpadky našich služeb. Domluvit se na formátu, jak získat data 
od týmů a ty o to pak poprosit. 
* Dále jsme se chtěli postarat o to, že týmy přejdou na Promethea pro 
monitoring a že na alerty využívají OpsGenie namísto Slacku. 
* Třetí cíl bylo udělat discovery kolem deploymentu – naše aktuální řešeni 
úplně dokonale nezvládá rollbacky a špatně se debuguje. 

Na to vše jsme žádali pět dní pro každého člena (x6) plus 3 dny na pravidelnou 
měsíční schůzku. 

Ono se to nezdá jako moc, ale za kvartál má v ideálním případě každý vývojář 
jen 60 dní na svůj tým, realisticky to je 40-50. Z toho žádat o 8 není vůbec 
málo. Naštěstí v rozjezdu byly týmy vstřícné a s kapacitou nebyl problém. 
Problém nastal s využitím slíbené kapacity. Zjistili jsme, že když se každý 
problému věnuje úplně jiný měsíc a u toho sedí v jiném městě, efektivita dost 
pokulhává. Navíc když vývojář žije pro svůj produkt a je jím každodenně 
obklopen, tak potom čas věnovaný bokem může působit jako krádež tomu „hlavnímu“.

Reálně tedy kvartál dopadnul tak, že nám první bod přerostl přes hlavu, a i 
když jsme mu věnovali části našich pravidelných schůzek, výsledku jsme dosáhli 
s velice odřenýma ušima. Druhý bod jsme vyřešili zaúkolováním konkrétních týmů 
(a ne všechny jsme „uhlídali“). Na třetí bod se vůbec nedostalo. 

## Druhá iterace – 2020Q3 – znovu a lépe

Po delším přemýšlení jsem došel k závěru, že aby skupina cokoliv zvládla vytvořit efektivně, je potřeba být na jednom místě, v jeden čas a přestat měnit kontexty. Tuto teorii jsme se kolektivně rozhodli otestovat a vyjet v rámci jednoho z cílů na hackathon do Jizerek. 

Naše OKRka byly poněkud méně ambiciózní: 

* 2 dny každého na hackathon na vytvoření MVP výše uvedeného výpadkového 
nástroje
* 3 dny každého na studium Error Budgetů a následného společného vytvoření 
ukázkové implementace
A ani ty jsme nestihly. Přestože hackathon byl krásný a skutečně vedl k 
splnění drtivé části všeho potřebného, ukousli jsme si trochu moc velké sousto. 
Chtěli jsme pro dokončení využít ty 3 dny z Error Budgetů, ale přes cíle 
produktových týmů, svátky a podobně se je všechny vybrat nepodařilo a nástroj 
jsme zatím nedokončili.

## Třetí iterace – 2020Q4 – kde jsme teď a kam dál

Jak je mým zvykem, začal jsem přemýšlet co je špatně a proč ani druhá iterace 
nevypadá jako recept na úspěch. Hackathony jsou sice v podstatě skvělé, ale 
bez tahu na branku to není ono, nemluvě o tom, že kvůli osobním životům je 
nejde organizovat zas tak často. 

Začal jsem si uvědomovat pár věcí: 

* Exekuce není úplně silná stránka distribuovaného nepřímo vedeného týmu.
* O dnech, které získají vývojáři k dispozici se papírově dá předem bavit, 
ale skutečnost je kvůli potřebné agilitě stejně jiná
* To, co dokážeme nabídnout jako skupina firmě, je omezováno naším rigidním 
plánováním čtvrt roku dopředu

Každá z našich skupinek zatím funguje hodně odlišně a každý z vedoucích má 
velice odlišné pohledy na věc. I přes to se nám podařilo shodnout na tom, 
že se nebudeme tento kvartál handrkovat o dny a prostě jen nastíníme naše cíle, 
které prodiskutujeme s produkťáky týmů, od kterých nějaký čas chtít budeme. 
Vyjasnili jsme si tím odhadované priority na následující kvartál a dohodli se, 
že o kapacitě se budeme vždy bavit v rámci sprintu.

Věc, na které jsme se s ostatními neshodli, je exekuční složka skupin. 
Jsem hluboce přesvědčený, že za operations ta nejlepší cesta vpřed vede přes 
dlouhodobé vzdělávání členů. Díky znalostem je potom možné exekuční složku, 
která patří do týmů (které je za svůj produkt zodpovědné), vykonávat mnohem 
efektivněji. 

Shodli jsme se tedy na následujících OKR:

* Získávání znalostí (začínáme u CI/CD, Disaster Readiness a Error Budgetů)
* Vymyslet proces pro rychlé reagování na potřeby firmy 
* Skutečně dodělat MVP nástroje pro výpočet ceny výpadků

Je trochu hloupé, že nástroj, o kterém půl roku mluvíme a věnovali jsme jeho 
vymýšlení a tvoření nemálo úsilí přestal být prioritou, na druhou stranu přesně 
toto je daň za agilní přístup. V tomto případě sice stále plánujeme nástroj 
dodělat, ale už teď je mi jasné, že bude hledat adoptivní rodiče a 
vlastnictví/zodpovědnost za provoz na virtuálním týmu zůstat nemůže.

Za pár dní nás čekají první prezentace získaných znalostí v rámci guildy a 
nemůžu se dočkat, pokud vše dopadne podle mých očekávání, mělo by se mi 
potvrdit, že stačilo půl roku a koncept základního fungování naší guildy 
můžeme začít tesat do kamene. Dále nás bude čekat přepnout do angličtiny, 
přizvat kolegy z Maďarska a Slovinska… Spousta práce je před námi, ale 
momentálně si velice užívám pocit, že jsme už jen malý krůček od prvního 
zdolaného vrcholku. Snad.

Kromě konceptu fungování, se nám konečně povedlo dodefinovat si co vlastně jsme. 
Dovolím si sem zkopírovat z naší interní wiki misi operations guildy v angličtině:

> Heureka runs on autonomous development teams. We aim to help developers take 
> on the responsibility of running their applications in production environment. 
> That means deploying them, operating, monitoring and reacting to all of that.
> 
> This should all lead to applications that are stable enough to not cause us 
> big losses while still being innovative from the product perspective.

## Shrnutí

Po dlouhém boji začínáme tušit co jsme a jakým způsobem přinášet firmě hodnoty, 
které dlouhodobě povedou k lepší technické úrovni. Jako správný kapitán jsem 
dalekohled nechal na souši a žádné ledovce nevidím.

Slibuji, že jsem tento článek nerozepsal za tímto účelem, 
ale když už jsme u toho: hledáme kapitána kapitánů našich skupinek, 
pokud se nebojíš pohybovat ve skutečně agilním prostředí s obří dávkou svobody 
a myslíš, že bys v takovém prostředí dokázal nepřímo vést mě a pár mých kamarádů 
(a skrze nás vlastně celý vývoj), tak mrkni na náš 
[inzerát](https://onas.heureka.cz/technical-lead).
