---
title: Interprétation des résultats
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="8bb53-102">Interprétation des résultats</span><span class="sxs-lookup"><span data-stu-id="8bb53-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bb53-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8bb53-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="8bb53-104">L’outil de stress et de performance de Lync Server 2013 (LyncPerfTool. exe) comporte de nombreux compteurs qui vous permettent de comprendre ce que le client effectue et s’il rencontre des problèmes.</span><span class="sxs-lookup"><span data-stu-id="8bb53-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="8bb53-105">Compteurs clients</span><span class="sxs-lookup"><span data-stu-id="8bb53-105">Client Counters</span></span>

<span data-ttu-id="8bb53-106">Chaque instance de LyncPerfTool. exe en cours d’exécution dispose d’une instance distincte des compteurs.</span><span class="sxs-lookup"><span data-stu-id="8bb53-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="8bb53-107">Chaque instance est nommée par son ID de processus.</span><span class="sxs-lookup"><span data-stu-id="8bb53-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="8bb53-108">Si les clients sont surchargés, des problèmes peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="8bb53-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="8bb53-109">Pour éviter ce problème, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8bb53-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="8bb53-110">Surveiller le processeur et l’utilisation de la mémoire sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="8bb53-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="8bb53-111">Si le processeur est toujours supérieur à 90%, réduisez le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8bb53-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="8bb53-112">Si l’encombrement mémoire est élevé, vous risquez de rencontrer des problèmes si le fichier de la page n’est pas assez grand.</span><span class="sxs-lookup"><span data-stu-id="8bb53-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="8bb53-113">Assurez-vous que la mémoire de validation n’atteint pas la limite de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="8bb53-114">Si vous utilisez des limites de mémoire, envisagez d’augmenter la taille de fichier de la page ou de réduire le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8bb53-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="8bb53-115">Les tableaux suivants répertorient les principaux compteurs de performances de LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="8bb53-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="8bb53-116">**Informations générales**</span><span class="sxs-lookup"><span data-stu-id="8bb53-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-117"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-118"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-119">Temps passé en minutes</span><span class="sxs-lookup"><span data-stu-id="8bb53-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="8bb53-120">Temps passé depuis le démarrage du processus.</span><span class="sxs-lookup"><span data-stu-id="8bb53-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-121">Points de terminaison actifs</span><span class="sxs-lookup"><span data-stu-id="8bb53-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="8bb53-122">Nombre de points de terminaison actuellement connectés au serveur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-123">Échecs de connexion</span><span class="sxs-lookup"><span data-stu-id="8bb53-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="8bb53-124">Nombre total d’échecs de connexion de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="8bb53-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-125">Tentatives d’ouverture de session</span><span class="sxs-lookup"><span data-stu-id="8bb53-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="8bb53-126">Nombre total de tentatives de connexion de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="8bb53-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-127">Points de terminaison déconnectés</span><span class="sxs-lookup"><span data-stu-id="8bb53-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="8bb53-128">Nombre total de points de terminaison qui ont été déconnectés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-129">**Informations de présence**</span><span class="sxs-lookup"><span data-stu-id="8bb53-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-130"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-131"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-132">Appels SetPresence</span><span class="sxs-lookup"><span data-stu-id="8bb53-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="8bb53-133">Nombre total de tentatives de changement de présence.</span><span class="sxs-lookup"><span data-stu-id="8bb53-133">Total number of presence change attempts.</span></span> <span data-ttu-id="8bb53-134">Pour les différents types de modifications de présence, voir le compteur de performance appels SetPresence (type de présence).</span><span class="sxs-lookup"><span data-stu-id="8bb53-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-135">NNN réponses pour SetPresence</span><span class="sxs-lookup"><span data-stu-id="8bb53-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="8bb53-136">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-137">Appels GetPresence</span><span class="sxs-lookup"><span data-stu-id="8bb53-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="8bb53-138">Nombre total de tentatives de demande de présence.</span><span class="sxs-lookup"><span data-stu-id="8bb53-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-139">NNN réponses pour GetPresence</span><span class="sxs-lookup"><span data-stu-id="8bb53-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="8bb53-140">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-141">**Informations relatives au service de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="8bb53-141">**Address Book service Information**</span></span>

