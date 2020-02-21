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
ms.openlocfilehash: 6b3683e2a2ac9fb163fe9db3dabce40b3c61d098
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="e25b1-102">Interprétation des résultats</span><span class="sxs-lookup"><span data-stu-id="e25b1-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e25b1-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e25b1-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e25b1-104">L’outil de contrainte et de performances de Lync Server 2013 (LyncPerfTool. exe) comporte de nombreux compteurs que vous pouvez utiliser pour comprendre ce que fait le client et s’il rencontre des problèmes.</span><span class="sxs-lookup"><span data-stu-id="e25b1-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="e25b1-105">Compteurs client</span><span class="sxs-lookup"><span data-stu-id="e25b1-105">Client Counters</span></span>

<span data-ttu-id="e25b1-106">Chaque instance de LyncPerfTool. exe en cours d’exécution dispose d’une instance distincte des compteurs.</span><span class="sxs-lookup"><span data-stu-id="e25b1-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="e25b1-107">Chaque instance est nommée par son ID de processus.</span><span class="sxs-lookup"><span data-stu-id="e25b1-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="e25b1-108">Si les clients sont surchargés, des problèmes peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="e25b1-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="e25b1-109">Pour éviter ces problèmes, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e25b1-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="e25b1-110">Surveillez l’utilisation du processeur et de la mémoire sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="e25b1-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="e25b1-111">Si le processeur est toujours supérieur à 90%, réduisez le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e25b1-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="e25b1-112">Si l’encombrement mémoire est élevé, vous pouvez rencontrer des problèmes si le fichier d’échange n’est pas assez grand.</span><span class="sxs-lookup"><span data-stu-id="e25b1-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="e25b1-113">Vérifiez que la charge dédiée n’atteint pas la limite de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="e25b1-114">Si vous utilisez des limites de mémoire, envisagez d’augmenter la taille du fichier d’échange ou de réduire le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e25b1-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="e25b1-115">Les tableaux suivants répertorient les compteurs de performances Key LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="e25b1-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="e25b1-116">**Informations générales**</span><span class="sxs-lookup"><span data-stu-id="e25b1-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-117"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-118"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-119">Temps passé en minutes</span><span class="sxs-lookup"><span data-stu-id="e25b1-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="e25b1-120">Temps passé depuis le démarrage du processus.</span><span class="sxs-lookup"><span data-stu-id="e25b1-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-121">Points de terminaison actifs</span><span class="sxs-lookup"><span data-stu-id="e25b1-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="e25b1-122">Nombre de points de terminaison actuellement connectés au serveur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-123">Échecs de connexion</span><span class="sxs-lookup"><span data-stu-id="e25b1-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="e25b1-124">Nombre total d’échecs de connexion au point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e25b1-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-125">Tentatives de connexion</span><span class="sxs-lookup"><span data-stu-id="e25b1-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="e25b1-126">Nombre total de tentatives de connexion au point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e25b1-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-127">Points de terminaison déconnectés</span><span class="sxs-lookup"><span data-stu-id="e25b1-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="e25b1-128">Nombre total de points de terminaison qui ont été déconnectés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-129">**Informations de présence**</span><span class="sxs-lookup"><span data-stu-id="e25b1-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-130"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-131"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-132">Appels SetPresence</span><span class="sxs-lookup"><span data-stu-id="e25b1-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="e25b1-133">Nombre total de tentatives de modification de présence.</span><span class="sxs-lookup"><span data-stu-id="e25b1-133">Total number of presence change attempts.</span></span> <span data-ttu-id="e25b1-134">Pour les différents types de modifications de présence, voir le compteur de performances appels SetPresence (type de présence).</span><span class="sxs-lookup"><span data-stu-id="e25b1-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-135">NNN réponses pour SetPresence</span><span class="sxs-lookup"><span data-stu-id="e25b1-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="e25b1-136">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-137">Appels GetPresence</span><span class="sxs-lookup"><span data-stu-id="e25b1-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="e25b1-138">Nombre total de tentatives de demande d’obtention de présence.</span><span class="sxs-lookup"><span data-stu-id="e25b1-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-139">NNN réponses pour GetPresence</span><span class="sxs-lookup"><span data-stu-id="e25b1-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="e25b1-140">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-141">**Informations du service de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="e25b1-141">**Address Book service Information**</span></span>

