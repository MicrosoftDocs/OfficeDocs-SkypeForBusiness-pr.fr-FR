---
title: 'Lync Server 2013 : Résumé des enregistrements DNS - Un directeur'
TOCTitle: Résumé des enregistrements DNS - Un directeur
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205021(v=OCS.15)
ms:contentKeyID: 49297792
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Un directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ci-dessous contient une synthèse des enregistrements DNS requis pour prendre en charge le directeur unique. Le rôle de directeur requiert des enregistrements DNS similaires au serveur frontal. Le nombre d’enregistrements requis est reflété dans les autres noms du sujet requis sur le certificat directeur. Différent du serveur frontal, le directeur n’héberge pas de comptes d’utilisateur ni de services de mobilité.

### Enregistrements DNS requis pour le directeur

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/Port</th>
<th>Nom de domaine complet/enregistrement DNS</th>
<th>Adresse IP/nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>directeur</p></td>
<td><p>Enregistrement d’hôte du directeur utilisé pour la réplication et serveur à serveur</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>directeur</p></td>
<td><p>Protocole SIP (Session Initiation Protocol) entrant de l’interface Edge interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>directeur</p></td>
<td><p>Services web d’accès à distance publiés depuis le proxy inverse</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>directeur</p></td>
<td><p>Services web de réunion publiés depuis le proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>directeur</p></td>
<td><p>Publié et défini par les services web externes Web Ticket du proxy inverse pour le directeur</p></td>
</tr>
</tbody>
</table>

