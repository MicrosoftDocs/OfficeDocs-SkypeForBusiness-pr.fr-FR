---
title: "Rapport de distrib. des mesures de qualité des médias dans Lync Server 2013"
TOCTitle: Rapport de distribution des mesures de qualité des médias
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205262(v=OCS.15)
ms:contentKeyID: 49298902
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de distribution des mesures de qualité des médias dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport de distribution des mesures de qualité des médias vous permet de consulter un graphique qui affiche les valeurs de distribution pour une mesure de la qualité de l’expérience, comme la gigue ou la perte de paquets. Par exemple, supposons que vos utilisateurs passent un total de 10 appels téléphoniques. Ces 10 appels présentent les délais d’aller-retour suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numéro de l’appel</th>
<th>Délai d’aller-retour (en millisecondes)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>4 550</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


Le délai d’aller-retour moyen est de 500 millisecondes (5 000 divisé par 10). Cinq cents millisecondes est un délai d’aller-retour extrêmement élevé. Par conséquent, vous pouvez penser que vous rencontrez un sérieux problème de surcharge du réseau. (Les délais d’aller-retour élevés sont généralement le résultat de surcharges au niveau du réseau.)

En réalité, 90 % de vos appels présentent d’excellents délais d’aller-retour. C’est à peine si vous avez passé un appel de mauvaise qualité qui a faussé les résultats globaux. Si vous tenez compte du délai d’aller-retour moyen, vous risquez de tirer une fausse conclusion.

Le rapport de distribution des mesures de qualité des médias vous permet de ne pas tirer de conclusions hâtives et erronées : il vous présente une répartition graphique d’une mesure précise (comme le délai d’aller-retour). Ces graphiques permettent de clarifier la situation, à savoir que vous avez passé neuf appels de très bonne qualité et un de mauvaise qualité. Vous souhaitez peut-être examiner plus en détail cet appel-ci. Cependant, le fait que 9 appels sur 10 étaient de bonne qualité semble indiquer qu’il n’existe aucune raison d’apporter des modifications radicales à votre réseau, au moins pas pour l’instant.

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.

### Filtres du rapport de distribution des mesures de qualité des médias

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
<td><p>Date/heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début, comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>03/07/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début, comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>03/07/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minimum sur l’axe x</strong></p></td>
<td><p>Plus petite valeur à afficher sur l’axe X du graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>Maximum sur l’axe x</strong></p></td>
<td><p>Plus grande valeur à afficher sur l’axe X du graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type d’accès</strong></p></td>
<td><p>Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Interne</p></li>
<li><p>Externe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment de passer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>VPN</p></li>
<li><p>Non-VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Câblé</p></li>
<li><p>Sans fil</p></li>
</ul></td>
</tr>
</tbody>
</table>

