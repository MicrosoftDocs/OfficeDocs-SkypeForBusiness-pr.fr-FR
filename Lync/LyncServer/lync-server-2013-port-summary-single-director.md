---
title: 'Lync Server 2013 : Résumé des ports - Directeur unique'
TOCTitle: Résumé des ports - Directeur unique
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204648(v=OCS.15)
ms:contentKeyID: 49296164
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Directeur unique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les ports de pare-feu requis pour un seul directeur sont ceux nécessaires à l’établissement des communications avec le Directeur à partir de l’interface interne ou du réseau interne du proxy inverse. Microsoft Lync Server 2013 s’attend par défaut à ce que les ports HTTP/TCP 8080 et HTTPS/TCP 4443 soient ouverts entre le proxy inverse, le directeur, le pool de serveurs frontaux et le serveur frontal. En outre, les communications SIP (Session Initiation Protocol) entre l’interface interne du serveur Edge, le directeur, le pool de serveurs frontaux et le serveur frontal doivent être assurées. Le protocole SIP utilise SIP/MTLS/TCP 5061 entre le serveur Edge, le pool de serveurs frontaux et le serveur frontal. Une règle qui permet les communications SIP/MTLS/TCP 5061 entre le directeur, le pool de serveurs frontaux le serveur frontal et l’interface interne du serveur Edge doit également être créée.

### Définitions des ports et des protocoles de directeur unique pour les pare-feu

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
<td><p>directeur</p></td>
<td><p>Initialement reçues par le côté externe du proxy inverse, les communications sont envoyées aux services web du directeur et du serveur frontal</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>directeur</p></td>
<td><p>Initialement reçues par le côté externe du proxy inverse, les communications sont envoyées aux services web du directeur et du serveur frontal</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>directeur</p></td>
<td><p>Serveur frontal ou pool frontal</p></td>
<td><p>Communications inter-serveurs entre le directeur et le serveur frontal</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clients internes</p></td>
<td><p>Services web du directeur</p></td>
<td><p>Le directeur fournit des services web aux clients internes et externes.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clients internes</p></td>
<td><p>Services web du directeur</p></td>
<td><p>Le directeur fournit des services web aux clients internes et externes.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>directeur</p></td>
<td><p>Communications SIP entre le serveur Edge, le directeur et le serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Commandes et collecte des journaux du contrôleur (ClsController.exe) ou de l’agent (ClasAgent.exe) du service de journalisation centralisée</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Commandes et collecte des journaux du contrôleur (ClsController.exe) ou de l’agent (ClasAgent.exe) du service de journalisation centralisée</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Commandes et collecte des journaux du contrôleur (ClsController.exe) ou de l’agent (ClasAgent.exe) du service de journalisation centralisée</p></td>
</tr>
</tbody>
</table>

