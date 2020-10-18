---
title: 'Lync Server 2013 : rapport de liste des échecs'
description: 'Lync Server 2013 : rapport de liste des échecs.'
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
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575050"
---
# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="96e51-103">Rapport de liste des échecs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e51-103">Failure List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e51-104">_**Dernière modification de la rubrique :** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="96e51-104">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="96e51-p101">Le Rapport des listes d’échecs fournit des informations sur les participants individuels à une session d’égal à égal ou session de conférence ayant échoué. Ces informations incluent l’URI de l’utilisateur qui a rencontré le problème, ainsi que le code de réponse SIP et l’ID de diagnostic associés à l’échec.</span><span class="sxs-lookup"><span data-stu-id="96e51-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="96e51-107">Accès au Rapport des listes d’échecs</span><span class="sxs-lookup"><span data-stu-id="96e51-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="96e51-108">Pour accéder au rapport des listes d’échecs, cliquez sur l’une des mesures suivantes dans le [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="96e51-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="96e51-109">Motifs de diagnostic principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-109">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="96e51-110">Modalités principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-110">Top modalities (sessions)</span></span>

  - <span data-ttu-id="96e51-111">Pools principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-111">Top pools (sessions)</span></span>

  - <span data-ttu-id="96e51-112">Sources principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-112">Top sources (sessions)</span></span>

  - <span data-ttu-id="96e51-113">Composants principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-113">Top components (sessions)</span></span>

  - <span data-ttu-id="96e51-114">Utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-114">Top from users (sessions)</span></span>

  - <span data-ttu-id="96e51-115">Utilisateurs destinataires principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-115">Top to users (sessions)</span></span>

  - <span data-ttu-id="96e51-116">Agents utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="96e51-116">Top from user agents (sessions)</span></span>

<span data-ttu-id="96e51-117">À partir du rapport des listes d’échecs, vous pouvez accéder au [rapport détaillé de session P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) en cliquant sur la mesure détails de la session pour une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="96e51-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="96e51-118">Vous pouvez également accéder au Rapport détaillé de conférence en cliquant sur la mesure Conférence pour une conférence.</span><span class="sxs-lookup"><span data-stu-id="96e51-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="96e51-119">Exploitation optimale du Rapport des listes d’échecs</span><span class="sxs-lookup"><span data-stu-id="96e51-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="96e51-p103">Le Rapport des listes d’échecs vous permet d’afficher une description de chaque code de réponse ou de chaque ID de diagnostic en maintenant simplement la souris au-dessus de la valeur concernée. Par exemple, si vous maintenez la souris au-dessus de l’ID de diagnostic 7025, les informations suivantes s’affichent dans une info-bulle :</span><span class="sxs-lookup"><span data-stu-id="96e51-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="96e51-122">Erreur du serveur interne lors de la création du média pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="96e51-122">Internal server error creating media for user.</span></span>

<span data-ttu-id="96e51-123">Il est important de noter que le Rapport des listes d’échecs ne fournit pas une méthode simple de récupérer directement une liste de tous les utilisateurs qui ont participé à au moins une session ayant échoué, et qu’il ne permet pas non plus de déterminer les utilisateurs qui sont le plus souvent impliqués dans une session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="96e51-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="96e51-124">(Pour une chose, le rapport des listes d’échecs n’a pas de fonctionnalités de filtrage.) Toutefois, si vous exportez les données, puis que vous les convertissez en un fichier de valeurs séparées par des virgules, vous pouvez utiliser Windows PowerShell pour trouver les réponses à des questions comme celles-ci.</span><span class="sxs-lookup"><span data-stu-id="96e51-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="96e51-125">Par exemple, supposons que vous enregistriez les données dans un fichier. Fichier CSV nommé C : \\ Data \\ Failure \_List.csv.</span><span class="sxs-lookup"><span data-stu-id="96e51-125">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="96e51-126">En fonction des données enregistrées dans ce fichier, la commande suivante répertorie tous les utilisateurs qui ont été impliqués dans au moins une session ayant échoué :</span><span class="sxs-lookup"><span data-stu-id="96e51-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="96e51-127">Cette commande retourne une liste semblable à ceci :</span><span class="sxs-lookup"><span data-stu-id="96e51-127">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="96e51-128">Les deux commandes suivantes retournent le nombre total de sessions ayant échoué dans lesquelles chaque utilisateur a été impliqué :</span><span class="sxs-lookup"><span data-stu-id="96e51-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="96e51-129">Des données semblables à ceci sont alors retournées :</span><span class="sxs-lookup"><span data-stu-id="96e51-129">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="96e51-130">Filtres</span><span class="sxs-lookup"><span data-stu-id="96e51-130">Filters</span></span>

<span data-ttu-id="96e51-p105">Aucun. Il est impossible de filtrer le Rapport des listes d’échecs.</span><span class="sxs-lookup"><span data-stu-id="96e51-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="96e51-133">Mesures</span><span class="sxs-lookup"><span data-stu-id="96e51-133">Metrics</span></span>

<span data-ttu-id="96e51-134">Le tableau qui suit répertorie les informations fournies dans le Rapport des listes d’échecs pour chaque appel ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="96e51-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="96e51-135">Mesures du Rapport des listes d’échecs</span><span class="sxs-lookup"><span data-stu-id="96e51-135">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96e51-136">Nom</span><span class="sxs-lookup"><span data-stu-id="96e51-136">Name</span></span></th>
<th><span data-ttu-id="96e51-137">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="96e51-137">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="96e51-138">Description</span><span class="sxs-lookup"><span data-stu-id="96e51-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96e51-139"><strong>Heure du rapport</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-139"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-140">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-140">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-141">Date et heure d’enregistrement du rapport.</span><span class="sxs-lookup"><span data-stu-id="96e51-141">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e51-142"><strong>Demande</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-142"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-143">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-143">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-p106">Type de demande SIP ayant échoué. Par exemple, INVITE ou BYE.</span><span class="sxs-lookup"><span data-stu-id="96e51-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e51-146"><strong>Code de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-146"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-147">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-147">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-148">Code de réponse SIP envoyé lors de l’échec de conférence.</span><span class="sxs-lookup"><span data-stu-id="96e51-148">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e51-149"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-149"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-150">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-150">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-151">Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="96e51-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e51-152"><strong>Coût/temps de connexion (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-152"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-153">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-153">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-154">Temps (en millisecondes) requis pour que l’utilisateur rejoigne la conférence.</span><span class="sxs-lookup"><span data-stu-id="96e51-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e51-155"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-155"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-156">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-156">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-157">Adresse SIP de l’utilisateur qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="96e51-157">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e51-158"><strong>Agent utilisateur d’origine</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-158"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-159">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-159">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-160">Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="96e51-160">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e51-161"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="96e51-161"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="96e51-162">Non</span><span class="sxs-lookup"><span data-stu-id="96e51-162">No</span></span></p></td>
<td><p><span data-ttu-id="96e51-163">Adresse IP de l’utilisateur qui était appelé.</span><span class="sxs-lookup"><span data-stu-id="96e51-163">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

