---
title: 'Lync Server 2013 : rapport détaillé de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51dc2a6834241e355f4a681e4b4d55ef95438fb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Rapport détaillé de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.

<div>

## <a name="accessing-the-conference-detail-report"></a>Accès au rapport détaillé de conférence

Le rapport détaillé de conférence est accessible à partir des rapports suivants :

  - Le [rapport de contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-call-admission-control-report.md) (en cliquant sur la mesure détails d’une conférence)

  - Le [rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md) (en cliquant sur la mesure de conférence)

  - [Rapport d’activité de l’utilisateur dans Lync Server 2013](lync-server-2013-user-activity-report.md) (en cliquant sur la mesure URI de la Conférence)

À partir du rapport détaillé de conférence, vous pouvez accéder au [rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md) en cliquant sur la mesure rapport de diagnostic (détail).

</div>

<div>

## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.

</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.

### <a name="conference-information-metrics"></a>Mesures des informations de conférence

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
<td></td>
<td><p>URI affectée à la conférence. Par exemple :</p>
<p>SIP : kmyer@litwareinc. com ; gruu ; opaque = app : conf : Focus : ID : drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Nom de domaine complet du pool</strong></p></td>
<td></td>
<td><p>Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de début</strong></p></td>
<td></td>
<td><p>Date et heure auxquelles la conférence a commencé.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td></td>
<td><p>Adresse SIP de l’utilisateur qui a organisé la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de fin</strong></p></td>
<td></td>
<td><p>Date et heure auxquelles la conférence s’est terminée.</p></td>
</tr>
</tbody>
</table>


Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.

### <a name="conference-participation-metrics"></a>Mesures de participation à la conférence

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
<td><p><strong>User</strong></p></td>
<td></td>
<td><p>Adresse SIP de l’utilisateur qui a participé à la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td></td>
<td><p>Rôle (par exemple, présentateur) joué par le participant à la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connectivité</strong></p></td>
<td></td>
<td><p>Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</p></td>
</tr>
<tr class="even">
<td><p>Heure d’arrivée</p></td>
<td></td>
<td><p>Date et heure auxquelles le participant a rejoint la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de départ</strong></p></td>
<td></td>
<td><p>Date et heure auxquelles le participant a quitté la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agent utilisateur</strong></p></td>
<td></td>
<td><p>Identifiant du logiciel utilisé par le point de terminaison du participant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapports de diagnostic</strong></p></td>
<td></td>
<td><p>Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant répertorie les informations fournies dans la section modalités de conférence du rapport détaillé de conférence.

### <a name="conference-modalities-metrics"></a>Mesures des modalités de conférence

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
<td><p><strong>User</strong></p></td>
<td></td>
<td><p>Adresse SIP de l’utilisateur qui a participé à la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure d’arrivée</strong></p></td>
<td></td>
<td><p>Date et heure auxquelles le participant a rejoint la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de départ</strong></p></td>
<td></td>
<td><p>Date et heure auxquelles un participant a quitté la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI du serveur de conférence</strong></p></td>
<td></td>
<td><p>URI du serveur de conférence utilisé dans la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapports de diagnostic</strong></p></td>
<td></td>
<td><p>Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

