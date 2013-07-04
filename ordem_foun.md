Title:Aprende Ordem (Learn Command )
Date: 2013-07-01 21:53


## chmod

chmod uja para atu modifika mode husi Owner, Group, no mos Everyone atu nunee ita belee fo lisensa ba se mak sei belee atu halo mmudansa ka modifika file nebee ita iha...

Exemplu:

Ita atu muda permission ka direitu baa se mak sei hetan atu belee halo mudansa ba iha file ida husi Owner, Group no mos Everyone. Atu halo ida nee ita presija ordem tuir mai nee.

Ordem nee uja para atu halo mudansa ba iha file ida nia mode.


    sudo chmod 644 file_nia_naran


Owner  = 6

Group  = 4

Everyone = 4

Belee mos koko atu troka ho numeru seluk hanesan 777, 666 ho 655.

Nia ordem hanesan tuir mai nee:

    sudo chmod 777 file_nia_naran
    sudo chmod 666 file_nia_naran
    sudo chmod 655 file_nia_naran
    
    
Ordem ida uja 777 nee nia fungsaun mak belee foo permission ka direitu tomak baa see det atu belee halo modifika baa file ida.

Entaun Owner, Group no mos Everyone belee halo modifika baa file ida tamba sira nain 3 hetan permission ka direitu tomak atu belee halo modifikasaun baa file ida.
Hanesan mos ho ordem nebee uja numeru seluk.


Exemplu:


    -rwxrwxrwx 1 root root

Observasaun:

     Owner  Group   Everyone
    -rwx    rwx     rwx        1 root root


Atu haree hanesan nee belee uja Ordem ida tuir mai nee atu haree file sira nebee iha permission ou direitu nebee belee hetan mudansa husi Owner, Group no mos Everyone baa iha file ida.

Hakerek ordem tuir mai nee:

    ls -laF

Observasaun:

+ r = Read (Lee)
+ w = Write (Hakerek)
+ x = Execute (Halao)



Observasaun:

rw - - r - - r ............ file1

rw - - - - - - .............file2

Iha file1 bele hetan permission a direitu husi Owner (rw), Group (r) no mos Everyone (r). Ida nee signifika Owner bele halo modifika ka troka file 1 maibe Group labele halo modifika ka troka file1 nia so belee (r) lee det file1 hanesan mos ho Everyone.

+ r = Read (Lee)
+ w = Write (Hakerek)
+ x = Execute (Halao)

Ita atu muda permission ka direitu baa se mak sei hetan atu belee halo mudansa ba iha file ida husi Owner, Group no mos Everyone. Atu halo ida nee ita presija ordem tuir mai nee.

Ordem nee uja para atu halo mudansa ba iha file ida nia mode.


    sudo chmod 644 file_nia_naran


Owner  = 6

Group  = 4

Everyone = 4

Resumo: husi ordem nee ita foo direitu ka permission ba iha Owner, Group no mos Everyone atu belee halo mudansa ba file ida.
