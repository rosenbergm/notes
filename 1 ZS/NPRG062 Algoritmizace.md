# NPRG062 Algoritmizace

- pan docent Topfer sídlí v pracovně 404, takže nevim, jestli ho tam najdeme
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
- slozitost je funkce
	- muze zaviset na jedne nebo vice promennych
- asymptoticka cas. slozitost
	- koukame na nejrychleji rostouci clen
	- ![ddcef84edfece05dea0160a807f8ea48.png](../../_resources/ddcef84edfece05dea0160a807f8ea48.png)
	- velke O
		- fce f se za shora odhadnout fci g
	- velka $\Omega$
		- odhad zdola
		- nebudeme je delat, jsou nam k nicemu
	- $\Theta$
		- presny (tesny) odhad
		- fakticky vime, jak roste
		- nejcennejsi, ale my se spokojime s O
- muzeme rozdelit do dvou skupin
	- polynomialne omezeny cas - obvykle zvladnutelne i pro velka N
	- exponencialni cas - pro vetsi N casove nezvladnutelne (pouzitelne jen, kdyz vstupni data budou vzdy mala)
- O(1)
	- jak topfer rekl, vytraci se hromadnost
	- mame n cisel, chceme najit prvni cislo - "to je ovsem ale debilni uloha"
- slozitost *problemu*
	- = slozitost nejlepsiho mozneho algoritmu (z hledisla cas. slozitosti), kterym lze resit dany problem
	- nelze odvodit ze slozitosti nejakeho konkr. alg, charakterizuje problem obecne (jaky nejlepsi alg resis problem muze v principu existovat)
	- casto obtizne, pro radu problemu nezname
- rozklad cisla na cifry
	- cislo X rozlozit na cifry
	- programatorsky - prevedu na string, pak rozkrajim lmao
	- algoritmicky - muzu pouzit $\% 10$
- test prvociselnosti cisla n
	- postupy
		- zkusit vsechny cisla od 2 do N-1 -> O(n)
		- staci zkouset vsechny delitele od 2 do N/2 (vetsi delitel neexistuje) -> O(n)
			- z hlediska fakticke rychlosti je dvojnasobne rychlejsi
		- staci zkouset vsechny delitele od 2 do $\sqrt{n}$ 
			- bacha na vypocet odmocniny, pr. rekurentni vzoerc, ktery konverguje k odmocnine
				- d<= $\sqrt{n}$ zapisu jak d^2<=n -> v kladnych cislech to same
			- mali N vlastniho delitele, musi mit i delitele z tohoto intervalu -> O($\sqrt{n}$)
			- dukaz:
				- N je slozene, muzeme vyjadrit jako a*b
					- a = b = $\sqrt{n}$
					- NEBO a bude vetsi nez $\sqrt{n}$ a b bude mensi NEBO NAOPAK
						- dokazano
		- staci zkusit cislo 2 (jedine sude prvocislo) a pak jen liche delitele
- nalezt prvocisla
	- eratosthenovo sito
		- urcete vsechna prv. od 2 do N
			- v rade cisel od 2 do N postupne vyskrtavame vsechnt nasobky jednotlivych prvoc.
			- co neni vyskrtnuto, je prvocislo
		- program -> list(bool), index je cislo od 2 do N, hodnota prvku rika, jestli je prvoc.
		- casova slozitost -> O(Nlog(logN))
- dlouha cisla
- vyhodnoceni polynomu v bode
	- bud primy vypocet - O(n^2)
		- n(n+1)/2 nasobeni, n scitani
	- nebo hornerovo schema O(n)
		- n nasobeni a n scitani
- 