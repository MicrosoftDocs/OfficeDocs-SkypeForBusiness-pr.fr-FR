---
title: 'Lync Server 2013 : Rapport d’enregistrement de l’utilisateur'
TOCTitle: Rapport d’enregistrement de l’utilisateur
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558614(v=OCS.15)
ms:contentKeyID: 49296353
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport d’enregistrement de l’utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport d’enregistrement de l’utilisateur offre une vue d’ensemble des ouvertures de session d’utilisateurs, en particulier des informations sur le nombre d’utilisateurs qui ont ouvert une session sur Microsoft Lync Server 2013 pendant une période donnée (heure, jour, semaine ou mois). N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session. Il ne vous apprend pas *qui* a ouvert une session. Les rapports de surveillance n’indiquent pas quels utilisateurs spécifiques utilisent Lync Server 2013 (et lesquels ne l’utilisent pas). Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.

Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes. Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes. Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise). Les ouvertures de session externes représentent les utilisateurs qui ont ouvert une session à l’extérieur du pare-feu via un serveur Edge (par exemple, un utilisateur qui a ouvert une session depuis un café Internet est considéré comme une ouverture de session externe). Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.

En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs *actifs* qui étaient présents pendant une période donnée. Un utilisateur actif est un utilisateur qui a participé à une session de messagerie instantanée, qui a assisté à une réunion Lync, qui a effectué ou reçu un appel téléphonique ou qui a utilisé Lync Server pendant cette période. Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.

## Accès au rapport d’enregistrement de l’utilisateur

Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.

## Utilisation optimale du rapport d’enregistrement de l’utilisateur

Après avoir déployé Lync Server, une des questions qui revient le plus souvent est la suivante : comment savoir si mes utilisateurs utilisent réellement cette nouvelle technologie ? Même s’il est quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question. Pour savoir si vos utilisateurs utilisent ou non Lync Server, vous devez effectuer deux opérations. Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur. Cette valeur indique le nombre d’individus qui ont ouvert une session sur Lync Server.

Par comparaison, la mesure Nombre total d’ouvertures de session indique combien de fois des utilisateurs ont ouvert une session sur Lync Server. Par exemple, supposons que Ken Myer a ouvert une session sur Lync Server cinq fois dans une seule journée. Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session. De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements. Par exemple, un utilisateur peut ouvrir une session sur son ordinateur de bureau, sur son ordinateur portable et il est possible que son téléphone IP ouvre automatiquement une session sur Lync Server. Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.

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
<td><p>07/07/2012 8:46 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>07/07/2012 9:17 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>07/07/2012 9:22 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>07/07/2012 9:31 AM</p></td>
</tr>
</tbody>
</table>


Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Cela illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.

En plus de connaître le nombre d’utilisateurs uniques par ouverture de session, vous devez savoir combien d’utilisateurs au total ont été activés pour Lync Server. Cette valeur peut être extraite en ouvrant Lync Server 2013 Management Shell et en exécutant la commande Windows PowerShell suivante :

    (Get-CsUser).Count

Si la commande précédente renvoie la valeur 1 236 et si la mesure Utilisateurs uniques par ouverture de session renvoie une valeur moyenne de 667, cela suggère qu’un peu plus de la moitié de vos utilisateurs activés pour Lync ouvrent réellement une session sur le système chaque jour (c’est-à-dire 667 divisé par 1 236, ce qui fait approximativement 54 %).

> [!WARNING]  
> Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée. Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système. Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système. Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session. Cela signifierait que presque 1 000 utilisateurs avaient ouvert une session sur Lync Server, ce qui impliquerait que près de 80 % de vos utilisateurs avaient ouvert une session.

Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques. La mesure Utilisateurs actifs uniques vous indique combien d’utilisateurs ont réellement utilisé Lync Server : en effectuant un appel téléphonique, en participant à une réunion Lync ou en prenant part à une session de messagerie instantanée. Ces informations sont utiles, car Microsoft Lync 2013 peut être configuré de manière à démarrer automatiquement à chaque fois qu’un utilisateur lance Windows. Pour cette raison, il est possible qu’un grand nombre d’utilisateurs se connectent automatiquement à Lync lorsqu’ils ouvrent une session sur Windows chaque jour, mais qui n’utilisent jamais réellement Lync Server pendant cette période.

La mesure Utilisateurs actifs uniques fournit également des données utiles dans une organisation où les utilisateurs ne ferment généralement pas leur session Windows à la fin de la journée. Ils se contentent de verrouiller leur ordinateur en laissant Windows et Lync s’exécuter. Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée. La mesure Utilisateurs actifs uniques vous indique toutefois si vos utilisateurs utilisent activement Lync ou un autre client Lync Server.

## Filtres

Les filtres vous permettent de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, grâce au rapport d’enregistrement de l’utilisateur, vous pouvez consulter les données de tous vos pool de serveurs d’inscriptions et serveurs Edge, ou celles d’un pool. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les enregistrements sont groupés par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’enregistrement de l’utilisateur.

### Filtres du rapport d’enregistrement de l’utilisateur

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
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p><ul><li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li><li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li><li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li><li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li></ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de départ de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours compris entre le 8/7/2012 à minuit et le 9/7/2012 à minuit (soit un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez soit sélectionner un pool individuel soit cliquer sur <strong>[Tous]</strong> pour afficher les données pour tous les pools. La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données.</p></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’enregistrement de l’utilisateur.

### Mesures du rapport d’enregistrement de l’utilisateur

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
<p><strong>Tous les jours</strong></p>
<p><strong>Toutes les semaines</strong></p>
<p><strong>Tous les mois</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, vous disposez de l’affichage heure par heure de l’activité d’inscription de l’utilisateur à cette date.</p></td>
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

