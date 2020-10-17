---
title: 'Lync Server 2013 : sous-rapport de résumé P2P'
description: 'Lync Server 2013 : sous-rapport de résumé P2P.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557380"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a>Sous-rapport de résumé P2P dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Le sous-rapport de résumé P2P offre un aperçu général de vos sessions de communication pair au pair ayant échoué.

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de résumé P2P.

### <a name="p2p-summary-subreport-filters"></a>Filtres de sous-rapport de résumé P2P

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le sous-rapport de résumé P2P.

### <a name="p2p-summary-subreport-metrics"></a>Mesures de sous-rapport de résumé P2P

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’échec</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions d’égal à égal ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions par modalité</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions groupées par modalité (par exemple, messagerie instantanée).</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’échec par modalité</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué groupées par modalité (par exemple, messagerie instantanée).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

