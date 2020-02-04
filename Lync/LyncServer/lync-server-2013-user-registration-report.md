---
title: 'Lync Server 2013 : rapport sur l’inscription des utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 079e6cb96a9401d909be4f459d7bbe7c3f6d4ed6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Rapport sur l’inscription des utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Le rapport sur l’inscription des utilisateurs fournit une vue d’ensemble de l’activité de connexion des utilisateurs, en particulier des informations sur le nombre d’utilisateurs connectés à Microsoft Lync Server 2013 pendant une période spécifiée (horaire, quotidienne, hebdomadaire, mensuel). N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session. Il ne vous apprend pas *qui* a ouvert une session. Les rapports d’analyse ne fournissent pas d’informations sur les utilisateurs spécifiques utilisant Lync Server 2013 (et ceux qui ne le sont pas). Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.

Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes. Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes. Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise). Les ouvertures de session externes représentent les utilisateurs qui se sont connectés depuis l’extérieur du pare-feu par le biais d’un serveur Edge (par exemple, un utilisateur qui s’est connecté à partir d’un cafés Internet compte comme une connexion externe). Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.

En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs *actifs* qui étaient présents pendant une période donnée. Un utilisateur actif est un utilisateur qui a participé à une session de messagerie instantanée, a participé à une réunion Lync, a émis ou reçu un appel téléphonique ou a utilisé Lync Server pendant la période écoulée. Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.

<div>

## <a name="accessing-the-user-registration-report"></a>Accès au rapport d’enregistrement de l’utilisateur

Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilisation optimale du rapport d’enregistrement de l’utilisateur

Après avoir déployé Lync Server, vous devez répondre aux questions fréquemment posées : Comment savoir si mes utilisateurs utilisent réellement cette nouvelle technologie ? Même s’il est quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question. Pour déterminer si des utilisateurs utilisent ou non Lync Server, vous devez effectuer deux opérations. Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur. Cette valeur indique le nombre d’utilisateurs distincts qui se sont connectés à Lync Server.

Par comparaison, la métrique total des ouvertures de session indique le nombre total de fois où quiconque s’est connecté à Lync Server. Par exemple, supposons que Ken Myer s’est connecté à Lync Server cinq fois par jour. Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session. De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements. Par exemple, l’utilisateur peut se connecter à l’aide d’un ordinateur de bureau, d’un ordinateur portable et peut disposer d’un téléphone IP qui ouvre automatiquement une session sur Lync Server. Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.

Pour mieux expliquer la différence entre le nombre total d’ouvertures de session et les utilisateurs uniques par ouverture de session, examinez les ouvertures de session pour une période donnée dans le tableau suivant.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Utilisateur</th>
<th>Date/heure d’ouverture de session</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:45 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:46 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:17 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:31 AM</p></td>
</tr>
</tbody>
</table>


Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Cela illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.

En plus de connaître le nombre d’ouvertures de session uniques, vous devez connaître le nombre total d’utilisateurs qui ont été activés pour Lync Server. Cette valeur peut être récupérée en ouvrant Lync Server 2013 Management Shell et en exécutant la commande Windows PowerShell suivante :

    (Get-CsUser).Count

Si la commande précédente renvoie une valeur de 1 236 et que la métrique des utilisateurs de connexion unique renvoie une valeur moyenne de 667, qui vous suggère qu’un peu plus de la moitié de vos utilisateurs est en train de se connecter au système chaque jour (667 divisé par 1 236 est approximativement de 54%).

<div>


> [!WARNING]  
> Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée. Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système. Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système. Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session. Cela signifie que vous avez réellement reçu une connexion de plus de 1 000 utilisateurs à Lync Server, ce qui signifie que plus près de 80% de vos utilisateurs ont été connectés.



</div>

Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques. La métrique utilisateurs actifs uniques indique le nombre d’utilisateurs uniques qui ont réellement utilisé Lync Server : ils ont effectué un appel téléphonique, ils ont rejoint une réunion Lync ou ont participé à une session de messagerie instantanée. Il s’agit d’informations utiles, car Microsoft Lync 2013 peut être configuré pour démarrer automatiquement chaque fois qu’un utilisateur démarre Windows. Pour cette raison, il est possible que vous disposiez d’un grand nombre d’utilisateurs qui se connectent automatiquement à Lync quand ils se connectent à Windows tous les jours, mais qu’ils n’utilisent jamais réellement Lync Server pendant cette période.

La métrique unique des utilisateurs actifs fournit également des données plus significatives au sein d’une organisation dans laquelle les utilisateurs ne ferment pas de fenêtre à la fin de la journée. Au lieu de cela, ils verrouillent simplement leur ordinateur et laissent Windows et Lync en cours d’exécution. Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée. Toutefois, les utilisateurs actifs uniques vous indiquent si les utilisateurs utilisent activement Lync ou un autre client Lync Server.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport sur l’inscription des utilisateurs vous permet d’afficher les données de l’ensemble de votre pool d’inscriptions et de vos serveurs Edge, ou d’afficher les données d’un pool individuel. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les enregistrements sont groupés par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’enregistrement de l’utilisateur.

### <a name="user-registration-report-filters"></a>Filtres du rapport d’enregistrement de l’utilisateur

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’enregistrement de l’utilisateur.

### <a name="user-registration-report-metrics"></a>Mesures du rapport d’enregistrement de l’utilisateur

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
<td><p><strong>Toutes les heures</strong></p>
<p><strong>Jour</strong></p>
<p><strong>Toutes les semaines</strong></p>
<p><strong>Mois</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle quotidien et que vous cliquez sur 7/7/2012, vous pouvez voir une répartition horaire de l’activité d’inscription des utilisateurs à cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total d’ouvertures de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’ouvertures de sessions réussies.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ouvertures de sessions internes</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’ouvertures de sessions dans le réseau interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ouvertures de sessions externes</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’ouvertures de sessions de l’extérieur du réseau interne, à l’aide du serveur Edge.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utilisateurs uniques par ouverture de session</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs qui ont ouvert au moins une session. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utilisateurs actifs uniques</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs qui ont été impliqués dans une session P2P ou de conférence. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

