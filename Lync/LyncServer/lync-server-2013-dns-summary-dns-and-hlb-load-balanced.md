---
title: "Lync Server 2013 : Résumé des enr. DNS - Éq. de ch. DNS et matérielle"
TOCTitle: Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205273(v=OCS.15)
ms:contentKeyID: 49298934
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ci-dessous fournit un résumé des enregistrements DNS requis pour prendre en charge le directeur avec charge DNS équilibrée et charge matérielle équilibrée. Le rôle du directeur nécessite des enregistrements DNS similaires à ceux du serveur frontal. Le nombre d’enregistrements demandé se reflète dans les noms de sujets alternatifs requis sur le certificat directeur. À la différence du serveur frontal, le pool de directeurs n’héberge pas de comptes d’utilisateur ou les services de mobilité.

### Enregistrements DNS nécessaires pour le pool de directeurs en utilisant l’équilibrage de la charge DNS et le programme d’équilibrage de la charge matérielle

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>pool de directeurs</p></td>
<td><p>Enregistrement d’hôte pour le pool de directeurs avec charge DNS équilibrée pour serveur à serveur</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>pool de directeurs</p></td>
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
<td><p>Services web externes de tickets web publiés et définis par le proxy inverse avec charge matérielle équilibrée pour le pool de directeurs</p></td>
</tr>
</tbody>
</table>

