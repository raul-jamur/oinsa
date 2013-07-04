Title: TCP
Date: 2013-07-04 12:01


TCP Overview
============

Protokol ida nebee mak dala barak liu uja iha Layer Transport mak TCP. Diferensia nebee basiu liu entre TCP no UDP mak problema reliability (diak liu). TCP jeitu connection oriented no belee garantia katak koneksaun entre host nebee atu haruka informasaun no ba iha fatin nebee prefere, Agora UDP nia jeitu connectionless no labele garanti karak prosesu manda ka haruka data.
  
Atu belee garantia katak atu manda ka haruka data, maka TCP sei haruka host atu halo koneksaun (establish connection) uluk tiha lai ho host nebee nia prefere antes atu haruka ka manda data. Ho ida nee halo host rua nee iha preparasaun atu halo data atu belee troka ba malu. Establish connection hotu ona, foin mak data nee belee ona atu haruka ba.Durante prosesu manda ka haruka data nee lao, TCP mos halo maintenance connection (manutensaun ba koneksaun). Ida nee halo atu haruka ka manda Acknowledgment atu parte nebee too tiha ona iha host nebee prefere. Acknowledgment manda husi host nebee atu simu no ba host nebee atu haruka ka manda data hanesan notifikasaun ida katak parte nebee prefere simu tiha ona. Tamba iha Acknowledgment, maka TCP mos iha abilidade atu halo retransmission segment, se karik parte nebee mak la konsege too ba iha host nebee prefere. Prosesu manda ka haruka data hotu ona, maka TCP sei halo terminate connection (terminasaun ba koneksaun). Ida nee signifika katak host nebee manda ka host nebee prefere hatene prosesu manda ka haruka data hotu ona ka remata ona.TCP Three Way Handshake Connection establish entre host nebee manda data no host nebee prefere, halao uja Three Way Handshake. Three Way Handshake sei halao husi host nebee manda data ho manda parte nebee iha SYN Flag ba host nebee prefere. Karik host nebee prefere pronto no hakarak halo komunikasaun, maka host nebee prefere sei manda ba parte nebee iha SYN no ACK Flag. Sei host nebee prefere lakohi atu halo komunikasaun, maka data nebee mak manda ba nee mak parte nebee iha Flag RST, ACK. Karik host host nebee prefere laiha, maka sei laiha informasaun nebee atu fo hatene ba host. Ho Three Way Handshake mak host nebee manda data belee halo kompara kondisaun ruma, atu iha ka laiha host nebee prefere no hakarak ou lakohi host nebee prefere tenki halo komunikasaun.
 
Lalok nebee ikus liu husi Three Way Handshake mak host nebee haruka parte nebee mak iha Flag ACK ba host nebee prefere. Agora atu manda data (komunikasaun) so belee deit akontese wainhira Three Way Handshake remata ka hotu tiha ona. Durante prosesu manda data, host nebee prefere sei haruka Acknowledgment hanesan sinal katak parte ida too tiha ona iha host nebee prefere. Acknowledgment la haruka data ba parte ida-idak, maibe haruka ba parte balu det. Iha parte balu hanaran Window Size.

TCP Session Termination
Karik data nebee manda nee hotu ona, maka TCP sei halo Terminate Connection. Host nebee hatene ou konyese data nebee manda ba hotu ona mak komesa fali prosesu Terminate Connection. Terminate connection halao hamutuk parte Flag FIN no sei fo fali hamutuk ho Flag ACK. Ba komunikasaun ida presija parte atu haruka data nee haat (4), ba FIN ka ba ACK husi host rua nee.
 
TCP Segment Reassembly
Segment husi data ida nebee manda ba iha ISN (Initial Sequence Number) nebee belee halo parte sira nee tuir malu ba stream data. Tambaa parte ida TCP manda data nee belee tuir dalan nebee diferente ba parte ida-idak, maka host prefere tenki belee halo fali data sira nee tuir malu iha parte ida-idak nebee nia simu data nee. Parte sira nee hotu belee mos too iha host nebee prefere la tuir malu.

Rekursu husi : CCNA Exploration 1 (ver 4.0)
Translate husi Raul
Deskulpa karik iha lia fuan balun nebee la los no mos sei sala...
