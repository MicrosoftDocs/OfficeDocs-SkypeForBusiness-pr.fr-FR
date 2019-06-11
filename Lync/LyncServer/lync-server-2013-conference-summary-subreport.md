---
title: 'Lync Server 2013: sous-état synthèse de la Conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b87ea9648404f495f487a639a3b11900f91dcda4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Sous-état synthèse de la Conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-06_

Le sous-rapport de synthèse de conférence fournit une vision générale des sessions de conférence ayant échoué. Ces échecs de session sont répartis par type de session : sessions Focus et les sessions MCU.

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de synthèse de conférence.

### <a name="conference-summary-subreport-filters"></a>Filtres du sous-rapport de synthèse de conférence

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
<td><p><strong>De</strong></p></td>
<td><p>Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le sous-rapport de synthèse de conférence.

### <a name="conference-summary-subreport-metrics"></a>Mesures du sous-rapport de synthèse de conférence

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
<td><p><strong>Nombre total de conférences</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences ayant eu lieu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de sessions de conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions de conférence. Une seule conférence peut avoir plusieurs sessions : par exemple, elle peut inclure à la fois une session Focus et une session MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec de session global</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de tous les échecs de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions Focus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions Focus.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec de focus</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage d’échec des sessions Focus.</p></td>
</tr>
<tr class="even">
<td><p>Sessions MCU</p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec MCU</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage d’échec des sessions MCU.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions MCU par modalité</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec par modalité</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage d’échec des sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

