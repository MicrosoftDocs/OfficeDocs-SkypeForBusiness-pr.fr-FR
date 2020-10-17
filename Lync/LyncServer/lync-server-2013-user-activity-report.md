---
title: 'Lync Server 2013 : rapport d’activité de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36001aaf38dc39d0bb4eb7524e41c616b0a1c160
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530231"
---
# <a name="user-activity-report-in-lync-server-2013"></a>Rapport d’activité de l’utilisateur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-02-27_

Le rapport d’activité de l’utilisateur fournit une liste détaillée des sessions d’égal à égal et des sessions de conférence exécutées par vos utilisateurs au cours d’une période donnée. Contrairement à la plupart des rapports de surveillance, le rapport d’activité de l’utilisateur lie chaque appel à des utilisateurs individuels. Par exemple, les sessions d’égal à égal spécifient l’URI SIP de la personne à l’origine de l’appel (utilisateur d’origine) et celle de la personne qui a été appelée (utilisateur de destination). Si vous développez les informations sur une conférence, vous obtiendrez la liste de tous les participants à la conférence, ainsi que le rôle qu’ils ont eu à cette occasion.

Le rapport d’activité de l’utilisateur est parfois appelé « rapport de support technique ». En effet, ce rapport est souvent utilisé par les équipes de support technique pour récupérer les informations de session d’un utilisateur spécifique. Vous pouvez filtrer les appels à destination ou en provenance d’un utilisateur individuel en tapant simplement son URI SIP dans la zone Préfixe d’URI d’utilisateur.

Dans ce cas, le rapport d’activité de l’utilisateur renverra des informations sur tous les utilisateurs dont l’URI SIP commence par la chaîne spécifiée. Par exemple, si vous tapez **Ken** dans la zone URI, le rapport d’activité de l’utilisateur localisera **Ken**. Myer@litwareinc.com. Toutefois, il localise également les utilisateurs suivants :

  - **ken**azi@litwareinc.com

  - **ken**Burg@litwareinc.com

  - **Ken**. Sanchez@litwareinc.com

  - **Ken**Nedy@litwareinc.com

Pour vous assurer que les informations uniquement pour Ken Myer sont renvoyées, tapez son URI complet (Ken.Myer@litwareinc.com) dans la zone de recherche ou au moins un type d’URI de Ken afin de le différencier des autres utilisateurs de votre organisation. Par exemple :

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>Pour accéder au rapport d’activité de l’utilisateur

