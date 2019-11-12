---
layout: post
title: "Jak jsem hacknul DevFest"
permalink: /jak-jsem-hacknul-devfest/
date: 2019-11-12 16:00:00 +0200
author: Pavel Škoda
tags: [konference, security, hack, devfest]
categories: [blog, kod, bezpecnost, meetupy_a_konference, legrace]
imageUrl: /assets/jak-jsem-hacknul-devfest/devfest.jpg
--- 	
Na úvod musím říct, že se letos [DevFest][devfest] rozhodně povedl. Kluci a holky z [GuG][gug] i všichni ostatní udělali hromadu práce, když tuhle konferenci připravovali a bylo to opravdu znát. Až na zlobivou Wi-Fi (což je, přiznejme si, problém většiny konferencí) šlo vše velmi hladce. Program byl našlapaný a většina přednášek opravdu zajímavých. Venue a kostýmy pořadatelů skvěle dokreslovali postapo atmosféru, v jejímž duchu se letos akce konala. Doufám, že následující řádky nevyzní nijak negativně, protože já jsem si letošní [DevFest][devfest] opravdu užil.

Když jsem přišel do předsálí, všiml jsem si, že jsou všude na stěnách nalepené papírky s QR kódy. Ze zvědavosti jsem jeden načetl přes klasickou QR čtečku v očekávání, že budu přesměrován na nějakou URL plnou zajímavých informací o programu, nebo třeba o tom, co bude k obědu. K mému překvapení se však uvnitř QR kódu skrývalo pouze číslo `920`, žádná URL, žádné informace, pouze to číslo. Nechal jsem tedy kód kódem a šel jsem si dát před úvodní přednáškou kafe.

Během “Keynote”, která byla velmi zábavná, jsme se dozvěděli, o čem bude gamifikace letošního [DevFestu][devfest]. V podstatě jsme se ocitli v postapo světě jako vystřiženém z Millerovy filmové série Mad Max. Sedíme uprostřed jednoho z posledních měst na zemi a tam venku je neúprosná pustina. Nedaleko ztroskotala vesmírná loď a její velitelka přišla prosit o trochu vody pro svou posádku.

Jenže vody mají všichni nedostatek, a jediný způsob jak “vytěžit” nějakou další je: přihlásit se na stránce s herní aplikací, naskenovat jeden z QR kódů a odpovědět na otázku, nebo vyřešit soutěžní úkol u některého stánku.

Jsem v Heurece členem [security][security] guildy, a tak se u všeho snažím přemýšlet kriticky s ohledem na bezpečnost. Proto mě hned napadlo, jak to asi bude fungovat, když QR kódy obsahují prostě čísla. Vygeneroval jsem si pomocí on-line generátoru QR kód obsahující číslo `920` a naskenoval ho herní aplikací. Samozřejmě to fungovalo a já tak přišel ke svým prvním litrům vody (to byly vlastně herní body) dříve, než se mohli ostatní vůbec zvednout ze židle a jít naskenovat první kód.
Zajímala mě také predikovatelnost, tak jsem zkusil vygenerovat kód s číslem `921` a opět jsem dostal další vodu (body). Zkoušel jsem tedy nějaká další čísla a zjistil jsem, že to co zadávám, je ID otázky, protože sama aplikace mi vracela chybu, která na to upozorňovala.

Začal jsem tedy zkoušet náhodná čísla a vypozoroval určitý vzorec. ID otázek se vyskytovaly pohromadě vždy následující po celé stovce a se zvyšujícím se číslem se zvyšoval i počet obdržených bodů. Nevím přesně, jak to fungovalo uvnitř, ale vsadil bych se, že všechna IDčka byla prostě třímístná číslá, kde první místo označovalo obtížnost otázky a tím i počet obdržené vody.

Přemýšlel jsem jak proiterovat všechna ID. A tak jsem našel webové [API na generování QR kódů][qoqr]. Nechal jsem si ale doma Laptop, takže jsem si musel vystačit s tabletem. Naštěstí žijeme v cloudovém světě a existují služby jako [JSFiddle][jsfiddle]. Napsal jsem tedy jednoduchý skript, který mi generovat jeden kód za druhým na tabletu a kódy jsem poté skenoval pomocí herní apky na mobilu. Za chvíli už jsem vlastnil více než třetinu zatím vytěžených zásob vody ve hře.
Samozřejmě by to šlo i jednoduše, po naskenování QRkódu se totiž volá URL ve tvaru `/<id-otázky>`, jenže přímé volání té URL mi nefungovalo, pravděpodobně obsahuje nějaký CSRF token a díky tomu, že jsem měl k dispozici pouze tablet, neměl jsem po ruce vývojářské nástroje v prohlížeči, abych mohl vysledovat, co se děje uvnitř apky.
Navíc, kdyby se jednalo o reálný útok, měl by můj přístup tu výhodu, že je špatně zjistitelný, jelikož se v podstatě chovám jako normální uživatel, takže v logu nebudou chybět requesty, které by měly přesměrování na otázku předcházet.

Když sedíte na konferenci s tabletem, na kterém blikají QR kódy a jeden za druhým a skenujete je mobilem, nejste úplně nenápadní a já se ani být nenápadný nesnažil, takže jsem seděl v hale kousek od skupinky pořadatelů. Po chvilce jsem uslyšel huronský smích, když si všimli, co dělám.

Šel jsem tedy za pořadateli a pověděl jim, jak se věci mají. Říkali, že se každý rok najde nějaký kulišák, který se snaží systém obejít. Vyžádali si jméno, aby mě mohli vyškrtnout z výsledků a smazat body. Poprosili mě, abych o tom nikomu neříkal, což jsem ani neměl v úmyslu, dokud hra neskončí. Nechtěl bych ostatním zkazit hru. Pořadatelé si na ni určitě dali dost práce a byla by škoda jim to pokazit.

Mohlo by se zdát, že zabezpečovat takovouhle jednorázovou aplikaci je ztráta času, vždyť tu nejde o peníze ani o životy, a přece si myslím, že by byli všichni smutní, kdyby tuhle zranitelnosti objevil někdo jiný a za tepla ji zveřejnil na Twitteru. Navíc zas tak těžké všimnout si té zranitelnosti nebylo, a přitom by stačilo ony tokeny (ID) otázek vygenerovat náhodně v nějakém větším než tříciferném prostoru.

Nakonec se naštěstí nic nestalo. Všichni si hru užili a ten kdo vyhrál, své body snad nasbíral poctivě. Já si to letos také velice užil a už se těším na příští [DevFest][devfest]. Tedy pokud mě nezabanují už při koupi lístku :).

![devfest]( /assets/jak-jsem-hacknul-devfest/devfest.jpg)

[security]: https://www.heurekadevs.cz/ktera-mikrosluzba-pracuje-s-nejcitlivejsimi-daty/
[devfest]: https://www.devfest.cz
[jsfiddle]: https://jsfiddle.net/
[qoqr]: http://goqr.me/api/
[gug]: https://gug.cz/