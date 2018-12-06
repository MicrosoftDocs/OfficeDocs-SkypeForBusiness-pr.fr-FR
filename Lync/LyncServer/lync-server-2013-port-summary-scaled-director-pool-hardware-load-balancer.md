---
title: "Lync Server 2013 : Résumé des ports - Pool dir. màé, équil. de ch. matérielle"
TOCTitle: Résumé des ports - Pool directeur mis à l’échelle, équilibreur de charge matérielle
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204983(v=OCS.15)
ms:contentKeyID: 49297507
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les ports de pare-feu requis pour un pool de directeurs sont ceux qui sont utilisés pour établir la communication avec le directeur à partir de l’interface interne du serveur Edge ou de l’interface côté interne du proxy inverse. Par défaut, Microsoft Lync Server 2013 s’attend à ce que les ports HTTP/TCP 8080 et HTTPS/TCP 4443 soient ouverts à partir du proxy inverse jusqu’au directeur, ainsi qu’au pool de serveurs frontaux et au serveur frontal. Par ailleurs, une communication SIP (Session Initiation Protocol) doit être établie à partir de l’interface interne du serveur Edge jusqu’au directeur, ainsi qu’au pool de serveurs frontaux et au serveur frontal. Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge jusqu’au pool de serveurs frontaux et au serveur frontal. Une règle qui autorise la communication SIP/MTLS/TCP 5061 à partir du directeur, du pool de serveurs frontaux et du serveur frontal jusqu’à l’interface interne du serveur Edge doit aussi être créée.

### Ports et protocoles de directeur pour les définitions de pare-feu

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle/Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Reçue initialement du côté externe du proxy inverse, la communication est envoyée vers l’adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur ainsi que vers les services web des serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Reçue initialement du côté externe du proxy inverse, la communication est envoyée vers l’adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur ainsi que vers les services web des serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>directeur</p></td>
<td><p>serveur frontal ou pool de serveurs frontaux</p></td>
<td><p>Communication inter-serveurs entre l’adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur et les serveurs frontaux</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clients internes</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Le directeur fournit des services web aux clients internes comme aux clients externes.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clients internes</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Le directeur fournit des services web aux clients internes comme aux clients externes.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Communication SIP à partir du serveur Edge jusqu’au directeur et au serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>directeur</p></td>
<td><p>Collecte des journaux et commandes du contrôleur (ClsController.exe) ou de l’agent (ClsAgent.exe) du service de journalisation centralisée</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>directeur</p></td>
<td><p>Collecte des journaux et commandes du contrôleur (ClsController.exe) ou de l’agent (ClsAgent.exe) du service de journalisation centralisée</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>directeur</p></td>
<td><p>Collecte des journaux et commandes du contrôleur (ClsController.exe) ou de l’agent (ClsAgent.exe) du service de journalisation centralisée</p></td>
</tr>
</tbody>
</table>