Le rapport d’activité de l’utilisateur est accessible via la page d’accueil des rapports de surveillance. Vous pouvez également accéder au rapport d’activité de l’utilisateur en cliquant sur la mesure URI de l’utilisateur sur le [rapport d’inventaire de téléphonie IP dans Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md). Si vous cliquez sur URI de la conférence (pour une conférence) dans le rapport d’activité de l’utilisateur, vous accèderez au rapport détaillé de conférence. De même, le fait de cliquer sur la mesure détail pour un appel P2P vous permet d’accéder au [rapport détaillé de session P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>Utilisation optimale du rapport d’activité de l’utilisateur

Bien que le rapport d’activité de l’utilisateur contienne des informations utiles, il peut parfois être difficile de les localiser. Par exemple, toutes les activités de l’utilisateur qui ont lieu dans votre organisation pendant une période spécifiée sont incluses dans le rapport d’activité de l’utilisateur ; Cela signifie que, lorsqu’il est inclus dans le rapport, des informations sur les utilisateurs qui ont réellement utilisé Microsoft Lync Server 2013.

<div>


> [!WARNING]  
> Techniquement, il est possible que certaines activités utilisateur ne soient pas enregistrées : tandis que Lync Server s’efforce de conserver des informations sur tous les appels téléphoniques, il est possible qu’un appel ait été effectué sans que les informations relatives à cet appel soient écrites dans la base de données. Lync Server est conçu pour donner un aperçu extrêmement précis mais pas nécessairement parfait de la façon dont Lync Server 2013 est utilisé. (Le fait qu’il n’existe aucune garantie que 100% de tous les appels sont enregistrés explique pourquoi la surveillance Lync Server ne doit pas être utilisée comme système de facturation.)<BR>En deuxième lieu, un rapport de surveillance ne peut afficher que 1 000 enregistrements, tout au plus. Ainsi, selon le volume d’activité de vos utilisateurs et la période considérée, votre requête risque de ne pas retourner toutes les données effectivement stockées dans la base de données.



</div>

  - Quels sont les utilisateurs qui ont utilisé le système au cours de cette période ?

  - Parmi les différents utilisateurs, quels sont ceux qui se sont montrés les plus actifs au cours de cette période ?

  - Les utilisateurs qui passent le plus grand nombre d’appels sont-ils aussi ceux qui participent le plus aux sessions de messagerie instantanée ?

Si vous avez besoin de répondre à ce type de question, vous pouvez exporter les données récupérées par les rapports de surveillance dans une feuille de calcul Excel. Vous pouvez alors vous servir de cette feuille de calcul et/ou d’un fichier de valeurs séparées par des virgules (CSV) pour analyser les données de façon plus poussée que dans le rapport d’activité de l’utilisateur. Par exemple, supposons que vous avez exporté les données du rapport dans Excel, puis dans un fichier CSV. À ce stade, vous pouvez importer les données à partir du. CSV vers Windows PowerShell à l’aide d’une commande semblable à celle-ci :

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Une fois que les données ont été importées, vous pouvez utiliser des commandes Windows PowerShell simples pour répondre à vos questions. Par exemple, cette commande retourne une liste d’utilisateurs uniques qui ont fait office d’expéditeur (« From user ») dans au moins une session :

    $x | Group-Object "From user" | Select Name | Sort-Object Name

En voici le résultat :

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

Cette commande dresse la liste des utilisateurs individuels (en fonction du nombre total de sessions auxquelles ils ont participé) :

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Les données retournées se présentent ainsi :

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

Cette commande limite les sessions recensées dans le rapport à celles qui incluaient la modalité audio :

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Si vous placez le curseur de la souris sur un ID de diagnostic figurant dans le rapport, une description de cet ID apparaît dans une info-bulle.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données retournées sur la base d’éléments tels que le type d’activité (à savoir, sessions d’égal à égal ou sessions de conférence) ou l’adresse SIP de l’utilisateur (vous permettant d’afficher les activités d’un utilisateur). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’activité de l’utilisateur.

### <a name="user-activity-report-filters"></a>Filtres du rapport d’activité de l’utilisateur

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
<p>Les semaines commencent le dimanche et se terminent le samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type d’activité</strong></p></td>
<td><p>Type d’activité. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Pair à pair</p></li>
<li><p>Conférence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalités</strong></p></td>
<td><p>La modalité disponible varie en fonction du type d’activité Select. Si le type d’activité est égal à égal, vous pouvez sélectionner messagerie instantanée ; Transfert de fichiers ; Partage d’application ; Vocale ou la vidéo comme modalité.</p>
<p>Si le type d’activité est Conférence, vous pouvez sélectionner conférence téléphonique de messagerie instantanée ; Conférence Web ; Partage d’application ; Conférence vocale/vidéo ; ou une conférence téléphonique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Catégorie de session</strong></p></td>
<td><p>Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Opération réussie</p></li>
<li><p>Échec attendu</p></li>
<li><p>Échec inattendu</p></li>
</ul>
<p>Un &quot; échec attendu &quot; est un échec qui est susceptible de se produire ; par exemple, si un utilisateur a défini son statut sur ne pas déranger, vous devez attendre l’échec de tout appel à cet utilisateur. Un &quot; échec inattendu &quot; est un échec qui se produit dans le cas d’un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Préfixe d’URI de l’utilisateur</strong></p></td>
<td><p>Adresse SIP pour l’utilisateur. Pour afficher exclusivement les enregistrements de l’utilisateur Ken Myer, vous devez entrer l’adresse SIP de Ken Myer. Par exemple :</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour sessions d’égal à égal

Le tableau suivant liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions d’égal à égal (à savoir les sessions impliquant deux participants uniquement).

### <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour sessions d’égal à égal

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
<td><p>Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de session d’égal à égal pour la session sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>De l’utilisateur</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de l’utilisateur qui a initié la session d’égal à égal.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À l’utilisateur</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de l’utilisateur qui s’est joint à la session d’égal à égal.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalités</strong></p></td>
<td><p>Oui</p></td>
<td><p>Type de communication utilisé dans la session. Par exemple, messagerie instantanée, audio ou transfert de fichier.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure d’invitation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure d’envoi de l’invitation initiale à se joindre à la session d’égal à égal.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de réponse</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure auxquelles l' &quot; &quot; utilisateur a accepté l’invitation à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure de fin de la session d’égal à égal.</p></td>
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

Le tableau suivant liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions d’égal à égal (à savoir les sessions impliquant deux participants uniquement).

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
<td><p>Identifiant de conférence unique. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de conférence pour la session sélectionnée. Lorsque vous développez cet élément, le rapport vous montre les informations sur les participants à la conférence. Pour plus d’informations, consultez la &quot; section mesures pour les participants à la Conférence &quot; plus loin dans cette rubrique.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de l’utilisateur qui a organisé la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Oui</p></td>
<td><p>Nom du serveur Edge (le cas échéant) utilisé dans la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de début</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure de début de la conférence.</p></td>
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

## <a name="metrics-for-conference-participants"></a>Mesures pour les participants de la conférence

Le tableau suivant liste les informations fournies dans le Rapport d’activité de l’utilisateur sur chaque participant d’une conférence.

### <a name="metrics-for-conference-participants"></a>Mesures pour les participants de la conférence

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
<td><p>Rôle de conférence (par exemple, Présentateur) pour l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>Participant</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connectivité</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de connexion réseau. Par exemple &quot; from Internal &quot; pour la connexion interne ou &quot; PSTN &quot; pour les utilisateurs d’appels entrants.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure d’arrivée</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure à laquelle l’utilisateur a rejoint la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de départ</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure à laquelle l’utilisateur a quitté la conférence.</p></td>
</tr>
<tr class="even">
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

