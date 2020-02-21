---
title: 'Lync Server 2013 : rapport des principales défaillances'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972c9e97015f5a39ace3cf1fc68051cc0afcc988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Rapport des principales défaillances dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Le rapport des principales défaillances expose les défaillances les plus fréquentes et leur évolution dans le temps. Les défaillances sont basées sur une combinaison des deux métriques suivantes :

  - **ID de diagnostic**. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP. Les ID de diagnostic fournissent des informations utiles pour résoudre les problèmes liés aux appels.

  - **Code de réponse**. Les codes de réponse sont utilisés dans les sessions de communication SIP pour répondre aux demandes SIP. Par exemple, supposons que Ken envoie la demande INVITE à Pilar Ackerman (en d’autres points, supposons que Ken Myer appelle Pilar Ackerman). Si Pilar répond, son téléphone envoie le code de réponse 200 (OK), en indiquant que le téléphone de Ken indique que Pilar a répondu. Le rapport des principales défaillances inclut uniquement les codes de réponse qui ont été envoyés en réponse à un échec de l’appel ; Lync Server n’effectue pas le suivi de tous les codes de réponse émis au cours d’un appel.

Les informations sont signalées pour le nombre total de sessions où une défaillance s’est produite, ainsi que pour le nombre total d’utilisateurs affectés par la panne.

<div>

## <a name="accessing-the-top-failures-report"></a>Accès au rapport des principales défaillances

Le rapport des principales défaillances est accessible à partir de la page d’accueil Rapports de surveillance. Si vous cliquez sur la mesure sessions signalées, vous accédez au [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Optimisation de l’utilisation du rapport des principales défaillances

Le rapport des principales défaillances est particulier : il vous permet de filtrer jusqu’à 5 ID de diagnostic à la fois. En règle générale, vous ne pouvez filtrer qu’un élément (par exemple, une adresse SIP d’utilisateur) à la fois. Pour filtrer plusieurs ID de diagnostic, il vous suffit d’entrer chaque ID dans la zone ID de diagnostic, en séparant les ID par des virgules. Si vous le souhaitez, vous pouvez laisser un espace vide après chaque virgule. Par exemple :

1011, 2412, 1033, 52116, 1008

Procédez ainsi pour afficher uniquement les appels défaillants qui correspondent à l’un de ces cinq ID de diagnostic.

Si vous pointez le curseur de la souris sur un code de réponse, vous voyez s’afficher une info-bulle qui vous indique la signification de ce code de réponse. Par exemple, si vous pointez sur le code de réponse 486, vous voyez s’afficher le message suivant :

Occupé ici.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données retournées sur la base d’éléments tels que le type d’activité (session d’égal à égal ou session de conférence) ou le code de réponse SIP qui accompagnait la session en échec. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport des principales défaillances.

### <a name="top-failures-report-filters"></a>Filtres du rapport des principales défaillances

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
<p>Les semaines commencent le dimanche et se terminent le samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type d’activité</strong></p></td>
<td><p>Type d’activité. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Pair à pair</p></li>
<li><p>Salle</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalités</strong></p></td>
<td><p>À ce stade, la seule option disponible est <strong>[Tous]</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge. Vous pouvez sélectionner un pool donné ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement pour vous sur la base des enregistrements de la base de données.</p></td>
</tr>
<tr class="even">
<td><p><strong>Catégorie</strong></p></td>
<td><p>Type de défaillance rencontrée. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Échecs attendus et inattendus</p></li>
<li><p>Échec inattendu</p></li>
</ul>
<p>Un &quot;échec&quot; attendu est un échec qui est attendu. Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue. Un &quot;échec&quot; inattendu est un échec qui se produit dans le cas d’un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Code de réponse </strong>.</p></td>
<td><p>Code de réponse SIP envoyé lors de l’échec de la conférence. Entrez le code de réponse entier. Par exemple :</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport des principales défaillances.

### <a name="top-failures-report-metrics"></a>Mesures du rapport des principales défaillances

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
<td><p><strong>Rank</strong></p></td>
<td><p>Oui</p></td>
<td><p>Classement relatif sur la base du nombre de sessions signalées.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions signalées</strong></p></td>
<td><p>Oui</p></td>
<td><p>Nombre total de sessions en échec sur la base de l’ID de diagnostic et du code de réponse SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utilisateurs affectés</strong></p></td>
<td><p>Oui</p></td>
<td><p>Nombre total d’utilisateurs affectés par l’échec de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Informations sur l’échec</strong></p></td>
<td><p>Non</p></td>
<td><p>Informations détaillées sur l’échec, notamment ID de diagnostic, code de réponse SIP et description de la cause de l’échec de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tendance dans le passé</strong></p></td>
<td><p>Non</p></td>
<td><p>Propose un graphique des échecs de session dans le temps.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

