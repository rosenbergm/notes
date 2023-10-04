- pan Topfer sídlí v pracovně 404, takže nevim, jestli ho tam najdeme
- https://ksvi.mff.cuni.cz/~topfer/
>Dohodneme se ze vime, co mame na mysli
- algoritmus
	- vlastnosti - nemusi mit vsechny samozrejme
		- konecnost, hromadnost (funguje pro jakoukoli posloupnost vstupnich dat), resultativnost (dava vysledky), jednoznacnost (pro stejny vstup stejny vystup, ale mame i algo pro random cisla, takze to taky nemusi platit vzdy), determinismus
	- formalni modely
		- rekurzivni fce, turinguv stroj, lambda kalkul, RAM pocitac
	- popis a zapis
		- slovni popis v prirozenem jazyce, pseudokod, program
## Nejvetsi spolecny delitel
- X,Y -> dve kladna cisla
- trivialni - NSD musi byt od 1 do min(X, Y), vyzkousim
	- muzu zkouset z obou stran, ale od min(x,y) dolu k 1 je to lepsi, ale jenom nekdy (cisla muzou byt nesoudelna)
	- slozitost
		- v nejhorsim, nejlepsim a prumernem (prumer ze vsech moznych situaci, co muzou nastat) pripade
		- my se budem bavit o slozitosti v nejhorsim pripade
- rozklad na prvocisla a vzit max. spolecnou cast
	- bez zkouseni mnoha moznosti, ale musim umet rozlozit na prvociselny rozklad
- eukleiduv algoritmus
	- velmi fajne
	- jeste lepsi muze byt s modulem!
	- spravnost eukl. algoritmu
		- konecnost - vypocet pro jakakoli vstupni data skonci
			- pri kazde iteraci jedna x+y aspon o jednicku klesne
		- parcialni spravnost - kdyz skonci, vyda spravny vysledek
			- **desivej dukaz**
## Problem stabilnich manzelstvi
- N muzu a N zen -> N paru, N! moznosti
- chceme stabilni parovani - takove parovani, ve kterem neexistuje prvek nestability - takovy muz a zena, kteri nejsou spolu v paru, ale kdyby oba opustili svoje stav. partnery, tak si OBA polepsi
- lze vzdy nalezt nejake stabilni parovani?
- je stabilni parovani urceno jednoznacne?
- jaym algoritmem a s jakou casovou slozitosti lze ulohy vyresit?
- reseni hrubou silou je n^3n! - bleh
- stabilni parovani vzdy existuje, mame na to algo
	- gale-shapley algoritmus
		- muzeme jit z obou stran
		- konecnost
			- iterace=nabidka, zadny muz nenabizi snatek teze zene dvakrat => cyklus nejvyse n^2 krat
		- uplnost parovani
			- jakmile je zena jednou zadana, uz nikdy nebude volna
			- zena muze odmitnout, jen kdyz je zadana
			- dukaz sporem => uplne parovani
		- 