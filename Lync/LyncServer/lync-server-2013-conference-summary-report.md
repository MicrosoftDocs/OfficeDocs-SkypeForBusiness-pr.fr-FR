---
title: 'Lync Server 2013 : Rapport de synthèse de conférence'
TOCTitle: Rapport de synthèse de conférence
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558656(v=OCS.15)
ms:contentKeyID: 49297410
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de synthèse de conférence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport de synthèse de conférence fournit une vue d’ensemble de vos sessions de conférence en ligne. Une conférence implique généralement plus de 2 utilisateurs et exige l’utilisation des services de conférence Microsoft Lync Server 2013. Par comparaison, une session P2P n’implique en général que 2 utilisateurs et ne nécessite pas l’utilisation des services de conférence Lync Server. Les activités P2P sont indiquées dans le [Rapport de synthèse des activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

Le rapport de synthèse de conférence affiche non seulement le nombre de conférences qui se sont tenues pendant une période donnée (par heure, par jour, par semaine et par mois), mais aussi le nombre total de personnes qui ont participé à ces conférences et le nombre total des organisateurs de conférence uniques.

Un organisateur « unique » est une personne qui planifie au moins une conférence. Par exemple, si Pilar Ackerman planifie une conférence, elle compte comme un organisateur unique. Si Ken Myer planifie 148 conférences, il compte aussi comme un organisateur unique. Le tableau ci-dessous répertorie 8 conférences planifiées, mais avec seulement trois organisateurs uniques (Ken Myer, Pilar Ackerman et David Ahs).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organisateur de la conférence</th>
<th>Date de la conférence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Le rapport de synthèse de conférence indique également le nombre de conférences incluant l’audio et/ou la vidéo.

## Accès au rapport de synthèse de conférence

Le rapport de synthèse de conférence est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez accéder au rapport des activités de conférence en cliquant sur l’une ou l’autre des mesures suivantes :

  - Nombre total de conférences

  - Nombre total de participants

## Exploiter au mieux le rapport de synthèse de conférence

Les valeurs totales pour la plupart des mesures utilisées sur le rapport de synthèse de conférence se trouvent dans la partie inférieure du rapport. Faites défiler le rapport vers le bas pour voir notamment le nombre total de conférences qui se sont tenues au cours de la période spécifiée et le nombre total de personnes qui ont participé à ces conférences. La mesure Nombre total d’organisateurs de conférence uniques, en bas du rapport, ne présente pas de total. En voici l’une des raisons : supposons que vous examiniez les données sur une période d’un mois. Le premier jour, vous avez eu 34 organisateurs de conférence uniques ; le deuxième, 27. Cela signifie-t-il que vous avez eu 61 organisateurs de conférence uniques pour ces deux journées ? Pas nécessairement. Après tout, les 27 personnes qui ont organisé des conférences le deuxième jour faisaient peut-être partie des 34 personnes ayant organisé des conférences le premier jour. Par exemple, dans ce rapport simple, vous pouvez constater que Ken Myer et Pilar Ackerman ont tous les deux planifié des conférences le 7/7/2012 et le 7/2/2012 :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organisateur de la conférence</th>
<th>Date de la conférence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Pour vous faire une meilleure idée du nombre total d’utilisateurs uniques qui ont organisé des conférences, modifiez votre intervalle de temps. Par exemple, au lieu d’examiner les données par mois, examinez-les par jour.

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le Rapport de synthèse de conférence vous permet de choisir le type de groupement des données. Dans le cas présent, les conférences sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de conférence.

### Filtres du rapport de synthèse de conférence

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
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de départ de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours compris entre le 8/7/2012 à minuit et le 9/7/2012 à minuit (soit un total de 31 jours de données).</p></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau ci-dessous contient les informations fournies par le rapport de synthèse de conférence.

### Mesures du rapport de synthèse de conférence

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
<td><p><strong>Nombre total de conférences</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences (de quelque type que ce soit) qui se sont tenues. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de participants</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de personnes ayant participé aux conférences. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre moyen de participants par conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre moyen de personnes ayant assisté à une conférence donnée. Valeur obtenue en divisant le nombre total de conférences par le nombre total de participants.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de conférences A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences ayant fait usage de son ou de vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de minutes par conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de minutes consacrées à la conférence audio/vidéo.</p>
<p>La mesure du nombre total de minutes de conférence audio/vidéo récapitule tous les types de conférence audio/vidéo, dont : conférences audio/vidéo, conférences avec messagerie instantanée, conférences avec partage d’application, conférences avec communication de données et conférences RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de minutes par participant à la conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de minutes consacrées par les participants à la conférence audio/vidéo. Supposons par exemple, qu’un utilisateur passe 5 minutes dans une conférence audio/vidéo et qu’un deuxième utilisateur y passe 3 minutes, nous obtenons un total de 8 minutes de participant.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre moyen de minutes par conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de minutes moyen par conférence audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total d’organisateurs uniques de conférences</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs ayant organisé au moins une conférence. Les utilisateurs ayant organisé plusieurs conférences sont comptabilisés comme des organisateurs uniques, à l’instar de ceux qui n’en ont organisées qu’une seule.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de messages de conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de messages instantanés envoyés au cours des conférences.</p></td>
</tr>
</tbody>
</table>

