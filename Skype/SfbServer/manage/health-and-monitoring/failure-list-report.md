---
title: Failure List Report dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Résumé : Découvrez le Failure List Report dans Skype pour Business Server.'
ms.openlocfilehash: 67c02e9b0366bcf850139717eedf5c3946183988
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926598"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="ed323-103">Failure List Report dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="ed323-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="ed323-104">**Résumé :** Découvrez le Failure List Report dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ed323-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="ed323-p101">Le Rapport des listes d’échecs fournit des informations sur les participants individuels à une session P2P ou session de conférence ayant échoué. Ces informations incluent l’URI de l’utilisateur qui a rencontré le problème, ainsi que le code de réponse SIP et l’ID de diagnostic associés à l’échec.</span><span class="sxs-lookup"><span data-stu-id="ed323-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="ed323-107">Accès au Rapport des listes d’échecs</span><span class="sxs-lookup"><span data-stu-id="ed323-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="ed323-108">Le rapport liste des défaillances est accessible en cliquant sur une des mesures suivantes dans le [Rapport de répartition dans Skype pour Business Server](failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="ed323-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="ed323-109">Motifs de diagnostic principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="ed323-110">Modalités principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="ed323-111">Pools principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="ed323-112">Sources principales (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="ed323-113">Composants principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="ed323-114">Utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="ed323-115">Utilisateurs destinataires principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="ed323-116">Agents utilisateurs émetteurs principaux (sessions)</span><span class="sxs-lookup"><span data-stu-id="ed323-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="ed323-117">Dans le rapport liste des défaillances, vous pouvez accéder le [rapport détaillé de Session d’égal à égal dans Skype pour Business Server](peer-to-peer-session-detail-report.md) en cliquant sur la mesure détail de Session pour une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="ed323-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="ed323-118">Vous pouvez également accéder au Rapport détaillé de conférence en cliquant sur la mesure Conférence pour une conférence.</span><span class="sxs-lookup"><span data-stu-id="ed323-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="ed323-119">Exploitation optimale du Rapport des listes d’échecs</span><span class="sxs-lookup"><span data-stu-id="ed323-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="ed323-p103">Le Rapport des listes d’échecs vous permet d’afficher une description de chaque code de réponse ou de chaque ID de diagnostic en maintenant simplement la souris au-dessus de la valeur concernée. Par exemple, si vous maintenez la souris au-dessus de l’ID de diagnostic 7025, les informations suivantes s’affichent dans une info-bulle :</span><span class="sxs-lookup"><span data-stu-id="ed323-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="ed323-122">Erreur du serveur interne lors de la création du média pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed323-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="ed323-123">Il est important de noter que le Rapport des listes d’échecs ne fournit pas une méthode simple de récupérer directement une liste de tous les utilisateurs qui ont participé à au moins une session ayant échoué, et qu’il ne permet pas non plus de déterminer les utilisateurs qui sont le plus souvent impliqués dans une session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="ed323-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="ed323-124">(Pour une chose, le Failure List Report ne possède aucuns possibilités de filtrage) Toutefois, si vous exportez les données, puis la convertir un fichier de valeurs séparées par des virgules, vous pouvez utiliser Windows PowerShell pour trouver les réponses aux questions telles que celles.</span><span class="sxs-lookup"><span data-stu-id="ed323-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="ed323-125">Par exemple, supposons que vous enregistrez les données dans un fichier .CSV nommé C:\Data\Failure_List.csv.</span><span class="sxs-lookup"><span data-stu-id="ed323-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="ed323-126">En fonction des données enregistrées dans ce fichier, la commande suivante répertorie tous les utilisateurs qui ont été impliqués dans au moins une session ayant échoué :</span><span class="sxs-lookup"><span data-stu-id="ed323-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="ed323-127">Cette commande renvoie une liste semblable à ceci :</span><span class="sxs-lookup"><span data-stu-id="ed323-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="ed323-128">Les deux commandes suivantes renvoient le nombre total de sessions ayant échoué dans lesquelles chaque utilisateur a été impliqué :</span><span class="sxs-lookup"><span data-stu-id="ed323-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="ed323-129">Des données semblables à ceci sont renvoyées :</span><span class="sxs-lookup"><span data-stu-id="ed323-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="ed323-130">Filtres</span><span class="sxs-lookup"><span data-stu-id="ed323-130">Filters</span></span>

<span data-ttu-id="ed323-p105">Aucun. Il est impossible de filtrer le Rapport des listes d’échecs.</span><span class="sxs-lookup"><span data-stu-id="ed323-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="ed323-133">Mesures</span><span class="sxs-lookup"><span data-stu-id="ed323-133">Metrics</span></span>

<span data-ttu-id="ed323-134">Le tableau qui suit répertorie les informations fournies dans le Rapport des listes d’échecs pour chaque appel ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="ed323-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="ed323-135">**Mesures du Rapport des listes d’échecs**</span><span class="sxs-lookup"><span data-stu-id="ed323-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="ed323-136">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ed323-136">**Name**</span></span>|<span data-ttu-id="ed323-137">**Est-il possible d’effectuer un tri sur cet élément ?**</span><span class="sxs-lookup"><span data-stu-id="ed323-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="ed323-138">**Description**</span><span class="sxs-lookup"><span data-stu-id="ed323-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed323-139">**Heure du rapport**</span><span class="sxs-lookup"><span data-stu-id="ed323-139">**Reported time**</span></span> <br/> |<span data-ttu-id="ed323-140">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-140">No</span></span>  <br/> |<span data-ttu-id="ed323-141">Date et heure d’enregistrement du rapport.</span><span class="sxs-lookup"><span data-stu-id="ed323-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="ed323-142">**Demande**</span><span class="sxs-lookup"><span data-stu-id="ed323-142">**Request**</span></span> <br/> |<span data-ttu-id="ed323-143">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-143">No</span></span>  <br/> |<span data-ttu-id="ed323-p106">Type de demande SIP ayant échoué. Par exemple, INVITE ou BYE.</span><span class="sxs-lookup"><span data-stu-id="ed323-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="ed323-146">**Code de réponse**</span><span class="sxs-lookup"><span data-stu-id="ed323-146">**Response code**</span></span> <br/> |<span data-ttu-id="ed323-147">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-147">No</span></span>  <br/> |<span data-ttu-id="ed323-148">Code de réponse SIP envoyé lors de l’échec de conférence.</span><span class="sxs-lookup"><span data-stu-id="ed323-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="ed323-149">**ID de diagnostic**</span><span class="sxs-lookup"><span data-stu-id="ed323-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="ed323-150">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-150">No</span></span>  <br/> |<span data-ttu-id="ed323-151">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.</span><span class="sxs-lookup"><span data-stu-id="ed323-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="ed323-152">**Coût/temps de connexion (ms)**</span><span class="sxs-lookup"><span data-stu-id="ed323-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="ed323-153">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-153">No</span></span>  <br/> |<span data-ttu-id="ed323-154">Temps (en millisecondes) requis pour que l’utilisateur rejoigne la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed323-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="ed323-155">**De l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ed323-155">**From user**</span></span> <br/> |<span data-ttu-id="ed323-156">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-156">No</span></span>  <br/> |<span data-ttu-id="ed323-157">Adresse SIP de l’utilisateur qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="ed323-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="ed323-158">**Agent utilisateur d’origine**</span><span class="sxs-lookup"><span data-stu-id="ed323-158">**From user agent**</span></span> <br/> |<span data-ttu-id="ed323-159">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-159">No</span></span>  <br/> |<span data-ttu-id="ed323-160">Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="ed323-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="ed323-161">**À l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ed323-161">**To user**</span></span> <br/> |<span data-ttu-id="ed323-162">Non</span><span class="sxs-lookup"><span data-stu-id="ed323-162">No</span></span>  <br/> |<span data-ttu-id="ed323-163">Adresse IP de l’utilisateur qui était appelé.</span><span class="sxs-lookup"><span data-stu-id="ed323-163">SIP address of the user who was being called.</span></span>  <br/> |
   

