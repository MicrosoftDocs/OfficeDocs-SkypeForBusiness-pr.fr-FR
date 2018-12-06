---
title: 'Lync Server 2013 : Rapport de diagnostic des activités P2P'
TOCTitle: Rapport de diagnostic des activités P2P
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558602(v=OCS.15)
ms:contentKeyID: 49296069
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de diagnostic des activités P2P dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport de diagnostic des activités P2P fournit des informations sur la réussite ou l’échec des sessions de communication P2P. Notez que Microsoft Lync Server 2013 fait la distinction entre différents types d’échec :

  - **Échec attendu** . Un échec attendu est en général un échec considéré comme strictement technique. Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit absente de son bureau et ne puisse donc répondre à votre appel. Étant donné que l’appel n’a pas été répondu, il est techniquement considéré comme un échec. Par ailleurs, cet échec était attendu : Microsoft Lync Server 2013 ne s’attend pas à ce que vous répondiez au téléphone si vous êtes indisponible. De même, un échec attendu se produira si vous tentez d’envoyer un message instantané à un utilisateur qui est hors ligne ou qui est connecté à un téléphone qui ne prend pas les messages instantanés.

  - **Échec inattendu** . Comme son nom l’indique, une erreur inattendue est une erreur que vous n’attendiez pas selon les circonstances. Par exemple, supposons que vous appeliez une personne et que cette personne ne puisse répondre à votre appel ; lorsque Lync Server 2013 tente de diriger l’appel vers la messagerie vocale, l’appel échoue, car la connectivité vers la messagerie unifiée Exchange a été perdue. Il s’agit d’une erreur inattendue : car vous vous attendiez à ce que les appels soient toujours dirigés vers la messagerie vocale. En règle générale, les échecs inattendus sont de vrais échecs : ce sont des problèmes auxquels il n’est pas possible de remédier en formant les utilisateurs ou à l’aide de mesures similaires.

Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, l’illustration précédente indique les valeurs suivantes :


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


Si vous additionnez 2024 + 469 + 16 vous obtenez un total de 2 509 sessions alors que la colonne du total des sessions indique 2 521 sessions. Les 12 sessions « manquantes » sont des sessions que le système n’est pas parvenu à classer comme des succès ou des échecs. Cela peut arriver lorsqu’un produit tiers introduit un code de diagnostic que Lync Server ne reconnaît pas. Lorsque cela arrive, les appels effectués à l’aide de ce produit et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.

## Accès au rapport de diagnostic des activités P2P

Le rapport de diagnostic des activités P2P est accessible à partir de la page d’accueil des rapports de surveillance. Pour accéder au [Rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md), cliquez sur l’une des mesures suivantes :

  - Volume des échecs inattendus

  - Volume des échecs attendus

## Utilisation optimale du rapport de diagnostic des activités P2P

Il existe plusieurs manières de filtrer le rapport de diagnostic des activités P2P mais, par défaut, les options de filtrage sont masquées. Pour les afficher, cliquez sur le bouton Afficher/Masquer les paramètres dans le coin supérieur droit de la fenêtre des rapports. Les options de filtrage s’affichent alors.

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de diagnostic des activités P2P vous permet de filtrer selon des éléments précis, tels que la modalité de session (à savoir messagerie instantanée, transfert de fichiers ou partage d’application). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.

Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic des activités P2P.

### Filtres du rapport de diagnostic des activités P2P

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
<td><p><strong>Modalité</strong></p></td>
<td><p>Indique le type d’activité de communication qui a eu lieu. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Messagerie instantanée</p></li>
<li><p>Transfert de fichiers</p></li>
<li><p>Partage d’application</p></li>
<li><p>Audio</p></li>
<li><p>Vidéo</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Mesures (par modalité)

Le tableau ci-dessous dresse la liste des informations fournies dans le rapport de diagnostic des activités P2P pour chaque modalité.

### Mesures (par modalité)

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
<td><p>Nombre total des sessions P2P réussies.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage de réussite</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage des sessions P2P qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre d’échecs attendus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions lors desquelles un « échec attendu » s’est produit.</p>
<p>Un échec attendu est un échec auquel il faut s’attendre. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, il faut s’attendre à ce que tout appel émis vers cet utilisateur échoue.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec attendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions P2P lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre d’échecs inattendus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions où un « échec inattendu » s’est produit.</p>
<p>Un échec inattendu est un échec qui se produit alors que le système semble intègre. Par exemple, un appel ne doit pas être coupé si l’appelant est mis en attente. Dans le cas contraire, ce problème est considéré comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec inattendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions P2P lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</p></td>
</tr>
</tbody>
</table>

