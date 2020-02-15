---
title: 'Lync Server 2013 : rapport de liste des échecs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9cd8d15e81a54085624fab2dc751759d8196c48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Rapport de liste des échecs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-07-02_

Le Rapport des listes d’échecs fournit des informations sur les participants individuels à une session d’égal à égal ou session de conférence ayant échoué. Ces informations incluent l’URI de l’utilisateur qui a rencontré le problème, ainsi que le code de réponse SIP et l’ID de diagnostic associés à l’échec.

<div>

## <a name="accessing-the-failure-list-report"></a>Accès au Rapport des listes d’échecs

Pour accéder au rapport des listes d’échecs, cliquez sur l’une des mesures suivantes dans le [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Motifs de diagnostic principaux (sessions)

  - Modalités principales (sessions)

  - Pools principaux (sessions)

  - Sources principales (sessions)

  - Composants principaux (sessions)

  - Utilisateurs émetteurs principaux (sessions)

  - Utilisateurs destinataires principaux (sessions)

  - Agents utilisateurs émetteurs principaux (sessions)

À partir du rapport des listes d’échecs, vous pouvez accéder au [rapport détaillé de session P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) en cliquant sur la mesure détails de la session pour une session d’égal à égal. Vous pouvez également accéder au Rapport détaillé de conférence en cliquant sur la mesure Conférence pour une conférence.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Exploitation optimale du Rapport des listes d’échecs

Le Rapport des listes d’échecs vous permet d’afficher une description de chaque code de réponse ou de chaque ID de diagnostic en maintenant simplement la souris au-dessus de la valeur concernée. Par exemple, si vous maintenez la souris au-dessus de l’ID de diagnostic 7025, les informations suivantes s’affichent dans une info-bulle :

Erreur du serveur interne lors de la création du média pour l’utilisateur.

Il est important de noter que le Rapport des listes d’échecs ne fournit pas une méthode simple de récupérer directement une liste de tous les utilisateurs qui ont participé à au moins une session ayant échoué, et qu’il ne permet pas non plus de déterminer les utilisateurs qui sont le plus souvent impliqués dans une session ayant échoué. (Pour une chose, le rapport des listes d’échecs n’a pas de fonctionnalités de filtrage.) Toutefois, si vous exportez les données, puis que vous les convertissez en un fichier de valeurs séparées par des virgules, vous pouvez utiliser Windows PowerShell pour trouver les réponses à des questions comme celles-ci. Par exemple, supposons que vous enregistriez les données dans un fichier. Fichier CSV nommé C :\\Data\\Failure\_List. csv. En fonction des données enregistrées dans ce fichier, la commande suivante répertorie tous les utilisateurs qui ont été impliqués dans au moins une session ayant échoué :

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Cette commande retourne une liste semblable à ceci :

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Les deux commandes suivantes retournent le nombre total de sessions ayant échoué dans lesquelles chaque utilisateur a été impliqué :

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Des données semblables à ceci sont alors retournées :

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Filtres

Aucun. Il est impossible de filtrer le Rapport des listes d’échecs.

</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le Rapport des listes d’échecs pour chaque appel ayant échoué.

### <a name="failure-list-report-metrics"></a>Mesures du Rapport des listes d’échecs

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
<td><p><strong>Heure du rapport</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure d’enregistrement du rapport.</p></td>
</tr>
<tr class="even">
<td><p><strong>Demande</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de demande SIP ayant échoué. Par exemple, INVITE ou BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Code de réponse</strong></p></td>
<td><p>Non</p></td>
<td><p>Code de réponse SIP envoyé lors de l’échec de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Coût/temps de connexion (ms)</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps (en millisecondes) requis pour que l’utilisateur rejoigne la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>De l’utilisateur</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur qui a initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agent utilisateur d’origine</strong></p></td>
<td><p>Non</p></td>
<td><p>Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>À l’utilisateur</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse IP de l’utilisateur qui était appelé.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

