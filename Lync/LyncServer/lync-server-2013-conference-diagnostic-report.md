---
title: 'Lync Server 2013 : Rapport de diagnostic de conférence'
TOCTitle: Rapport de diagnostic de conférence
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615042(v=OCS.15)
ms:contentKeyID: 49299203
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de diagnostic de conférence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport de diagnostic de conférence fournit des informations sur la réussite ou l’échec de toutes les sessions de conférence. Notez que Microsoft Lync Server distingue différents types d’échecs :

  - **échec attendu**. Un échec attendu est généralement une erreur au sens technique seulement. Par exemple, supposons que quelqu’un démarre une conférence, mais raccroche avant que des personnes puissent participer. Techniquement, c’est une erreur : la conférence a été lancée, mais n’a pas été achevée. Cependant, il s’agit d’une erreur à laquelle on peut s’attendre : si l’organisateur annule la conférence avant que des personnes puissent participer, on ne s’attend pas à ce que cette conférence soit achevée.

  - **échec inattendu**. Un échec inattendu constitue exactement ce que son nom indique : une erreur à laquelle on ne s’attend pas, compte tenu des circonstances. Par exemple, supposons qu’une conférence ne puisse pas avoir lieu parce que la stratégie de réunion de l’organisateur n’a pas pu être récupérée. Il s’agit d’une erreur inattendue : la stratégie de réunion d’un utilisateur doit toujours pouvoir être récupérée.

Notez que les mesures de Réussite, d’Échec attendu et d’Échec inattendu peuvent ne pas être comptabilisées dans la mesure Nombre total de sessions. Par exemple, vous pouvez voir les valeurs suivantes dans le rapport :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Réussites</th>
<th>Échecs attendus</th>
<th>Échecs inattendus</th>
<th>Nombre total de sessions</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Si vous ajoutez 2024 + 469 + 16, vous obtenez un total de 2 509 sessions alors que la colonne Nombre total de sessions indique 2 521 sessions. Les 12 sessions « manquantes » sont celles que le système n’a pas pu catégoriser comme réussies ou non. C’est parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic inconnu du serveur de suivi. Dans ce cas, les appels effectués à l’aide de ce produit et reportant ce code de diagnostic ne peuvent pas toujours être catégorisés en tant que réussite, échec attendu ou échec inattendu.

## Accès au rapport de diagnostic de conférence

Le rapport des de diagnostic de conférence est accessible à partir de la page d’accueil des Rapports de suivi. Vous pouvez accéder au [Rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) (contenu éventuellement en anglais) en cliquant sur l’une des mesures suivantes :

  - Volume des échecs inattendus

  - Volume des échecs attendus

## Utilisation optimale du rapport de diagnostic de conférence

Le rapport de diagnostic de conférence inclut une série de graphiques. Chaque colonne de graphique constitue un lien hypertexte. En cliquant sur une colonne, vous atteignez le [Rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) (contenu éventuellement en anglais) pour la période et le type de conférence donnés.

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de diagnostic de conférence vous permet de filtrer les éléments tels que le type de conférence mené (par exemple, une conférence Focus) pour le serveur Edge utilisé dans la conférence. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic de conférence.

### Filtres du rapport de diagnostic de conférence

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
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions de conférence</strong></p></td>
<td><p>Indique le type de session de conférence. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Sessions Focus</p></li>
<li><p>Toutes les sessions MCU</p></li>
<li><p>Conférence par messagerie instantanée</p></li>
<li><p>Partage d’application</p></li>
<li><p>Conférence A/V</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic de conférence pour chaque type de session de conférence.

### Mesures du rapport de diagnostic de conférence

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
<td><p><strong>Nombre de réussites</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences réussies.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage de réussite</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences qui se sont déroulées sans problème majeur. Calculé en divisant le nombre de réussites par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre d’échecs attendus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences pour lesquelles un « échec attendu » s’est produit.</p>
<p>Un échec attendu est un échec auquel il faut s’attendre. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, il faut s’attendre à ce que tout appel émis vers cet utilisateur échoue.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec attendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences qui ont rencontré une erreur attendue. Calculé en divisant le nombre d’échecs attendus par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre d’échecs inattendus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences pour lesquelles un « échec inattendu » s’est produit.</p>
<p>Un échec inattendu est un échec qui se produit alors que le système semble intègre. Par exemple, un appel ne doit pas être coupé si l’appelant est mis en attente. Dans le cas contraire, ce problème est considéré comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec inattendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences qui ont rencontré une erreur inattendue. Calculé en divisant le nombre d’échecs inattendus par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences, incluant les conférences qui ont réussi et celles qui ont échoué (à la fois les échecs attendus et les échecs inattendus), ainsi que les conférences qui n’appartiennent à aucune catégorie.</p></td>
</tr>
</tbody>
</table>

