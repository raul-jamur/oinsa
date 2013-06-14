#Ordem Basico (Basic Command) iha Ubuntu By Raul Jamur Inside

Ordem (command) basiku iha GNU/Linux halao iha shell ida nebee bai-bain hanaran _terminal_ ou console. Terminal ou console nee rekonese ho naran _Command Line Interface (CLI)_ nebee bele aktiva hanesan klik ou hili Menu Applications – Accessories – Terminal. Dalan seluk bele mos halao husi Console los det nia lalaok mak hanehan ctrl+alt+F1 iha Keyboard iha Keyboard F1 hanehan koko to F6. Atu fila fali mai mode Grafical User Interface (GUI) Hanehan ctrl+alt+F7 iha Keyboard. Tuir mai iha Ordem (command) jeral nebee hetan iha distribuisaun ida-idak iha GNU/Linux liu-liu iha distribuisaun Ubuntu.

1. login 
Fungsaun :atu tama ba iha rede nia area.
<p>Observasaun :Ema ida-idak nebee legal uja sistema UNIX iha identifikasaun kona ba identidate (ID).
2. Password
 Fungsaun :Hatama lian xhave _(Password)_ wainhira login. <p>Observasaun:Ba ema nebe foun nebee registu tiha ona husi SUPER USER maka user la presija atu hatama tan lian xhave _(password)_. Ida nee atu Bele assegura lian segeredu ou lian xhave nebee iha tiha ona.
3. login
 Fungsaun :Atu halo ou troka ita nia lian xhave.
4. who 
Fungsaun :Atu hatene User nebee aktifu ka Onlline hela (login). 
5. finger
 Fungsaun : Finger iha fungsaun nebee atu hanesan ho who, so que finger prepara informasaun baa identitade user nebee kompletu liu iha who.
6. logout 
Fungsaun :Atu sai husi sistema ou taka sessaun login nian. <p>Observasaun :Se wainhira atu taka terminal diak liu uja ordem ida nee, para aksesu nebee legal husi login nee ema seluk sei la uja ou tama fali uja ita nian.
7. exit
Fungsaun :Atu sai ou taka sistema.
<p>Observasaun :Hanesan ho fungsaun logout.
8. whoami
Fungsaun :Atu hatene user nebee mak login iha komputer/terminal. <p>Observasaun : Uja para atu hetan terminal nebee seidauk logout ou exit no atu hakarak hatene se nian mak uja terminal nee.
9. date
Fungsaun :Atu haree ou muda oras no loron/fulan.tinan. 
10. cal
Fungsaun :Atu haree kalendariu husi tinan 0000 t/f 9999.
11. ls
Fungsaun :Atu haree lista file iha folder ka direktori nebee aktivu hela. <p>Observasaun :Ordem ida nee atu haree informasaun kona baa direktori ho file nian. Ordem nebee simples husi ls atu hatudu naran file det. Ordem nebee naruk aumenta ou komesa ho opsaun –l, nebee sei hatudu naran file nebee hamutuk ho informasaun atu nunee file ita bele haree ida-ida.

Opsaun-opsaun nebee iha:

+ -a : Atu haree file iha directory inklui mos nia laran.
+ -o : Atu haree det naran directory
+ -g : Halo (Cetak) ID grupu iha lalaok nebe naruk
+ -I : Halo (Cetak) numeru ba iha User ida-idak.
+ -l : Atu haree kompletu file hotu-hotu.
+ -o : Halo (Cetak) ID ema nebee uja (karik uja –1)
+ -r : Hadia ou Haktuir naran file nebee iha tiha ona
+ -t : Hadia naran file baseia ba oras ida nebee ita modifika tiha ona, la tuir naran.
+ -o : Hadia naran file Baseia ba momentu ida nebee ikus hadia.

Ba opsaun naran, bele “naran” nee maka fatin ba directory, ordem bee halo (Mencetak) informasaun nebee husu husi opsaun nebee (option) ba file hotu iha direktori laran. Wainhira “naran” file ida, maka informasaun file nebee iha relasaun ho ida nebee haloo sai tiha ona (dicetak).

