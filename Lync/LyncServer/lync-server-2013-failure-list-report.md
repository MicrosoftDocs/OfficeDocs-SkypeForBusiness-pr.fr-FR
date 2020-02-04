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
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Rapport de liste des échecs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-07-02_

Le Rapport des listes d’échecs fournit des informations sur les participants individuels à une session P2P ou session de conférence ayant échoué. Ces informations incluent l’URI de l’utilisateur qui a rencontré le problème, ainsi que le code de réponse SIP et l’ID de diagnostic associés à l’échec.

<div>

## <a name="accessing-the-failure-list-report"></a>Accès au Rapport des listes d’échecs

Le rapport de liste d’échecs est accessible en cliquant sur l’une des mesures suivantes sur le [rapport de distribution des échecs dans Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Motifs de diagnostic principaux (sessions)

  - Modalités principales (sessions)

  - Pools principaux (sessions)

  - Sources principales (sessions)

  - Composants principaux (sessions)

  - Utilisateurs émetteurs principaux (sessions)

  - Utilisateurs destinataires principaux (sessions)

  - Agents utilisateurs émetteurs principaux (sessions)

Dans le rapport de la liste des échecs, vous pouvez accéder au [rapport détaillé de la session d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) en cliquant sur la métrique des détails de session pour une session d’égal à égal. Vous pouvez également accéder au Rapport détaillé de conférence en cliquant sur la mesure Conférence pour une conférence.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Exploitation optimale du Rapport des listes d’échecs

Le Rapport des listes d’échecs vous permet d’afficher une description de chaque code de réponse ou de chaque ID de diagnostic en maintenant simplement la souris au-dessus de la valeur concernée. Par exemple, si vous maintenez la souris au-dessus de l’ID de diagnostic 7025, les informations suivantes s’affichent dans une info-bulle :

Erreur du serveur interne lors de la création du média pour l’utilisateur.

Il est important de noter que le Rapport des listes d’échecs ne fournit pas une méthode simple de récupérer directement une liste de tous les utilisateurs qui ont participé à au moins une session ayant échoué, et qu’il ne permet pas non plus de déterminer les utilisateurs qui sont le plus souvent impliqués dans une session ayant échoué. (Pour une chose, le rapport de la liste des échecs n’a pas de fonctionnalités de filtrage.) Toutefois, si vous exportez les données et que vous les convertissez en fichier de valeurs séparées par des virgules, vous pouvez utiliser Windows PowerShell pour trouver les réponses à des questions comme celles-ci. Par exemple, supposons que vous enregistriez les données dans un fichier. Fichier CSV nommé C :\\Data\\Failure\_List. csv. En fonction des données enregistrées dans ce fichier, la commande suivante répertorie tous les utilisateurs qui ont été impliqués dans au moins une session ayant échoué :

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Cette commande renvoie une liste semblable à ceci :

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Les deux commandes suivantes renvoient le nombre total de sessions ayant échoué dans lesquelles chaque utilisateur a été impliqué :

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Des données semblables à ceci sont renvoyées :

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
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.</p></td>
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

