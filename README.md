# UniversalRobot + OnRobot Eyes Guide
Guide til at bruge OnRobot Eyes til Universal Robot

Det første vi starter med, er at tilslutte kameraet til robotten, i dette eksempel er der brugt en UR3e.
Først åbnes pakken og kameraet installeres med de dertilhørende skruer. 
Boksen der følger med, ser således ud:
![image](https://github.com/user-attachments/assets/cb846df7-551e-4473-b04d-34c7a591556b)


Ved det grønne tilsluttes strømmen, med den tilhørende strømtilslutning. 
USB kablet, skal sættes i det røde og derefter indsættes i On-Robot-Eyes på siden.
Til at kommunikere, skal der sættes et ethernet kabel i den blå og den anden ende i switchen og fra switchen til robottens Ethernet indgang. 
Som det kan ses i det turkise område har kameraet en fixed IP: 192.168.1.1. I og med at vi også skal vise kommunikation med en PLC, som skal køre igennem en router med samme IP-adresse, har vi nu følgende mulighed:
I det lilla område sidder der 4 dip-switches. Hvis alle 4 peger nedad, betyder det at DHCP bliver aktivt og kameraet opretter derefter selv en ip-adresse indenfor 192.168.1.100 - 105 
Subnet (255.255.255.0).
Vi går nu videre til hvordan installationen fortsættes i TeachPendant.
Med i kassen til On-Robot-Eyes er der et USB-stik, dette indsættes i TeachPendant, herefter følger vi denne guide:

![image](https://github.com/user-attachments/assets/f8ec2a7e-c669-4a8f-a585-17e948574785)

![image](https://github.com/user-attachments/assets/668dadaf-68bb-4129-bcfa-0c3281eacf21)


Nu skal vi konfigurere kameraet i URCaps, her følges guiden igen:
!!!VIGTIGT!!!  Før der kan skabes en forbindelse er det vigtigt at alle fieldbusses er deaktiveret, disse findes under installations fanen og derefter fieldbus.

![image](https://github.com/user-attachments/assets/302566b3-a10b-40e3-94ce-fe48cdea9d8a)

![image](https://github.com/user-attachments/assets/440441df-35e2-4936-ae09-a533b5f9fc20)


![image](https://github.com/user-attachments/assets/04b3c1e7-4fab-4241-8249-a924a6bedfa2)

![image](https://github.com/user-attachments/assets/180aba95-2dce-4375-b36c-7f45055c75ee)

![image](https://github.com/user-attachments/assets/0b22dcec-f21d-4b76-8976-4e601c9cda3b)

![image](https://github.com/user-attachments/assets/3dd7cd0c-e616-40eb-a7b8-de0bc7ad6a59)

![image](https://github.com/user-attachments/assets/34ecff64-addc-4021-b185-61c6733c56a2)

![image](https://github.com/user-attachments/assets/654d7bef-3ee4-463c-9fa5-f2a55daebe82)

![image](https://github.com/user-attachments/assets/b4a511ab-f006-43f3-a4a4-f5eb61e60d50)

![image](https://github.com/user-attachments/assets/65242ed1-2da3-4cf9-a259-d24913a34cdb)

![image](https://github.com/user-attachments/assets/457054c1-b7f0-44a9-8a0d-9f33ecec14fd)

![image](https://github.com/user-attachments/assets/f539ba7a-582d-4a08-b608-ae35f0c751dd)

![image](https://github.com/user-attachments/assets/28267bd7-e44b-48ed-98a8-3a5e1ce5d605)

![image](https://github.com/user-attachments/assets/cf9596ab-6484-4b31-920b-d175d182355c)

![image](https://github.com/user-attachments/assets/11a32ae5-b6d2-4ac8-825e-3c10a513ed17)

![image](https://github.com/user-attachments/assets/d86da1d6-cb94-479f-b76d-ae1d93a1b38d)

## **Opsætning i Control Expert**
I topmenuen vælg “**Tools**” og “**DTM-browser**”
I DTM-browser højre-klik på din PLC, vælg ”**Device Menu**”, ”**Additional Functions**”, ”**Add EDS to library**”. \
![image](https://github.com/user-attachments/assets/48cec715-8978-4fac-b4c9-6317ef4ec32e) 

Nu får du EDS import guiden op. Vælg ”**Next**”, og vælg .EDS filen til din Universal Robot. Vælg ”**Next**”, ”**Next**” og ”**Finish**”\
![image](https://github.com/user-attachments/assets/b38a5229-3789-43eb-92b6-4b7c6836ac3f) 

Efter .EDS filen er tilføjet **SKAL** du genstarte Control Expert for at opdatere .EDS cataloget \
Højreklik på din PLC i DTM-browseren igen, og vælg ”**Add..**”. Tryk på ”**Protocol**” dropdown menuen, og vælg ”**Ethernet/IP**”. Og find Universal Robot filen \
![image](https://github.com/user-attachments/assets/5020be2d-b150-4faa-8933-77b65b80d9a7) 

Dobbelt-klik på din PLC i DTM-browseren, og find din nyligt tilføjede Universal Robot Ip-adresse under ”**Address setting**”. Giv den en korrekt IP-adresse, og tryk ”**Apply**” \
![image](https://github.com/user-attachments/assets/733460ee-e408-4514-8fe5-26e055a7431b) 

Din PLC burde nu være forbundet til Universal Robot via Ethernet/IP.\
Du kan evt. lave et animation table for at bekræfte kommunikationen, og hvilket data kommer hvorhen\
![image](https://github.com/user-attachments/assets/199bb501-43e1-4e33-9a35-49d09782f627)

Vi har i denne guide blot lavet en simpel kamera inspektion hvor DINT_Output_Register_1 bliver sat til 1, hvis kameraet detekterer et korrekt element.\
![image](https://github.com/user-attachments/assets/e1d93db5-0cea-4447-a2f1-a85f1c41ea0c)

![image](https://github.com/user-attachments/assets/de2909fd-3d3c-4c4f-b819-490717ed00a5)