<span data-ttu-id="e25b1-142">Cette catégorie comprend les compteurs utilisés pour surveiller les téléchargements de fichiers du service de carnet d’adresses et les demandes de service de requête Web du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="e25b1-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-143"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-144"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-145">Tentatives de téléchargements de fichiers complets/Delta ABS</span><span class="sxs-lookup"><span data-stu-id="e25b1-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-146">Nombre total de demandes de téléchargements de fichiers complets ou deltas.</span><span class="sxs-lookup"><span data-stu-id="e25b1-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-147">Les téléchargements de fichiers complets/Delta ABS ont réussi</span><span class="sxs-lookup"><span data-stu-id="e25b1-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e25b1-148">Nombre total de demandes de téléchargements de fichiers complets ou deltas.</span><span class="sxs-lookup"><span data-stu-id="e25b1-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-149">Compteurs liés au service de requête Web du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="e25b1-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="e25b1-150">Compteurs liés au téléchargement du fichier de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="e25b1-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-151">Tentatives d’appels WS WS</span><span class="sxs-lookup"><span data-stu-id="e25b1-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-152">Nombre total de demandes de service de requête sur le Web du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="e25b1-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-153">Appels WS WS réussis</span><span class="sxs-lookup"><span data-stu-id="e25b1-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e25b1-154">Nombre total de demandes de service de requête Web de carnet d’adresses ayant renvoyé un code de réponse réussi.</span><span class="sxs-lookup"><span data-stu-id="e25b1-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-155">Échec des appels d’ABS WS</span><span class="sxs-lookup"><span data-stu-id="e25b1-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="e25b1-156">Nombre total de demandes de service de requête Web de carnet d’adresses qui a renvoyé un code de réponse d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-157">**Informations sur la liste de distribution (DL)**</span><span class="sxs-lookup"><span data-stu-id="e25b1-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-158"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-159"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-160">Tentatives d’appels</span><span class="sxs-lookup"><span data-stu-id="e25b1-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-161">Nombre total de demandes de service Web d’expansion de liste de distribution (DLX).</span><span class="sxs-lookup"><span data-stu-id="e25b1-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-162">Appels réussis</span><span class="sxs-lookup"><span data-stu-id="e25b1-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e25b1-163">Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse réussi.</span><span class="sxs-lookup"><span data-stu-id="e25b1-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-164">Échec des appels</span><span class="sxs-lookup"><span data-stu-id="e25b1-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="e25b1-165">Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-166">**Informations de base VoIP**</span><span class="sxs-lookup"><span data-stu-id="e25b1-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="e25b1-167">Les compteurs de performance répertoriés ci-dessous indiquent les numéros de tous les appels VoIP (Voice over IP), y compris les appels vers le serveur de médiation, le serveur de conférence A/V, le serveur Edge, l’application Response Group et le standard automatique de conférence, lorsque ces scénarios sont activés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-168"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-169"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-170">Appelle active</span><span class="sxs-lookup"><span data-stu-id="e25b1-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="e25b1-171">Nombre total d’appels vocaux entrants/sortants en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-172">Appels terminés</span><span class="sxs-lookup"><span data-stu-id="e25b1-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="e25b1-173">Nombre total d’appels vocaux entrants/sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-174">Appels refusés</span><span class="sxs-lookup"><span data-stu-id="e25b1-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="e25b1-175">Nombre total d’appels vocaux entrants refusés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-176">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="e25b1-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-177">Nombre total d’appels vocaux entrants/sortants tentés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-178">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="e25b1-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="e25b1-179">Nombre total d’appels vocaux entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="e25b1-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-180">Appels reçus NNN</span><span class="sxs-lookup"><span data-stu-id="e25b1-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="e25b1-181">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-182">Taux de réussite VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="e25b1-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="e25b1-183">Nombre total d’appels établis/nombre total d’appels tentés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-184">**Informations sur les appels au service Response Group**</span><span class="sxs-lookup"><span data-stu-id="e25b1-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-185"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-186"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-187">Appelle active</span><span class="sxs-lookup"><span data-stu-id="e25b1-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="e25b1-188">Nombre total d’appels actifs à l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="e25b1-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-189">Tentatives d’appels</span><span class="sxs-lookup"><span data-stu-id="e25b1-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-190">Nombre total d’appels tentés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-191">**Informations sur les appels de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="e25b1-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-192"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-193"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-194">Appelle active</span><span class="sxs-lookup"><span data-stu-id="e25b1-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="e25b1-195">Nombre total d’appels de messagerie instantanée entrants/sortants en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-196">Appels terminés</span><span class="sxs-lookup"><span data-stu-id="e25b1-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="e25b1-197">Nombre total d’appels de messagerie instantanée entrants/sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-198">Appels reçus NNN</span><span class="sxs-lookup"><span data-stu-id="e25b1-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="e25b1-199">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-200">Messages INSTANTANÉs reçus/envoyés</span><span class="sxs-lookup"><span data-stu-id="e25b1-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="e25b1-201">Nombre total de messages reçus ou envoyés pour toutes les sessions.</span><span class="sxs-lookup"><span data-stu-id="e25b1-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-202">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="e25b1-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-203">Nombre total d’appels de messagerie instantanée entrants/sortants.</span><span class="sxs-lookup"><span data-stu-id="e25b1-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-204">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="e25b1-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="e25b1-205">Nombre total d’appels de messagerie instantanée entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="e25b1-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-206">**Informations sur les appels de partage d’application**</span><span class="sxs-lookup"><span data-stu-id="e25b1-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-207"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-208"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-209">Appelle active</span><span class="sxs-lookup"><span data-stu-id="e25b1-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="e25b1-210">Nombre total d’appels de partage d’application entrants/sortants en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-211">Appels terminés</span><span class="sxs-lookup"><span data-stu-id="e25b1-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="e25b1-212">Nombre total d’appels de partage d’application entrants et sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-213">Appels reçus NNN</span><span class="sxs-lookup"><span data-stu-id="e25b1-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="e25b1-214">Nombre total de codes de réponse nnn reçus du serveur.</span><span class="sxs-lookup"><span data-stu-id="e25b1-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-215">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="e25b1-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-216">Nombre total d’appels de partage d’application entrants/sortants.</span><span class="sxs-lookup"><span data-stu-id="e25b1-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-217">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="e25b1-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="e25b1-218">Nombre total d’appels de partage d’application entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="e25b1-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-219">**Informations sur les appels CAA**</span><span class="sxs-lookup"><span data-stu-id="e25b1-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-220"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-221"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-222">Appelle active</span><span class="sxs-lookup"><span data-stu-id="e25b1-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="e25b1-223">Nombre total d’appels RTC (réseau téléphonique commuté) en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-224">Appels terminés</span><span class="sxs-lookup"><span data-stu-id="e25b1-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="e25b1-225">Nombre total d’appels RTC entrants/sortants déjà terminés.</span><span class="sxs-lookup"><span data-stu-id="e25b1-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-226">Tentatives d’appels entrants/sortants</span><span class="sxs-lookup"><span data-stu-id="e25b1-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="e25b1-227">Nombre total d’appels RTC entrants/sortants.</span><span class="sxs-lookup"><span data-stu-id="e25b1-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-228">Appels entrants/sortants établis</span><span class="sxs-lookup"><span data-stu-id="e25b1-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="e25b1-229">Nombre total d’appels RTC entrants/sortants établis.</span><span class="sxs-lookup"><span data-stu-id="e25b1-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-230">**Informations sur la Conférence**</span><span class="sxs-lookup"><span data-stu-id="e25b1-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-231"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-232"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-233">Conférences de messagerie instantanée actives</span><span class="sxs-lookup"><span data-stu-id="e25b1-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="e25b1-234">Nombre total de conférences de messagerie instantanée en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-235">Conférences audio/vidéo actives</span><span class="sxs-lookup"><span data-stu-id="e25b1-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="e25b1-236">Nombre total de conférences audio/vidéo (A/V) en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-237">Conférences de partage d’applications actives</span><span class="sxs-lookup"><span data-stu-id="e25b1-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="e25b1-238">Nombre total de conférences de partage d’application en cours.</span><span class="sxs-lookup"><span data-stu-id="e25b1-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-239">Nombre de participants</span><span class="sxs-lookup"><span data-stu-id="e25b1-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="e25b1-240">Nombre total de participants actuellement connectés à des conférences.</span><span class="sxs-lookup"><span data-stu-id="e25b1-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-241">Échec de la planification des conférences</span><span class="sxs-lookup"><span data-stu-id="e25b1-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="e25b1-242">Nombre total d’échecs lors de la tentative de planification d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="e25b1-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-243">Rejoindre la Conférence</span><span class="sxs-lookup"><span data-stu-id="e25b1-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="e25b1-244">Nombre total d’échecs lors de la tentative de connexion à une conférence.</span><span class="sxs-lookup"><span data-stu-id="e25b1-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e25b1-245">**Compteurs client UCWA**</span><span class="sxs-lookup"><span data-stu-id="e25b1-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-246"><strong>Compteur de performance</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="e25b1-247"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e25b1-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-248">Nombre total de jointures IMMCU réussies</span><span class="sxs-lookup"><span data-stu-id="e25b1-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e25b1-249">Nombre total de conférences de messagerie instantanée jointes.</span><span class="sxs-lookup"><span data-stu-id="e25b1-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-250">Nombre total de jointures DMCU réussies</span><span class="sxs-lookup"><span data-stu-id="e25b1-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e25b1-251">Nombre total de conférences A/V jointes.</span><span class="sxs-lookup"><span data-stu-id="e25b1-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

