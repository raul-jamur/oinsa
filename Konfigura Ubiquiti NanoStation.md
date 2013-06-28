Konfigura Ubiquiti NanoStation2 Loco
======================================

###Rekerementu:

+ Fiu Ethernet atu halo koneksaun PC ho NanoStation. Switched connection ka bridged connection ita belee halao servisu nee offline.

+ Konfigura Network baa  PC: 192.168.1.254/255.255.255.0
+ TFTP cliente iha PC ida.
NanoStation firmware file husi Ubiquiti (nee laos OpenWrt nia imazem)

Prosedurasaun

1. Taka tiha Nanostation2 nee

2. Hanehan reset button

3. Halo lakan fali Nanostation2

4. Husik reset button ~10 secondus (mos labele kleur) halo lakan tiha Nanostation2. Ita sei hatene wainhira lampu LEDs lakan no troka kor.

5. Ping 192.168.1.20. Sei lao,entaun ita prontu atu upload imagem ida, Se lae, Fila fali baa lalaok ida  1.

6. tftp imagem nebee iha binary mode ba 192.168.1.20 hanesan 'flash_update'.




    tftp 192.168.1.20

    tftp> bin

    tftp> put openwrt-atheros-ubnt5-squashfs.bin flash_update

    Sent 1965199 bytes in 28.8 seconds tftp> quit 



ou iha Windows Dos hakerek


    tftp -i 192.168.1.20 put openwrt-atheros-ubnt5-squashfs.bin flash_update	
    
7. Sinal LEDs sei lakan mate no troka kor wainhira ita halao hela upgrade.Iha Nano5L, lampu power fila fali no bei-beik to dala 7. Hein ~ Minutu 7 antes restarting ou too lampu power para lakan no lakan bei-beik too dala 7. Restart fali Nanostation2 belee halo fila fali baa konfigurasaun ida uluk nian (OpenWrt la estraga no la modifika NVRAM nia konfigurasaun).



8. telnet ba 192.168.1.1 no halo ita nia password ho


    passwd


Atu Restore(Fila-Ba) Original AirOS nian firmware iha Nanostation
Atu restore fila fali original firmware ita labele uja mtd ou sysupgrade maibe ita belee uja tftp nia metodu. 

Uluk nanain tau Nanostation iha recovery mode liu husi reset button wainhira power lakan, Hotu tiha flash original flash image liu husi tftp. 