<span data-ttu-id="8bb53-142">Cette catégorie inclut des compteurs permettant de surveiller les téléchargements de fichiers du service de carnet d’adresses et les demandes de service de requête sur le carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="8bb53-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-143"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-144"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-145">Tentatives de téléchargements de fichiers complets/Delta de ABS</span><span class="sxs-lookup"><span data-stu-id="8bb53-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-146">Nombre total de demandes de téléchargement de fichiers complets ou Delta.</span><span class="sxs-lookup"><span data-stu-id="8bb53-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-147">Réussite des téléchargements de fichiers complets/Delta</span><span class="sxs-lookup"><span data-stu-id="8bb53-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="8bb53-148">Nombre total de demandes de téléchargement de fichiers complets ou Delta.</span><span class="sxs-lookup"><span data-stu-id="8bb53-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-149">Compteurs liés au service de requête Web dans le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="8bb53-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="8bb53-150">Compteurs liés au téléchargement du fichier du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="8bb53-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-151">Tentatives d’appels WS WS</span><span class="sxs-lookup"><span data-stu-id="8bb53-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-152">Nombre total de demandes de service de requête Web dans le carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="8bb53-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-153">Appels WS WS réussis</span><span class="sxs-lookup"><span data-stu-id="8bb53-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="8bb53-154">Nombre total de demandes de service de requête Web de carnet d’adresses qui renvoient un code de réponse réussi.</span><span class="sxs-lookup"><span data-stu-id="8bb53-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-155">Échecs des services d’ABS WS</span><span class="sxs-lookup"><span data-stu-id="8bb53-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="8bb53-156">Nombre total de demandes de service de requête Web de carnet d’adresses qui renvoient un code de réponse d’erreur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-157">**Informations de liste de distribution (DL)**</span><span class="sxs-lookup"><span data-stu-id="8bb53-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-158"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-159"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-160">Appels essayés</span><span class="sxs-lookup"><span data-stu-id="8bb53-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-161">Nombre total de demandes de service Web d’extension de liste de distribution (DLX) effectuées.</span><span class="sxs-lookup"><span data-stu-id="8bb53-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-162">Appels réussis</span><span class="sxs-lookup"><span data-stu-id="8bb53-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="8bb53-163">Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse réussi.</span><span class="sxs-lookup"><span data-stu-id="8bb53-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-164">Appels en échec</span><span class="sxs-lookup"><span data-stu-id="8bb53-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="8bb53-165">Nombre total de demandes de service Web DLX qui renvoient un code de réponse d’erreur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-166">**Informations de base sur VoIP**</span><span class="sxs-lookup"><span data-stu-id="8bb53-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="8bb53-167">Les compteurs de performance indiqués ci-dessous indiquent les numéros de tous les appels voix sur IP (VoIP), y compris les appels vers le serveur de médiation, le serveur de conférence A/V, le serveur Edge, l’application Response Group et le standard automatique des conférences, lorsque ces scénarios sont activés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-168"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-169"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-170">Appels actifs</span><span class="sxs-lookup"><span data-stu-id="8bb53-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="8bb53-171">Nombre total d’appels vocaux entrants/sortants actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="8bb53-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-172">Appels interrompus</span><span class="sxs-lookup"><span data-stu-id="8bb53-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="8bb53-173">Nombre total d’appels vocaux entrants/sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-174">Appels refusés</span><span class="sxs-lookup"><span data-stu-id="8bb53-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="8bb53-175">Nombre total d’appels vocaux entrants refusés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-176">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="8bb53-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-177">Nombre total d’appels vocaux entrants/sortants.</span><span class="sxs-lookup"><span data-stu-id="8bb53-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-178">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="8bb53-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="8bb53-179">Nombre total d’appels vocaux entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="8bb53-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-180">Appels reçus NNN</span><span class="sxs-lookup"><span data-stu-id="8bb53-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="8bb53-181">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-182">Taux de passe VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="8bb53-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="8bb53-183">Nombre total d’appels passés/nombre total d’appels tentés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-184">**Informations de l’appel service de Response Group**</span><span class="sxs-lookup"><span data-stu-id="8bb53-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-185"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-186"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-187">Appels actifs</span><span class="sxs-lookup"><span data-stu-id="8bb53-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="8bb53-188">Nombre total d’appels actifs vers l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="8bb53-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-189">Appels essayés</span><span class="sxs-lookup"><span data-stu-id="8bb53-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-190">Nombre total d’appels tentés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-191">**Informations sur les appels de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="8bb53-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-192"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-193"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-194">Appels actifs</span><span class="sxs-lookup"><span data-stu-id="8bb53-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="8bb53-195">Nombre total d’appels de messages instantanés entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="8bb53-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-196">Appels interrompus</span><span class="sxs-lookup"><span data-stu-id="8bb53-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="8bb53-197">Nombre total d’appels entrants/sortants de messagerie instantanée déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-198">Appels reçus NNN</span><span class="sxs-lookup"><span data-stu-id="8bb53-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="8bb53-199">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-200">Messages INSTANTANÉs reçus/envoyés</span><span class="sxs-lookup"><span data-stu-id="8bb53-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="8bb53-201">Nombre total de messages reçus ou envoyés pour toutes les sessions.</span><span class="sxs-lookup"><span data-stu-id="8bb53-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-202">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="8bb53-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-203">Nombre total d’appels entrants/sortants de messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-204">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="8bb53-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="8bb53-205">Nombre total d’appels entrants/sortants de messages instantanés établis.</span><span class="sxs-lookup"><span data-stu-id="8bb53-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-206">**Informations sur les appels de partage d’application**</span><span class="sxs-lookup"><span data-stu-id="8bb53-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-207"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-208"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-209">Appels actifs</span><span class="sxs-lookup"><span data-stu-id="8bb53-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="8bb53-210">Nombre total d’appels de partage d’application entrants ou sortants.</span><span class="sxs-lookup"><span data-stu-id="8bb53-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-211">Appels interrompus</span><span class="sxs-lookup"><span data-stu-id="8bb53-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="8bb53-212">Nombre total d’appels de partage d’application entrants/sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-213">Appels reçus NNN</span><span class="sxs-lookup"><span data-stu-id="8bb53-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="8bb53-214">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="8bb53-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-215">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="8bb53-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-216">Nombre total d’appels entrants/sortants de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="8bb53-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-217">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="8bb53-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="8bb53-218">Nombre total d’appels de partage d’application entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="8bb53-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-219">**Informations sur les appels CAA**</span><span class="sxs-lookup"><span data-stu-id="8bb53-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-220"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-221"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-222">Appels actifs</span><span class="sxs-lookup"><span data-stu-id="8bb53-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="8bb53-223">Nombre total d’appels entrants/sortants de réseau téléphonique commuté (RTC) actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="8bb53-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-224">Appels interrompus</span><span class="sxs-lookup"><span data-stu-id="8bb53-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="8bb53-225">Nombre total d’appels RTC entrants/sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="8bb53-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-226">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="8bb53-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="8bb53-227">Nombre total d’appels RTC entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="8bb53-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-228">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="8bb53-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="8bb53-229">Nombre total d’appels RTC entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="8bb53-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-230">**Informations sur la Conférence**</span><span class="sxs-lookup"><span data-stu-id="8bb53-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-231"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-232"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-233">Conférences de messagerie instantanée actives</span><span class="sxs-lookup"><span data-stu-id="8bb53-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="8bb53-234">Nombre total de conférences de messagerie instantanée en cours.</span><span class="sxs-lookup"><span data-stu-id="8bb53-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-235">Conférences audio/vidéo actives</span><span class="sxs-lookup"><span data-stu-id="8bb53-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="8bb53-236">Nombre total de conférences audio/vidéo (A/V) en cours.</span><span class="sxs-lookup"><span data-stu-id="8bb53-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-237">Conférences de partage d’application actives</span><span class="sxs-lookup"><span data-stu-id="8bb53-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="8bb53-238">Nombre total de conférences de partage d’application en cours.</span><span class="sxs-lookup"><span data-stu-id="8bb53-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-239">Nombre de participants</span><span class="sxs-lookup"><span data-stu-id="8bb53-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="8bb53-240">Nombre total de participants actuellement connectés aux conférences.</span><span class="sxs-lookup"><span data-stu-id="8bb53-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-241">Échec de la planification de conférences</span><span class="sxs-lookup"><span data-stu-id="8bb53-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="8bb53-242">Nombre total d’échecs lors de la planification d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="8bb53-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-243">Participer à une conférence téléphonique</span><span class="sxs-lookup"><span data-stu-id="8bb53-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="8bb53-244">Nombre total d’échecs lors d’une tentative de connexion à une conférence.</span><span class="sxs-lookup"><span data-stu-id="8bb53-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8bb53-245">**Compteurs du client UCWA**</span><span class="sxs-lookup"><span data-stu-id="8bb53-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bb53-246"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="8bb53-247"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8bb53-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bb53-248">Nombre total de jointures IMMCU réussies</span><span class="sxs-lookup"><span data-stu-id="8bb53-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="8bb53-249">Nombre total de conférences de messagerie instantanée jointes.</span><span class="sxs-lookup"><span data-stu-id="8bb53-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bb53-250">Nombre total de jointures DMCU réussies</span><span class="sxs-lookup"><span data-stu-id="8bb53-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="8bb53-251">Nombre total de conférences A/V jointes.</span><span class="sxs-lookup"><span data-stu-id="8bb53-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

