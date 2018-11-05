---
title: "Lync Server 2013 : Résumé DNS - Pool directeur màé, équilibreur de ch. mat."
TOCTitle: Résumé DNS - Pool directeur mis à l’échelle, équilibreur de charge matérielle
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204655(v=OCS.15)
ms:contentKeyID: 49296174
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé DNS - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ci-dessous contient un résumé des enregistrements DNS requis pour prendre en charge le directeur avec charge matérielle équilibrée. Le rôle du directeur nécessite des enregistrements DNS similaires à ceux du serveur frontal. Le nombre d’enregistrements nécessaires est reflété dans les autres noms de sujet requis sur le certificat du directeur. Différent du serveur frontal, le pool de directeurs n’héberge ni les comptes d’utilisateur, ni les services de mobilité.

### Enregistrements DNS requis pour le pool de directeurs utilisant un équilibreur de la charge matérielle et l’équilibrage de charge DNS

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
<td><p>Enregistrement d’hôte directeur utilisé pour la réplication et les communications serveur à serveur</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Adresse IP virtuelle du programme d’équilibrage de la charge matérielle du pool de directeurs</p></td>
<td><p>Enregistrement d’hôte du pool de directeurs avec charge DNS équilibrée</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Adresse IP virtuelle du pool de directeurs avec charge matérielle équilibrée</p></td>
<td><p>Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Adresse IP virtuelle du pool de directeurs avec charge matérielle équilibrée</p></td>
<td><p>Services web de numérotation publiés avec charge matérielle équilibrée à partir d’un proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Adresse IP virtuelle du pool de directeurs avec charge matérielle équilibrée</p></td>
<td><p>Services web de conférence publiés avec charge matérielle équilibrée à partir d’un proxy inverse</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Adresse IP virtuelle du pool de directeurs avec charge matérielle équilibrée</p></td>
<td><p>Charge matérielle équilibrée, publiée et définie par les services web externes de ticket web du proxy inverse pour le pool de directeurs</p></td>
</tr>
</tbody>
</table>

