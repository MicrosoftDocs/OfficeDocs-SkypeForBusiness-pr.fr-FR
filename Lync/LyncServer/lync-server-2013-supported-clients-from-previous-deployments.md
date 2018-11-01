---
title: 'Lync Server 2013 : Clients pris en charge provenant d’anciens déploiements'
TOCTitle: Clients pris en charge provenant d’anciens déploiements
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398499(v=OCS.15)
ms:contentKeyID: 49297500
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clients pris en charge provenant d’anciens déploiements dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Dans un scénario de coexistence, les clients Lync Server 2013 peuvent interagir avec des clients exécutant des versions antérieures de Lync Server et d’Office Communications Server. Contrairement aux versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013. Cela permet aux organisations qui effectuent une mise à niveau à partir de Lync Server 2010 de déployer les clients indépendamment des mises à niveau de Lync Server.

## Combinaisons de serveur et de client prises en charge

Le tableau ci-dessous dresse la liste des combinaisons prises en charge selon la version du client et du serveur. Lync Server 2013 prend en charge deux versions de client antérieures et Lync Server 2010 prend en charge le nouveau client Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Intendant Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Conversation de groupe Lync 2010</p></td>
<td><p>Non applicable</p></td>
<td><p>Pris en charge1</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Participant Lync 2010</p></td>
<td><p>Non pris en charge2</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interopérable3</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Intendant Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
</tbody>
</table>


1Dans Microsoft Lync Server 2010, la conversation de groupe était disponible avec le serveur de conversation de groupe, application approuvée tierce pour Lync Server 2010. Les clients Lync 2013 ne sont pas compatibles avec Lync Server 2010, conversation de groupe.

2Lync Web App 2013 offre à présent un environnement de réunion complet, incluant le son et la vidéo, et est considéré comme remplaçant Participant Lync 2010.

3Les fonctionnalités de présence et de messagerie instantanée dans Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, contrairement aux fonctionnalités de conférence. Pendant la migration depuis Office Communications Server 2007 R2, Office Communicator 2007 R2 convient pour l’interopérabilité avec les fonctionnalités de présence et de messagerie instantanée, mais les utilisateurs doivent recourir à Lync Web App 2013 pour participer aux réunions Lync Server 2013.

> [!NOTE]  
> Pour plus d’informations sur la possibilité pour les clients Lync Server 2013 de coexister et d’interagir avec des clients exécutant des versions antérieures de Lync Server et d’Office Communications Server, reportez-vous à <a href="lync-server-2013-client-interoperability-in-lync-2013.md">Interopérabilité des clients dans Lync 2013</a> dans la documentation de planification.
