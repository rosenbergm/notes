# NSWI141 Úvod do počítačových sítí

> Nezazní tady žádný důkaz, až na výjimky...

- casual rant na videotutorialy
- nebyly to moc zazivny lol
- sitovy referencni model
	- OSI
		- ted pouzivan jako ref. model pro popis vsech siti
- sitova architektura (protocol suite)
	- sitovy model, komunik. tech, sluzby a protokoly
	- TCP/IP
- model OSI (open systems interconnection)
	- od dole po nahore
	- fyzicka vrstva
		- skutecny prenos mezi uzly
		- fyzikalni stranka prenosu
	- linkova
		- prenos datovych ramcu
		- prenos bloku - je spravne preneseny do druheho uzlu
	- sitova
		- comms a smerovani mezi sitemi
	- transportni
		- e2e prenos datovych bloku
		- uz zna logiku, neni to jenom par bitu
	- relacni
		- handling spojeni a dialogu
	- prezentacni
		- datove konverze pro aplikace
		- typicky pro endianness
	- aplikacni
		- komunikace mezi programy
- TCP/IP
	- kasle na fyz. a link. vrstvu, rika tomu sitove rozhrani
	- zacina u 3. vrstvy
	- 3v OSI = sitova v tcpip
	- 4v OSI = transportni tcpip
		- dva protokoly - TCP/UDP
	- dalsi tri -> aplikacni
- TCP/UDP
	- spojovana sluzba
		- TCP
		- reliablke
	- nespojovana sluzba
		- UDP
		- unreliable
- model klient/server
	- klient zna server
	- klient init. comms, zadava pozadavky
	- server->klient: download, opak upload
	- DNS, WWW, SMTP
- p2p
	- napster, bittorrent
	- klient je serverem
- adresovani pocitacu
	- hw (linkova vrstva)
		- fyzicka adresa, MAC (media access control) adresa
		- dana vyrobcem (driv), nastavitelna (dnes)
		- nerespektuje topologii
	- sw (sitova vrstva)
		- ip adresa
			- pridelovana podle topologie site
			- urcuje jednoznacne sit a jejim ranci pocitac
	- pro lidi (aplikacni vrstva)
		- domenova adresa
		- prideleni podle org. struktury
		- snazsi zapamatovani/odvozeni
- forst chce zabit kamarada vozickare