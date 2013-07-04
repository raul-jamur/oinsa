Title: Oinsa atu uja apt-get ??
Date: 2013-07-01 11:28


Oinsaa atu uja apt-get ??
=========================

##Uja *apt* _(Advanced Packaging Tool)_ Iha Ubuntu

*Advanced Packaging Tool*, uluk porting tiha ona husi Conectiva atu uja hamutuk ho rpm no adopsia tiha husi distro seluk.

Ordem sira nebee _apt-get_ nia linya iha ordem ida atu halao apilkasaun nebee atu uja ba servisu hamutuk ho *Ubuntu's Advanced Packaging Tool (APT)* halo fungsaun-fungsaun hirak nee atu halao instalasaun pakete (Software), atu-upgrade pakete (Software) nebee iha, atu-update lista pakete indeks, no bele aumenta ou haforsa lalaok sistema nebee iha Ubuntu.

*APT* uja baa file ida nebee iha lista 'rekursu' husi pakete nebee ita atu belee hetan. File nee iha / etc / apt / sources.list. 

Atu Tama baa file nee nia laran halo tuir formatu tuir mai nee:

<code>
deb http://host/ubuntu distribution section1 section2 section3
</code>


<code>
deb-src http://host/ubuntu distribution section1 section2 section3
</code>

Liafuan primeiru baa linya iha leten nee, mak deb ou deb-src, atu hatudu modelu arquivo: katak iha ka lae pakete binary (deb), ne mak pre-compiled pakete-pakete nebee bai-bain ita uja, ou  _(Packet Resource)_ rekursu pakete (deb-src). 

Agora mai ita konhese tok ordem nebee iha apt-get

Update lista pakete nebee iha

Sistema nebee uja database (Base de Dadus) privadu atu buka tuir ka buka hatene pakete nebee instal ka monta tiha ona, ida nebee mak la hatama ka install no ida nebee mak belee atu halo installasaun. Programa apt-get uja database (Base De Dadus) nee atu hatene tuir dalan ou maneira atu install ou hatama ka monta pakete-pakete nebee kliente ka ema nebee uja nia hakarak no atu hatene pakete-pakete sira seluk presija atu hatene pakete nebee mak ita hili atu halao servisu ho diak.

<code>
sudo apt-get update
</code>
Opsaun apt-get nee parese belee fungsiona

+ -h tekstu ajuda nian.
+ -d Download det- LA instal ou hasai ka sobu arquivo
+ -f Koko atu halo fila fali karik falha ka labele koko integritasaun
+ -s LA-HALO BUAT IDA. Hameno simulasaun
+ -y Hatete Yes atu halao ordem no laiha obrigasaun
+ -u Atu haree lista pakete upgrade nian

Install ka halao Pakete Uja apt-get

<code>
sudo apt-get install paketenianaran
</code>

Lee tan kona baa: penjelasan apt-get lengkap | Ubuntu Online :: Tutorial Ubuntu, Tutorial Instalasi


Exemplu:

<code>
1. sudo apt-get install apache2
</code>

Ordem ida nee uja para atu halao ka installasaun baa aplikasaun Apache2 iha ita nia Komputador nebee nia sistema operasaun base mak Ubuntu ka Linux.

<code>
2. apt-get install apache2 apache2-doc apache2-utils
</code>

Ordem ida segundu nee uja para atu halao ka halo instalasaun baa aplikasaun Apache2 hamutuk ho nia documentasaun no moos utilizasaun baa Apache2 nian.

<code>
3.  apt-get install python-mysqldb
</code>

Ordem ida terseiru nee nia fungsaun atu halo instalasaun ba aplikasaun Apache2 nia fungsaun belee moos suporta ba python no moos MySQL. Atu nunee ita belee halao server web ida iha ita nia komputador maske ita laiha server ida iha internet.

<code>
4. a2dissite default
</code>

Ordem ida baa dala haat, nia fungsaun atu hamate ou hapara (disable) aplikasaun Apache2 nia servisu.
