#Oinsaa Uja SCP ??
SCP liafuan badak husi *Secure Copy* maka fasilidade nebee atu halo transferensia data husi Komputer ida ba Komputer seluk.
Protokolu ida nee lao iha port _(Odamatan)_ 22, no presija aksesu iha shell *(Karik iha Linux)* ba server rua nee.
Tamba pakote data nebee transfere uluk tiha ona hetan ou iha ona Enkripsaun, maka sei akontese velosidade nebee lalais atu transfere data nee, mais ou menos 60-70% kleur liu do que atu uja FTP ou wget husi HTTP.

Ida nee maka ezemplu atu uja SCP atu halo transferensia data;

local ba remote

	scp file_name username@Ip_Address:file_name

remote ba local

	scp username@Ip_Address:file_name file_name

remote ba remote

	scp username@Ip_Address:file_name username@Ip_Address:file_name
	
## Ida Ikus nee Presiza
	Public Private Key encryption
	Shared Keys
