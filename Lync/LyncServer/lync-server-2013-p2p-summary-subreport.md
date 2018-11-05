---
title: Sous-rapport résumé des sessions d’égal à égal
TOCTitle: Sous-rapport résumé des sessions d’égal à égal
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205416(v=OCS.15)
ms:contentKeyID: 49299436
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sous-rapport résumé des sessions d’égal à égal

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le sous-rapport de résumé P2P offre un aperçu général de vos sessions de communication pair au pair ayant échoué.

## Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de résumé P2P.

### Filtres de sous-rapport de résumé P2P

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
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>07/03/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>07/03/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</p></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le sous-rapport de résumé P2P.

### Mesures de sous-rapport de résumé P2P

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
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’échec</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions d’égal à égal ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions par modalité</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions groupées par modalité (par exemple, messagerie instantanée).</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’échec par modalité</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué groupées par modalité (par exemple, messagerie instantanée).</p></td>
</tr>
</tbody>
</table>

