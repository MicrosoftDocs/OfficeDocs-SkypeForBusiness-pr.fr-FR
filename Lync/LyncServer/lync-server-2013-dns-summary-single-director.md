---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-directeur unique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>Résumé des enregistrements DNS-directeur unique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur unique. Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal. Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur. Différent du serveur frontal, le directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.

### <a name="dns-records-required-for-the-director"></a>Enregistrements DNS requis pour le directeur

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>Nom de domaine complet/enregistrement DNS</th>
<th>Adresse IP/Nom de domaine complet</th>
<th>Mappe vers/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>48000b</p></td>
<td><p>Enregistrement d’hôte directeur utilisé pour la réplication et le serveur vers le serveur</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>48000b</p></td>
<td><p>Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface Edge interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>48000b</p></td>
<td><p>Services web d’accès à distance publiés depuis le proxy inverse</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>48000b</p></td>
<td><p>Services web de réunion publiés depuis le proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>48000b</p></td>
<td><p>Publié et défini par les services Web externes de ticket Web de proxy inverse pour le directeur</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

