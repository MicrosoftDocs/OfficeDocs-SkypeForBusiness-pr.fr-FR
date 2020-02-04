---
title: 'Lync Server 2013 : rapport sur la liste des appels de groupe de réponse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Rapport de liste des appels de Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

L’application Response Group permet à Microsoft Lync Server 2013 de répondre aux appels téléphoniques et de les acheminer en fonction du numéro composé et, éventuellement, des réponses de l’appelant à une série de questions. En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents. Par exemple, si une personne appelle le numéro de téléphone de votre support technique, Lync Server 2013 peut automatiquement diriger l’appel vers le premier agent de support technique disponible. Par ailleurs, Lync Server peut poser une série de questions (en appuyant sur 1 si vous rencontrez des problèmes de matériel. Appuyez sur 2 pour des problèmes logiciels. Tapez 3 Si vous rencontrez des problèmes de réseau. puis Routez l’appel vers l’agent de support technique le plus approprié en fonction de la réponse à ces questions.

Le Rapport des listes d’appels Response Group représente une collection d’appels effectués pendant une période spécifiée et pour un type d’appel spécifié. Le Rapport d’utilisation de Response Group (qui doit être ouvert au préalable pour que vous puissiez ouvrir le Rapport des listes d’appels Response Group) reconnaît les types d’appels suivants :

  - **Appels reçus**. Nombre total d’appels reçus par toutes les instances de l’application Response Group.

  - **Appels réussis**. Nombre total d’appels auxquels l’application Response Group a répondu.

  - **Appels offerts**. Nombre total d’appels transférés à un agent Response Group.

  - **Appels ayant obtenu une réponse**. Nombre total d’appels auxquels un agent Response Group a effectivement répondu.

  - Pourcentage d’appels abandonnés. Pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez reçu dix appels et sept avec réponse, vous soustrayez sept de dix et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par dix, ce qui vous fournit un pourcentage d’appels abandonnés de 30 %.

  - **Appels transférés**. Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de débordement de la file d’attente.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Accès au Rapport des listes d’appels Response Group

Pour accéder au rapport de la liste des appels de Response Group, vous pouvez uniquement cliquer sur l’une des mesures suivantes figurant dans le [rapport utilisation du groupe de réponse dans Lync Server 2013](lync-server-2013-response-group-usage-report.md):

  - Appels reçus

  - Appels réussis

  - Appels offerts

  - Appels ayant obtenu une réponse

  - Appels transférés

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Utilisation optimale du Rapport des listes d’appels Response Group

Le Rapport des listes d’appels Response Group vous permet de limiter les données affichées aux appels impliquant un flux de travail Response Group particulier. Pour cela, vous devez entrer l’URI de flux de travail (l’adresse SIP du flux de travail) dans la zone URI du flux de travail. Avant cela, vous devez cependant être en mesure de voir cette zone URI du flux de travail. Pour afficher les options de filtrage du Rapport des listes d’appels Response Group, cliquez sur le bouton Afficher / Masquer les paramètres dans la partie supérieure gauche de la fenêtre de rapport.

Notez que le Rapport des listes d’appels Response Group n’affiche pas d’informations relatives au code de réponse ou à l’ID de diagnostic si vous maintenez le pointeur de la souris sur l’une de ces mesures. Si vous avez besoin d’informations supplémentaires, vous pouvez noter le code de réponse et/ou l’ID de diagnostic, puis rechercher ces valeurs dans le rapport sur les [principaux échecs de Lync Server 2013](lync-server-2013-top-failures-report.md).

Si vous souhaitez obtenir la réponse à une question telle que « Quel est le flux de travail ayant reçu le plus d’appels ? », vous pouvez procéder comme suit :

1.  Dans le Rapport d’utilisation de Response Group, définissez la période souhaitée, puis cliquez sur la mesure Appels reçus pour ouvrir le Rapport des listes d’appels Response Group.

2.  Exportez les données affichées dans le Rapport des listes d’appels Response Group. Par exemple, vous pourriez exporter les données au format Microsoft Excel, puis utiliser Excel pour convertir ces données en un fichier de valeurs séparées par des virgules.

3.  Exécutez vos analyses à l’aide de Windows PowerShell.

Par exemple, si vous avez enregistré les données dans un fichier nommé C :\\Data\\Response\_Group\_\_\_. csv, vous pouvez utiliser la commande suivante pour renvoyer le nombre total d’appels reçus pour chaque flux de travail répertorié dans le rapport :

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

Des informations analogues aux suivantes seront renvoyées :

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de liste des appels Response Group.

### <a name="response-group-call-list-report-filters"></a>Filtres de rapport de liste des appels Response Group

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
<td><p><strong>URI du flux de travail</strong></p></td>
<td><p>Vous permet de limiter les données renvoyées au flux de travail Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels</strong></p></td>
<td><p>Vous pouvez sélectionner l’un des types d’appels suivants :</p>
<ul>
<li><p>Appels reçus</p></li>
<li><p>Appels réussis</p></li>
<li><p>Appels offerts</p></li>
<li><p>Appels ayant obtenu une réponse</p></li>
<li><p>Appels transférés</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de liste des appels Response Group pour chaque appel reçu par l’application Response Group.

### <a name="response-group-call-list-report-metrics"></a>Mesures du rapport de liste des appels Response Group

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
<td><p><strong>Appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flux de travail</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP du flux de travail Response Group.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de début</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure de début de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure de fin de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Code de réponse</strong></p></td>
<td><p>Non</p></td>
<td><p>Code de réponse SIP envoyé lors de l’échec de session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

