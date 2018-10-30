---
title: 'Lync Server 2013 : Résumé des ports - Équilibrage de charge DNS et matérielle'
TOCTitle: Résumé des ports - Équilibrage de charge DNS et matérielle
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205179(v=OCS.15)
ms:contentKeyID: 49298567
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Équilibrage de charge DNS et matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les conditions requises pour les ports du pare-feu pour un directeur unique se composent des ports utilisés pour établir une communication avec le directeur à partir de l’interface interne ou du réseau côté interne du proxy inverse. Par défaut, Microsoft Lync Server 2013 s’attend à ce que les ports HTTP/TCP 8080 et HTTPS/TCP 4443 soient ouverts du proxy inverse jusqu’au directeur, ainsi qu’au pool de serveurs frontaux et au serveur frontal. De plus, il doit exister une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur, ainsi que vers le pool de serveurs frontaux et le serveur frontal. Le protocole SIP utilise la communication SIP/MTLS/TCP 5061 du serveur Edge vers le pool de serveurs frontaux et le serveur frontal. Une règle autorisant la communication SIP/MTLS/TCP 5061 du directeur, du pool de serveurs frontaux et du serveur frontal vers l’interface internet du serveur Edge doit également être créée.

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
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Initialement reçue par le côté externe du proxy inverse, la communication est envoyée à l’adresse IP virtuelle HLB du directeur et aux services web du serveur frontal.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du directeur</p></td>
<td><p>Initialement reçue par le côté externe du proxy inverse, la communication est envoyée à l’adresse IP virtuelle HLB du directeur et aux services web du serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>directeur</p></td>
<td><p>pool de serveurs frontaux or serveur frontal</p></td>
<td><p>Communication entre serveurs entre l’adresse IP virtuelle du directeur et le serveur frontal ou les serveurs frontaux.</p></td>
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
<td><p>directeur</p></td>
<td><p>Communication SIP du serveur Edge vers le directeur, ainsi que vers les serveurs frontaux.</p></td>
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

