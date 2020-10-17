---
title: 'Lync Server 2013 : rapport d’utilisation de Response Group'
description: 'Lync Server 2013 : rapport d’utilisation de Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e541a618e8578debc84630037d530c96f4e39ea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553060"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a>Rapport d’utilisation de Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

L’application Response Group permet à Microsoft Lync Server 2013 de répondre et d’acheminer les appels téléphoniques en fonction du numéro composé et, éventuellement, des réponses de l’appelant à une série de questions. En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents. Par exemple, si une personne appelle le numéro de téléphone de votre support technique, Lync Server 2013 peut automatiquement acheminer cet appel vers le premier agent de support disponible. En guise d’alternative, Lync Server peut poser une série de questions («appuyez sur 1 si vous rencontrez des problèmes de matériel. Appuyez sur 2 pour des problèmes logiciels. Appuyez sur 3 Si vous rencontrez des problèmes réseau. ") puis Acheminez l’appel vers l’agent du support technique le plus approprié en fonction de la réponse à ces questions.

Le rapport d’utilisation de Response Group donne une vision détaillée du nombre d’appels téléphoniques reçus par tous vos flux de travail Response Group, puis répartit ces appels en catégories plus précises telles que Appels offerts, Appels ayant obtenu une réponse et Appels abandonnés.

La meilleure façon de tirer parti du rapport d’utilisation de Response Group est de comprendre la différence entre les types d’appel signalés :

  - **Appels reçus** : nombre total d’appels reçus par toutes les instances de l’application Response Group.

  - **Appels réussis**. Nombre total d’appels qui ont été sélectionnés par l’application Response Group.

  - **Appels offerts** : nombre total d’appels transférés à un agent Response Group.

  - **Appels ayant obtenu une réponse** : nombre total d’appels auxquels un agent Response Group a effectivement répondu.

  - **Pourcentage d’appels abandonnés** : pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous recevez 10 appels dont 7 avec réponse, vous retranchez 7 de 10 et obtenez donc 3 appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous donne un pourcentage d’appels abandonnés de 30 %.

  - **Appels transférés** : nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de saturation de la file d’attente.

Si vous examinez le rapport d’utilisation de Response Group et que vous ne vous souvenez pas de la définition des types d’appels indiqués, il suffit de pointer le curseur de la souris sur l’étiquette du type d’appel concerné et une info-bulle apparaît contenant une brève description du type de l’appel.

Le rapport d’utilisation de Response Group vous permet de filtrer sur un URI de flux de travail (l’adresse SIP associée à ce flux de travail). Toutefois, les URI de flux de travail n’apparaissent pas réellement dans le rapport. Si vous cherchez à identifier les flux de travail qui répondent le plus aux appels ou ceux qui reçoivent le plus d’appels transférés, cliquez sur la mesure appropriée pour ouvrir le rapport des listes d’appels Response Group pour la période donnée. Ce rapport, en revanche, indique les URI de flux de travail.

<div>

## <a name="accessing-the-response-group-usage-report"></a>Accéder au rapport d’utilisation de Response Group

Le rapport d’utilisation de Response Group est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez accéder au [rapport liste des appels Response Group dans Lync Server 2013](lync-server-2013-response-group-call-list-report.md) en cliquant sur l’une des mesures suivantes :

  - Appels reçus

  - Appels réussis

  - Appels offerts

  - Appels ayant obtenu une réponse

  - Appels transférés

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Tirer le meilleur parti du rapport d’utilisation de Response Group

L’utilisation la plus intéressante de ce rapport n’est peut-être pas la plus évidente : il s’agit de sa capacité à recueillir des informations d’utilisation pour un seul flux de travail Response Group.

<div>


> [!WARNING]  
> Un flux de travail Response Group est fondamentalement un ensemble d’instructions qui déterminent le rôle de Lync Server lorsqu’un utilisateur compose un numéro de téléphone particulier. À cette fin, chaque flux de travail est associé de manière unique à un numéro de téléphone. Lorsqu’une personne appelle ce numéro, le flux de travail détermine la manière dont l’appel sera géré. Par exemple, le flux de travail peut entraîner le routage de l’appel vers une série de questions de réponse vocale interactive (IVR) invitant l’appelant à entrer des informations supplémentaires («appuyez sur 1 pour obtenir de l’assistance matérielle. Appuyez sur 2 pour obtenir une assistance logicielle. "). En guise d’alternative, le flux de travail peut entraîner le placement de l’appel dans une file d’attente, l’appelant étant mis en attente jusqu’à ce qu’un agent soit disponible pour répondre à l’appel. La disponibilité des agents pour répondre aux appels dépend également du workflow : les workflows permettent de définir les heures ouvrées (jours de la semaine et heures pendant lesquels les agents sont disponibles pour répondre aux appels) et les congés (jours pendant lesquels aucun agent n’est disponible pour répondre aux appels). Chaque fois que vous composez un numéro de téléphone qui appartient à l’application Response Group, vous appelez un flux de travail Response Group.



</div>

Bien que les URI de flux de travail n’apparaissent pas dans le rapport d’utilisation de Response Group, il est encore possible d’afficher les statistiques d’utilisation pour un seul flux de travail, ce qui est souvent très utile. Par exemple, supposons que vous avez récemment lancé une nouvelle campagne publicitaire et que vous souhaitez savoir si des personnes appellent pour en savoir plus sur le produit. Si vous avez associé un flux de travail Response Group au numéro de téléphone indiqué dans la campagne publicitaire, vous pouvez facilement consulter le nombre de personnes (s’il y en a) qui ont appelé ce numéro.

Vous pouvez aussi utiliser une approche similaire pour évaluer le nombre d’appels gérés par votre support technique interne ou votre service client.

Pour passer en revue les statistiques d’utilisation d’un flux de travail en particulier, entrez l’URI du flux de travail dans la zone correspondante. Comme indiqué auparavant, les URI de flux de travail (adresse SIP associée au flux de travail) n’apparaissent pas dans le rapport. Cela signifie que vous devez utiliser un autre moyen pour déterminer l’URI d’un flux de travail. Pour ce faire, vous pouvez utiliser Windows PowerShell et Lync Server Management Shell. Par exemple, cette commande renvoie les URI de tous vos flux de travail Response Group :

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Les données renvoyées seront de ce type :

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Cette commande renvoie les informations relatives à un seul flux de travail, celui qui porte le nom « New Ad Campaign » :

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’utilisation de Response Group vous permet d’afficher les données de tous vos flux de travail Response Group ou d’un seul. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’utilisation de Response Group.

### <a name="response-group-usage-report-filters"></a>Filtres du rapport d’utilisation de Response Group

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
<td><p>Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</p>
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
<p>7/7/2012 1:00 PM</p>
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
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de départ le 07.08.12 et une date de fin le 28.09.12, les données sont affichées pour les jours compris entre le 07.08.12 12:00 AM et le 07.09.12 12:00 AM (soit un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de flux de travail</strong></p></td>
<td><p>Vous permet de limiter les données retournées au flux de travail de Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’utilisation de Response Group.

### <a name="response-group-usage-report-metrics"></a>Mesures du rapport d’utilisation de Response Group

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
<td><p>Indique l’intervalle de temps sélectionné. Si applicable, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07.07.12, vous affichez une répartition horaire de l’activité d’inscription de l’utilisateur à cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels reçus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels reçus par toutes les instances de l’application Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appels réussis</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels auxquels l’application Response Group a répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels offerts</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels qui ont été transférés à un agent Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appels ayant obtenu une réponse</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels auxquels un agent Response Group a effectivement répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’appels abandonnés</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Ce chiffre est calculé en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez 10 appels reçus et sept avec réponse, vous soustrayez sept de 10, et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous fournit un pourcentage d’appels abandonnés de 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minutes d’appel moyennes par agent</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps moyen consacré par un agent Response Group à un appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels transférés</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de saturation de la file d’attente. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

