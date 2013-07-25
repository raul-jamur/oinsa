Title: Implementasaun NAT
Date: 2013-07-01 21:54


Konseptu no Implementasaun NAT (Network Address Translation)  Husi : Raul Jamur


### A. Tamba saa presiza NAT?

_Network Address Translation_ ou belee habadak ho naran NAT, mosu wainhira fatin baa IP (Internet Protocol) versaun 4 mihis liu ona no rede komputador tenki halo klasifikasaun sai fali Rede Publiku ou ida nebee mak ita bai-bain konyese ho naran Rede Internet no mos Rede Privadu ou ida nebee mak ita konyese ho naran _Rede Area Lokal_ (Local Area Network). Se karik antes nee ita aprende tiha ona  konseptu Routing, entaun ita sei hatene Host ida-idak nebee mak halo Koneksaun ba malu ho Host seluk nebee mak iha baa rede (network) nebee la hanesan tenki halao Route ba malu baa rede (network) nebee objektivu, atu hatene klean liu tan belee haree imazem tuir mai nee.

![Figura 1](http://127.0.0.1/grey/img/route.jpg)

![Figura-01.] Routing Direksaun Rua

Host iha Rede (Network) A halao tiha ona konfigurasaun route ba Rede (Network) B liu husi interface eth1 Router, hanesan mos Server iha Rede (Network) B halao tiha ona konfigurasaun route ba Rede (Network) A liu husi interface eth0 Router.
Maibe iha realidade, iha kondisaun nebee halo konfigurasaun route so belee det akontese ou lao iha linya ida deit, entaun koneksaun sei hetan difikuldade husi akontesimentu ida nee, hanesan mos iha imazem ida tuir mai nee.

![Figura 1](http://127.0.0.1/grey/img/dua_arah.jpg)

![Figura-02.] Routing Direksaun Ida

Tamba sa mak konfigurasaun route iha Direksaun ida deit? Tamba laiha sasan ida husi rede nian iha Internet nebee atu halo konfigurasaun ba iha rede LAN. Metodu belee halo Host ho Server belee halo komunikasaun nafatin mak NAT, nee mak ho dalan halo translasaun IP Host LAN baa IP Publiku Router ne par belee rekonyese husi sasan Rede sira seluk nebee iha internet.

B. Tipu NAT

B.1. Source NAT

Source NAT uja wainhira kondisaun uluk liu nebee ita hakarak mak halo translasaun husi IP Privadu LAN ba IP Publiku Router, hanesan iha imazem tuir mai nee.

![Figura 1](http://127.0.0.1/grey/img/Source.jpg)

![Figura-03.](/home/jamur/Desktop/PKL/Source.jpg) Source NAT


B.2. Destination NAT

Diferente ho Source NAT, Destination NAT uja wainhira kondisaun uluk liu nebee ita hakarak mak halo translasaun husi IP Publiku Router ba IP Privadu nebee iha LAN, hanesan mos iha imazem tuir mai nee.

![Figura 1](http://127.0.0.1/grey/img/SourceNAT.jpg)

![Figura-04.] Destination NAT



C. Relasaun entre Translasaun NAT

C.1. One-to-One Address Translation

Relasaun NAT nee bai-bain mos konhese ho naran Static NAT, nebee sei halo translasaun IP ida iha LAN nian ba IP Publiku ida seluk iha interface router, ou halo translasaun IP Publik ida ba interface router ba IP ida iha LAN nian ho lalaok nebee statis ou manual.

![Figura 1](http://127.0.0.1/grey/img/Single.jpg)

![Figura-05.] Single Static NAT

Ordem ba iptables Router Linux:

    # iptables -t nat -A POSTROUTING -s 10.0.0.2 -j SNAT –-to 2.2.2.2

Ordem ba MikroTik Router OS:

    # ip firewall nat add chain=srcnat src-address=10.0.0.2 action=src-nat to-addresses=2.2.2.2

![Figura 1](http://127.0.0.1/grey/img/multiple.jpg)

![Figura-06.] Multiple Static NAT

Ordem ba iptables Router Linux:

    # iptables -t nat -A POSTROUTING -s 10.0.0.2 -j SNAT –-to 2.2.2.2
    # iptables -t nat -A POSTROUTING -s 10.0.0.3 -j SNAT –-to 2.2.2.3

Ordem ba MikroTik Router OS:

    # ip firewall nat add chain=srcnat src-address=10.0.0.2 action=src-nat to-addresses=2.2.2.2
    # ip firewall nat add chain=srcnat src-address=10.0.0.3 action=src-nat to-addresses=2.2.2.3
C.2. Pool-to-Pool Address Translation

Relasaun NAT nee bai-bain konyese ho naran Dynamic NAT, nebe sei halo translasaun husi IP ida iha LAN nian ba IP Publiku ida seluk  ba interface router, ou halo translasaun husi IP Publiku ida ba iha interface router ba IP nebee mak iha LAN ho lalaok nebee dinamika.

![Figura 1](http://127.0.0.1/grey/img/dinamik.jpg)

![Figura-07.](/dinamik.jpg)
Figura-07. Dynamic NAT Kondisaun Primeiru



![Figura 1](http://127.0.0.1/grey/img/dinamik2.jpg)

![Figura-01.] Dynamic NAT Kondisaun Segundu


Ordem ba iptables Router Linux:

    # iptables -t nat -A POSTROUTING -s 10.0.0.2 -j SNAT –-to 2.2.2.2-2.2.2.3
    # iptables -t nat -A POSTROUTING -s 10.0.0.3 -j SNAT –-to 2.2.2.2-2.2.2.3

Ordem ba MikroTik Router OS:

    # ip firewall nat add chain=srcnat src-address=10.0.0.2-10.0.0.3 \
  action=src-nat to-addresses=2.2.2.2-2.2.2.3

D.  Port Address Translation (PAT)

Desvantazen husi metodu NAT nian mak wainhira IP Publiku fo husi ISP so ida deit nebee mak ita hetan komputador balun iha LAN nebee mak sei halo koneksaun ba internet. Wainhira IP host (LAN) nian hetan ka halo tiha ona translasaun ba IP Publiku router nian entaun IP host sira seluk labele tan halo translasaun ona, nebee belee fo impaktu so wainhira iha host ida deit nebee belee halo koneksaun ba internet. Port Address Translation (PAT) mosu ou iha para belee resolve problema nebee iha leten, koneksaun nebee husu  mai husi host iha LAN nebee ba iha internet sei halo translasiaun ba port balun deit nebee belee aprovita husi port nia rekursu nebee kria husi host nebee hun (asal), atu klaru liu tan belee haree Figura tuir mai nee.

![Figura 1](http://127.0.0.1/grey/img/manda.jpg)

![Figura-09.]PAT (wainhira host LAN manda request ba Server)


![Figura 1](http://127.0.0.1/grey/img/simu.jpg)

![Figura-10.] PAT (wainhira host LAN simu reply husi Server)

Ordem ba iptables Router Linux:

    # iptables -t nat -A POSTROUTING -s 10.0.0.0/24 -j SNAT –-to 2.2.2.2

ou

    # iptables -t nat -A POSTROUTING -s 10.0.0.0/24 -j MASQUERADE

Ordem ba MikroTik Router OS:

    # ip firewall nat add chain=srcnat src-address=10.0.0.0/24 \
  action=src-nat to-addresses=2.2.2.2
atau
    # ip firewall nat add chain=srcnat src-address=10.0.0.0/24 action=masquerade

Ida nee mak modelu seluk husi implementasaun Port Address Translation.

![Figura 1](http://127.0.0.1/grey/img/portforward.jpg)
Figura-11. PAT (bai-bain konyese ho naran Port Forwarding)

Ordem ba iptables Router Linux:

    # iptables -t nat -A PREROUTING -p tcp --dport 2100 -d 2.2.2.2 -j DNAT --to 10.0.0.2:80

Perintah MikroTik Router OS:

    # ip firewall nat add chain=dstnat dst-address=2.2.2.2 dst-port=2100 \
  action=dst-nat to-addresses=10.0.0.2 to-ports=80


![Figura 1](http://127.0.0.1/grey/img/portdirek.jpg)
Figura-12. PAT (bai-bain koyese ho naran Port Redirection)

Ordem ba iptables Router Linux:

    # iptables -t nat -A PREROUTING -s 10.0.0.0/24 -p tcp --dport 80 -j DNAT --to 2.2.2.3:3128


Ordem ba MikroTik Router OS:

    # ip firewall nat add chain=dstnat src-address=10.0.0.0/24 protocol=tcp dst-port=80 \
  action=dst-nat to-addresses=2.2.2.3 to-ports=3128




:: Estuda didiak baa ::
