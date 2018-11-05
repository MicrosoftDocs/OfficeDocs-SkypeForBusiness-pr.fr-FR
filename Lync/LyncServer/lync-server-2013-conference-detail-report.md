---
title: Rapport détaillé de conférence
TOCTitle: Rapport détaillé de conférence
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204728(v=OCS.15)
ms:contentKeyID: 49296439
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport détaillé de conférence

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.

## Accès au rapport détaillé de conférence

Le rapport détaillé de conférence est accessible à partir des rapports suivants :

  - Le [Rapport de contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-call-admission-control-report.md) (en cliquant sur la mesure Détails d’une conférence)

  - Le [Rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md) (en cliquant sur la mesure Conférence)

  - Le [Rapport d’activité de l’utilisateur dans Lync Server 2013](lync-server-2013-user-activity-report.md) (en cliquant sur la mesure URI de la conférence)

Le rapport détaillé de conférence vous permet d’accéder au [Rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md) en cliquant sur la mesure Rapport de diagnostic (détaillé).

## Filtres

Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.

## Mesures

Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.

### Mesures des informations de conférence

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
<td><p><strong>URI de la conférence</strong></p></td>
<td><p></p></td>
<td><p>URI affectée à la conférence. Par exemple :</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Nom de domaine complet du pool</strong></p></td>
<td><p></p></td>
<td><p>Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de début</strong></p></td>
<td><p></p></td>
<td><p>Date et heure auxquelles la conférence a commencé.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisateur</strong></p></td>
<td><p></p></td>
<td><p>Adresse SIP de l’utilisateur qui a organisé la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de fin</strong></p></td>
<td><p></p></td>
<td><p>Date et heure auxquelles la conférence s’est terminée.</p></td>
</tr>
</tbody>
</table>


Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.

### Mesures de participation à la conférence

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
<td><p><strong>Utilisateur</strong></p></td>
<td><p></p></td>
<td><p>Adresse SIP de l’utilisateur qui a participé à la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rôle</strong></p></td>
<td><p></p></td>
<td><p>Rôle (par exemple, présentateur) joué par le participant à la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connectivité</strong></p></td>
<td><p></p></td>
<td><p>Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</p></td>
</tr>
<tr class="even">
<td><p>Heure d’arrivée</p></td>
<td><p></p></td>
<td><p>Date et heure auxquelles le participant a rejoint la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de départ</strong></p></td>
<td><p></p></td>
<td><p>Date et heure auxquelles le participant a quitté la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agent utilisateur</strong></p></td>
<td><p></p></td>
<td><p>Identifiant du logiciel utilisé par le point de terminaison du participant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapports de diagnostic</strong></p></td>
<td><p></p></td>
<td><p>Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</p></td>
</tr>
</tbody>
</table>


Le tableau qui suit répertorie les informations fournies dans la section Modalités de conférence du rapport détaillé de conférence.

### Mesures des modalités de conférence

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
<td><p><strong>Utilisateur</strong></p></td>
<td><p></p></td>
<td><p>Adresse SIP de l’utilisateur qui a participé à la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure d’arrivée</strong></p></td>
<td><p></p></td>
<td><p>Date et heure auxquelles le participant a rejoint la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de départ</strong></p></td>
<td><p></p></td>
<td><p>Date et heure auxquelles un participant a quitté la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI du serveur de conférence</strong></p></td>
<td><p></p></td>
<td><p>URI du serveur de conférence utilisé dans la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapports de diagnostic</strong></p></td>
<td><p></p></td>
<td><p>Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</p></td>
</tr>
</tbody>
</table>

