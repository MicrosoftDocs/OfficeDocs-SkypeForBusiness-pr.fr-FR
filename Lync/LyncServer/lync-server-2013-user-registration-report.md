---
title: 'Lync Server 2013 : rapport d’enregistrement de l’utilisateur'
description: 'Lync Server 2013 : rapport d’enregistrement de l’utilisateur.'
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
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569750"
---
# <a name="user-registration-report-in-lync-server-2013"></a>Rapport d’enregistrement de l’utilisateur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Le rapport d’enregistrement de l’utilisateur fournit une vue d’ensemble de l’activité d’ouverture de session de l’utilisateur, notamment des informations sur le nombre d’utilisateurs connectés à Microsoft Lync Server 2013 pendant une période spécifiée (toutes les heures, tous les jours, toutes les semaines, tous les mois). N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session. Il ne vous apprend pas *qui* a ouvert une session. Les rapports de surveillance ne fournissent pas d’informations sur les utilisateurs spécifiques qui utilisent Lync Server 2013 (et ceux qui ne le sont pas). Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.

Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes. Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes. Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise). Les ouvertures de session externes représentent les utilisateurs qui se sont connectés depuis l’extérieur du pare-feu via un serveur Edge (par exemple, un utilisateur qui a ouvert une session à partir d’un cybercafé sur Internet compte comme une ouverture de session externe). Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.

En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs *actifs* qui étaient présents pendant une période donnée. Un utilisateur actif est un utilisateur qui a participé à une session de messagerie instantanée (IM), a participé à une réunion Lync, a effectué ou reçu un appel téléphonique ou utilisé Lync Server pendant cette période de temps. Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.

<div>

## <a name="accessing-the-user-registration-report"></a>Accès au rapport d’enregistrement de l’utilisateur

Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilisation optimale du rapport d’enregistrement de l’utilisateur

Une fois que vous avez déployé Lync Server, une question fréquemment posée est la suivante : Comment savoir si mes utilisateurs utilisent réellement cette nouvelle technologie ? Bien qu’il soit quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question. Pour déterminer si les utilisateurs utilisent ou non Lync Server, vous devez effectuer deux opérations. Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur. Cette valeur indique le nombre de personnes qui ont ouvert une session sur Lync Server.

Par comparaison, la mesure nombre total d’ouvertures de session indique le nombre total de fois qu’une personne s’est connectée à Lync Server. Par exemple, supposons que Ken Myer s’est connecté à Lync Server cinq fois par jour. Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session. De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements. Par exemple, un utilisateur peut se connecter à l’aide de son ordinateur de bureau, son ordinateur portable, et il peut disposer d’un téléphone IP qui se connecte automatiquement à Lync Server. Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.

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
<td><p>7/7/2012 8 h 45</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8 h 46</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9 h 17</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9 h 22</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9 h 31</p></td>
</tr>
</tbody>
</table>


Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Ceci illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.

En plus de connaître le nombre d’ouvertures de session uniques, vous devez connaître le nombre total d’utilisateurs qui ont été activés pour Lync Server. Cette valeur peut être récupérée en ouvrant Lync Server 2013 Management Shell et en exécutant la commande Windows PowerShell suivante :

    (Get-CsUser).Count

Si la commande précédente renvoie la valeur 1 236 et que la mesure utilisateurs uniques de l’ouverture de session renvoie une valeur moyenne de 667, cela indique qu’un peu plus de la moitié de vos utilisateurs permettent à Lync de se connecter en réalité au système chaque jour (c’est-à-dire, 667 divisé par 1 236, soit environ 54%).

<div>


> [!WARNING]  
> Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée. Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système. Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système. Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session. Cela signifie que vous disposiez en réalité de près de 1 000 utilisateurs connectés à Lync Server, ce qui signifie que plus près de 80% de vos utilisateurs étaient connectés.



</div>

Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques. La mesure utilisateurs actifs uniques indique le nombre d’utilisateurs uniques qui ont réellement utilisé Lync Server : ils ont effectué un appel téléphonique, ils ont rejoint une réunion Lync ou ont participé à une session de messagerie instantanée. Il s’agit d’informations utiles, car Microsoft Lync 2013 peut être configuré pour démarrer automatiquement chaque fois qu’un utilisateur démarre Windows. Pour cette raison, vous avez peut-être un grand nombre d’utilisateurs qui se connectent automatiquement à Lync lorsqu’ils se connectent à Windows chaque jour, mais qui n’utilisent jamais en réalité Lync Server pendant cette période.

La mesure utilisateurs actifs uniques fournit également des données plus significatives dans une organisation où les utilisateurs ne se déconnectent généralement pas de Windows à la fin de la journée. Au lieu de cela, ils verrouillent leur ordinateur et laissent Windows et Lync en cours d’exécution. Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée. Toutefois, les utilisateurs actifs uniques indiquent si les utilisateurs utilisent Lync ou un autre client Lync Server activement.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’enregistrement de l’utilisateur vous permet d’afficher les données de l’ensemble de votre pool de serveurs d’inscriptions et de vos serveurs Edge ou d’afficher les données d’un pool individuel. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les enregistrements sont groupés par heure, jour, semaine ou mois.

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
<td><p><strong>Interval</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début de 7/8/2012 et une date de fin de 28/9/2012, les données sont affichées pour les jours compris entre le 7/8/2012 à 12 h 00 et le 7/9/2012 à 12 h 00 (c’est-à-dire un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez soit sélectionner un pool individuel soit cliquer sur <strong>[Tous]</strong> pour afficher les données pour tous les pools. La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données.</p></td>
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
<p><strong>Journalière</strong></p>
<p><strong>Hebdomadaire</strong></p>
<p><strong>Mensuelle</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps que vous avez sélectionné sur la barre d’outils du filtre. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher les informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, vous voyez un décompte horaire de l’activité d’enregistrement de l’utilisateur pour cette date.</p></td>
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
<td><p>Nombre total d’utilisateurs qui ont été impliqués dans une session d’égal à égal ou de conférence. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