12. chmod
Fungsaun : Troka permission ida iha direktori/file.
<p>Formatu : chmod 777 naran_file
13. clear
Fungsaun :Hamos layar, (Hanesan ho ordem CLS iha DOS).
<p>Formatu : clear ou bele mos hanehan kombinasaun husi letra iha Keyboard ctrl+D
14. cmp
Fungsaun :Atu halo komparasaun file1 ho file2 no bele halo reportajem ba nia diferensa.
<p>Formatu : cmp file1 no file2
<p>Observasaun :Orden ida nee sei la halo reportajem karik file 2 nee hanesan ou identiku.
15. cp
Fungsaun :Atu halo file1 sai ba file2.
<p>Formatu :$ cp file1 file2 copia → file1 ba file2
$ cp koko3 /home/jamur/raul → copia file koko3 baa direktori seluk <p>Observasaun :Ordem cp sei-copia file ida baa file seluk ou halo copia file ida ou liu ba iha direktori ida.
16. rm
Fungsaun :Atu apaga ou hamoos file ida.
<p>Format : rm naran-file.
ou rm /path_file_iha-ba
17. mv
Fungsaun :Atu muda file husi fatin ida ou bele mos troka naran (rename) naran file ida.
<p>Formatu : $ mv file1 file2 Rename → file1 sai fali file2
$ mv koko3 /home/jamur/raul → muda file koko3 ba direktori seluk
<p>Observasaun :mv sei muda file ida ba file seluk ou muda file ida det ou liu husi 1, baa iha direktori ida.
18. cat
Fungsaun :Atu haree saida mak iha file ida nia laran (hanesan o ordem TYPE iha DOS). Cat fungsiona mos para atu halo (mencetak) ba iha monitor file ida nia laran. Karik file nee haree husi nia fungsaun ordem nee laos file text nebee mak atu sai karakter- karakter nebe arbiru iha layar.. atu prevene ida neekarakter-karakter arbiru nee bele uja ba ordem cat –v.
19. more
Fungsaun :Atu haree text file iha layar ida-idak.
<p>Format :more naran-file
<p>Observasaun :Ho ordem ida nee file nia laran bele haree ida layar ida-idak atu nunee bele kuriji detailu liu. Hanehan spasi atu haree file nia laran iha layar ida seluk.
20. history
Fungsaun :Atu haree ordem-ordem nebee uja tiha ona.
<p>Formatu :history
21. wc
Fungsi :Menghitung jumlah kata, jumlah baris dan jumlah karakter
dalam suatu file.
<p>Format :wc nama-file
22. man
<p>Fungsaun :Lian badak husi manual ida nebee atu haree pajina manual baa ordem hotu iha UNIX. Ordem nee valor liu baa ema sira nebee uja UNIX tamba bele ajuda ita atu bele hanoin fila fali ordem-ordem nebee iha UNIX.
<p>Formatu :man naran-ordem
23. grep
Fungsaun :Buka file ida nia laran iha directori seda det.
<p>Formatu :grep –n ‘naran-file’ iha-direktori
<p>Observasaun :Ordem nee sei buka variable ida linya laran ruma, iha direktori seda det baa file hotu-hotu. Grep
fungsiona tebes atu buka naran file ida iha direktori laran ou buka variable ida iha grupu programa ida.
<p>Exemplo : grep –n ‘shutdown’ /etc/*.
24. mkdir
Fungsaun :Atu halo direktori.
<p>Formatu :mkdir naran-direktori
~$ mkdir koko1 koko2 koko3 (halo direktori 3 dala ida)
<p>Observasaun: Iha DOS nia ordem mak MD (make directory)
25. rmdir
Fungsaun :Apaga ou hamos direktori nebee mamuk.
<p>Formatu : rmdir naran-direktori
~$ rmdir koko1 koko2 koko3 (apaga direktori
3 dala ida)
Wainhira directori nebe apaga ou hamos tiha ona ne mak laiha maka sei iha mensajem ida.
<p>Observasaun : Iha DOS nia ordem mak RD (remove directory).
26. pwd
Fungsaun :Hatudu direktori nebee aktivu.
<p>Formatu :pwd
27. cd
Fungsaun :Tama baa lokasaun direktori ida.
<p>Formatu : cd path-direktori
<p>Exemplu : ~$ cd /etc , Maka nia sei muda baa direktori etc
28. adduser
Fungsaun :Aumenta user foun iha sistema.
<p>Format :adduser naran-user
29. ps
Fungsaun : Uja baa atu monitoring informasaun kona baa prosesu
nebee aktivu iha sistema UNIX.
<p>Format :ps -aux
30. kill
Fungsaun : Uja atu taka prosesu ida nebee mak servisu hela.
<p>Formatu :kill id-proses
<p>Observasaun: Id prosesu bele haree husi PID husi ordem ps -aux.
31. &
Fungsaun :Halao programa ida iha layar kotuk (multitasking).
<p>Formatu :& naran-programa
32. bc
Fungsaun :Ordem bc Bele uja atu asesu calculator.
<p>Observasaun: Fasilidade nee laiha iha versaun UNIX nebee standar.
33. pr
Fungsaun :Halo (mencetak) file ida ba printer.
<p>Format :pr naran-file > /dev/lp0
34. write user [tty]
Fungsaun :Haruka mensajem ba User nebee login hela. <p>Observasaun:Write sei halo relasaun husi keyboard baa layar user nebee ita hili. Saida det mak ita hanehan iha keyboard sei mosu iha layar ema ida nebee atu simu mensajem.
35. mesg [opsaun]
Fungsaun :Rejeuta mensajem nebee husi user seluk.<p>Observasaun:Ita bele mos rejeita mensajem nebee haruka husi user seluk nebee uja ordem write. Ordem nee labee rejeita lisensa husi super user atu haruka mensajem.
36. mail [ema nebee simu]
Fungsaun:Haruka no lee mensajem nebee hanesan surat. 
<p>Observasaun:Mail hanesan programa ida haruka mensajem elektroniku haruka mensajem ba user seluk ou lee mensajem husi  user seluk.
37. wall
Fungsaun :Mensajem nebee ita haruka husi super user.
<p>Observasaun :Baa super user, sistema operasaun UNIX halo preparasaun atu haruka mensajem ba User hotu nebee log in hela wainhira mensajem ho ordem nee so super user det mak bele asesu ou komanda.

Rekursu Husi : Ebook-Ubuntu-Indonesia.Com-V01
	Translate Husi Raul Amaral
	Deskulpa karik iha liafuan ruma nebee karik sei salah no mos la los.
