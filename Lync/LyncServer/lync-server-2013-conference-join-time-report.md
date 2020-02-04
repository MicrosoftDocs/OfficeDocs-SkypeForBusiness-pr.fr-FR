---
title: 'Lync Server 2013 : rapport de temps de participation à la Conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce80d3c61e94752423c70de9827d41243da7119
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Rapport de temps de participation à une conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-23_

Le résumé des heures d’arrivée aux conférences vous permet de déterminer le temps nécessaire à vos utilisateurs pour rejoindre une conférence. Le rapport indique le temps nécessaire moyen (en millisecondes) et fournit également une répartition montrant combien d’utilisateurs ont pu rejoindre la conférence en 2 secondes ou moins, combien ont nécessité entre 2 et 5 secondes, etc.

<div>

## <a name="accessing-the-conference-join-time-report"></a>Accès au rapport des heures d’arrivée aux conférences

Le rapport des heures d’arrivée aux conférences est accessible à partir de la page d’accueil des Rapports de suivi.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport du temps de participation aux conférences.

### <a name="conference-join-time-report-filters"></a>Filtres du rapport des heures d’arrivée aux conférences

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
<td><p><strong>Intervalle</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions de conférence</strong></p></td>
<td><p>Type de session. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Sessions Focus (gestionnaire central des états et stratégies pour les téléconférences, le Focus coordonne tous les aspects d’une conférence)</p></li>
<li><p>Partage d’application</p></li>
<li><p>Conférence A/V</p></li>
</ul>
<p>Si vous sélectionnez [Tout], total des heures d’arrivée aux conférences s’affiche en haut du rapport. Notez que ces totaux ne concernent que les conférences planifiées à l’aide de Microsoft Exchange ou Microsoft Outlook.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le rapport des heures d’arrivée aux conférences.

### <a name="conference-join-time-report-metrics"></a>Mesures du rapport des heures d’arrivée aux conférences

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
<td><p><strong>Date</strong></p>
<p>Le titre réel de cette mesure varie en fonction de l’intervalle sélectionné.</p></td>
<td><p>Non</p></td>
<td><p>Date et heure des conférences.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Moyenne (ms)</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps moyen (en millisecondes) nécessaire aux participants pour rejoindre la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions &lt; 2 secondes, volume</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de participants ayant pu rejoindre la conférence en moins de 2 secondes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions &lt; 2 secondes, pourcentage</strong></p></td>
<td><p>Non</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Sessions 2-5 secondes, Volume</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de participants ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions 2-5 secondes, Pourcentage</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage du total des participants à l’appel ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions 5-10 secondes, Volume</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de participants ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions 5-10 secondes, Pourcentage</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage du total des participants à l’appel ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions &gt; 10 secondes, volume</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de participants ayant nécessité plus de 10 secondes pour rejoindre la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions &gt; 10 secondes, pourcentage</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage du total des participants à l’appel ayant nécessité plus de 10 secondes pour rejoindre la conférence.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

