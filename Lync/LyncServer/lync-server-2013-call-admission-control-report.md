---
title: 'Lync Server 2013 : rapport de contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c1ff2b667c0529dfb7a90291dba7ad5ab154a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517961"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a>Rapport de contrôle d’admission des appels dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-29_

Le rapport de contrôle d’admission des appels fournit des informations sur les sessions d’égal à égal et de conférence menées sous restrictions définies en place par le contrôle d’admission des appels. Le contrôle d’admission des appels, introduit dans Microsoft Lync Server 2010, permet aux administrateurs d’autoriser (ou non) les sessions de communication en fonction des contraintes de bande passante. Par exemple, les administrateurs peuvent créer des stratégies qui imposent une limite sur la quantité de bande passante disponible pour les appels vocaux et vidéo. Si cette limite de bande passante a été atteinte, aucun nouvel appel vocal ou vidéo ne peut être passé tant que l’un des appels en cours n’a pas terminé et libéré les ressources réseau requises.

<div>

## <a name="accessing-the-call-admission-control-report"></a>Accès au rapport de contrôle d’admission des appels

Le rapport de contrôle d’admission des appels est accessible à partir de la page d’accueil des rapports de surveillance. À partir du rapport de contrôle d’admission des appels, vous pouvez accéder à l’un des rapports suivants :

  - Rapport détaillé de conférence : pour accéder à ce rapport, cliquez sur la mesure détails à partir d’une session de conférence.

  - Rapport détaillé de session P2P : pour accéder à ce rapport, cliquez sur la mesure détails d’une session d’égal à égal.

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Utilisation optimale du rapport de contrôle d’admission des appels

Pour obtenir la liste des appels ayant échoué en raison d’une bande passante insuffisante, sélectionnez appels rejetés en raison du contrôle d’admission des appels dans la liste déroulante catégorie d’appel. La plupart des appels renvoyés auront probablement l’ID de diagnostic 5 :

Bande passante insuffisante pour établir une session. Tentez un nouveau routage PSTN.

Cela indique que les limitations du contrôle d’admission des appels empêchaient l’appel d’être effectué sur le réseau VoIP.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de contrôle d’admission des appels vous permet de filtrer les appels par l’utilisateur qui a initié l’appel ou par l’utilisateur qui a été appelé. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.

Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de contrôle d’admission des appels.

### <a name="call-admission-control-report-filters"></a>Filtres du rapport de contrôle d’admission des appels

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
<td><p>Date/heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</p>
<p>17/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/17/12012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/13/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>17/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/17/12012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/13/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</p></td>
</tr>
<tr class="even">
<td><p><strong>Type d’activité</strong></p></td>
<td><p>Type d’activité. Sélectionnez l’une des activités suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Égal à égal</p></li>
<li><p>Conférence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Catégorie d’appel</strong></p></td>
<td><p>Indique la raison pour laquelle le contrôle d’admission des appels a été utilisé pour l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Appel rejeté en raison du contrôle d’admission des appels</p></li>
<li><p>Appels réacheminés via PSTN en raison du contrôle d’admission des appels</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions d’égal à égal

Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions P2P (c’est-à-dire, les sessions qui n’impliquent que deux participants).

### <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions d’égal à égal

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
<td><p><strong>Detail</strong></p></td>
<td><p>Non</p></td>
<td><p>Lorsque vous cliquez sur cet élément, le rapport vous montre un rapport détaillé de session P2P pour la session spécifiée.</p></td>
</tr>
<tr class="even">
<td><p><strong>De l’utilisateur</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de l’utilisateur ayant initié la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À l’utilisateur</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de l’utilisateur qui a été invité à rejoindre la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalités</strong></p></td>
<td><p>Oui</p></td>
<td><p>Modalités de communication (audio et vidéo, par exemple) qui ont été utilisées pendant la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure d’invitation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure auxquelles l’invitation initiale à la session a été envoyée à l’utilisateur de.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de réponse</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure auxquelles l’acceptation de l’invitation a été reçue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure de fin de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Oui</p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour les sessions de conférence (c’est-à-dire, les sessions qui impliquent trois participants ou plus).

### <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

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
<td><p>Oui</p></td>
<td><p>Identificateur unique de la Conférence. Lorsque vous cliquez sur cet élément, le rapport affiche les participants individuels de la Conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de l’utilisateur qui a organisé la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Oui</p></td>
<td><p>Serveur Edge utilisé dans la Conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de début</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure auxquelles la conférence a commencé.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure de fin de la conférence.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>Mesures pour les participants à la Conférence individuelle

Le tableau suivant répertorie les informations fournies dans le rapport de contrôle d’admission des appels pour chaque participant d’une conférence.

### <a name="metrics-for-individual-conference-participants"></a>Mesures pour les participants à la Conférence individuelle

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
<td><p><strong>Role</strong></p></td>
<td><p>Non</p></td>
<td><p>Rôle (par exemple, présentateur) joué par le participant à la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Participant</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP du participant à la Conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connectivité</strong></p></td>
<td><p>Non</p></td>
<td><p>Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalités</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de conférence (par exemple, conférence A/V).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure d’arrivée</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles le participant a rejoint la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de départ</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles le participant a quitté la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

