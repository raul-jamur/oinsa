Title: Instala Pelican
Date: 2013-07-22 10:46


Instala Pelican
===================

Pelican lao diak iha Python 2.7.x, versaun ida uluk Python nian sei la suporta. Iha suporta temporariu baa versaun Python 3.2 no versaun bot liu tan, Maske belee iha sessaun nebee ladun diak, liu – liu ida nebee maka iha relasaun ho komponente opsional. 
Ita belee instala Pelican liu husi metodu – metodu nebee diferente. Simples liu maka liu husi pip: 

    $ Pip install pelican 

Sei ita seidauk instala pip, metodu alternativu maka easy_install: 

    $ Easy_install pelican 

(Ita presija lembra katak sistema operasaun husu bei – beik ita wainhira iha prosesu primeiru husi ordem ida iha leten nee hanesan sudo atu halao instalasaun Pelican sistema tomak.) 
Metodu ida iha leten, metodu ida nebee simples liu, nia sugestaun maka atu belee kria ambiente virtual baa Pelican liu husi virtualenv antes atu instala Pelican. Ho ida nee ita nia virtualenv instala tiha ona, Hotu tiha ita belee loke sesaun terminal foun no kria ambiente virtual foun baa Pelican: 

    $ virtualenv ~/virtualenvs/pelican
    $ cd ~/virtualenvs/pelican
    $ . bin/activate

Ambiente virtual halo tiha no aktiva ona, Pelican belee instala liu husi pip instala pelican hanesan buat nebee hatete tiha ona iha leten. Ou, sei ita iha rekursu baa projektu ida, ita belee instala Pelican uja metodu distutils: 

    $ cd path-to-Pelican-source
    $ python setup.py install

Sei ita hakarak uja Markdown hanesan format markup, Ita tenki instala Markdown library mos: 

    $ Pip install Markdown


Pelican instala hotu ona,ita belee uja atu belee muda Markdown ou konten sira nee baa HTML liu husi ordem pelican, desidi path ba ita nia konten no (opsional) path ba file nebee ita konfigura tiha ona: 

    $ pelican /path/to/your/content/ [-s path/to/your/settings.py] 

Ordem nebee iha leten sei kria situs ida no no sei rai iha output / folder, uja tema default atu belee kria situs ida nebee simples. Tema default nee mai husi HTML nebee simples no la uja styling no mos prepara ba ema foin mak atu aprende halo nia tema rasik. 

Ita mos belee fo hatene baa Pelican atu ita belee haree modifikasaun nebee ita kria ou halo, laos manual wainhira ita hakarak atu haree fali ita nia modifikasaun. Atu aktiva ida nee, uja ordem pelican ho -r opsaun – autoreload nian.
 
Pelican iha ordem switch nebee pelican iha tiha ona. Belee haree ordem nee iha ajuda haree opsaun hotu -  hotu nebee ita belee uja: 

    $ Pelican - help 
