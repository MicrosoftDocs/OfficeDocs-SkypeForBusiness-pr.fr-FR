---
title: Rapport Détails de la Conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Résumé: en savoir plus sur le rapport Détails de la Conférence utilisé dans Skype entreprise Server.'
ms.openlocfilehash: 5b88ae62c7d06437b3502bd72dd965fc26fbfcb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305786"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="b86d7-103">Rapport Détails de la Conférence dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b86d7-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="b86d7-104">**Résumé:** En savoir plus sur le rapport Détails de la Conférence utilisé dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b86d7-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="b86d7-p101">Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="b86d7-109">Accès au rapport détaillé de conférence</span><span class="sxs-lookup"><span data-stu-id="b86d7-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="b86d7-110">Le rapport détaillé de conférence est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="b86d7-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="b86d7-111">Le [Call Admission Control Report](call-admission-control-report.md) (en cliquant sur la mesure Détails d’une conférence)</span><span class="sxs-lookup"><span data-stu-id="b86d7-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="b86d7-112">Le [Failure List Report](failure-list-report.md) (en cliquant sur la mesure Conférence)</span><span class="sxs-lookup"><span data-stu-id="b86d7-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="b86d7-113">Le [User Activity Report](call-diagnostic-reports-per-user.md) (en cliquant sur la mesure URI de la conférence)</span><span class="sxs-lookup"><span data-stu-id="b86d7-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="b86d7-114">Dans le rapport Détails de la Conférence, vous pouvez accéder au [repor de diagnostic](diagnostic-report.md) en cliquant sur la métrique du rapport de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="b86d7-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="b86d7-115">Filtres</span><span class="sxs-lookup"><span data-stu-id="b86d7-115">Filters</span></span>

<span data-ttu-id="b86d7-p102">Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="b86d7-118">Mesures</span><span class="sxs-lookup"><span data-stu-id="b86d7-118">Metrics</span></span>

<span data-ttu-id="b86d7-119">Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="b86d7-120">**Mesures des informations de conférence**</span><span class="sxs-lookup"><span data-stu-id="b86d7-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="b86d7-121">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b86d7-121">**Name**</span></span>                 | <span data-ttu-id="b86d7-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="b86d7-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b86d7-123">**URI de la conférence**</span><span class="sxs-lookup"><span data-stu-id="b86d7-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="b86d7-p103">URI affectée à la conférence. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b86d7-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="b86d7-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="b86d7-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="b86d7-127">**FQDN du pool**</span><span class="sxs-lookup"><span data-stu-id="b86d7-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="b86d7-128">Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.</span><span class="sxs-lookup"><span data-stu-id="b86d7-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="b86d7-129">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="b86d7-129">**Start time**</span></span> <br/>     | <span data-ttu-id="b86d7-130">Date et heure auxquelles la conférence a commencé.</span><span class="sxs-lookup"><span data-stu-id="b86d7-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="b86d7-131">**Organisateur**</span><span class="sxs-lookup"><span data-stu-id="b86d7-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="b86d7-132">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="b86d7-133">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="b86d7-133">**End time**</span></span> <br/>       | <span data-ttu-id="b86d7-134">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="b86d7-135">Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="b86d7-136">**Mesures de participation à la conférence**</span><span class="sxs-lookup"><span data-stu-id="b86d7-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="b86d7-137">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b86d7-137">**Name**</span></span>|<span data-ttu-id="b86d7-138">**Description**</span><span class="sxs-lookup"><span data-stu-id="b86d7-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b86d7-139">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b86d7-139">**User**</span></span> <br/> |<span data-ttu-id="b86d7-140">Adresse SIP de l’utilisateur qui a participé à la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-141">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="b86d7-141">**Role**</span></span> <br/> |<span data-ttu-id="b86d7-142">Rôle (par exemple, présentateur) joué par le participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="b86d7-143">**Connectivité**</span><span class="sxs-lookup"><span data-stu-id="b86d7-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="b86d7-144">Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</span><span class="sxs-lookup"><span data-stu-id="b86d7-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="b86d7-145">**Heure d’arrivée**</span><span class="sxs-lookup"><span data-stu-id="b86d7-145">**Join time**</span></span> <br/> |<span data-ttu-id="b86d7-146">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-147">**Heure de départ**</span><span class="sxs-lookup"><span data-stu-id="b86d7-147">**Leave time**</span></span> <br/> |<span data-ttu-id="b86d7-148">Date et heure auxquelles le participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-149">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b86d7-149">**User agent**</span></span> <br/> |<span data-ttu-id="b86d7-150">Identificateur pour le logiciel utilisé par le point de terminaison du participant.</span><span class="sxs-lookup"><span data-stu-id="b86d7-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="b86d7-151">**Rapports de diagnostic**</span><span class="sxs-lookup"><span data-stu-id="b86d7-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="b86d7-p104">Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="b86d7-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="b86d7-154">Le tableau suivant répertorie les informations fournies dans la section modalités de la Conférence du rapport Détails de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="b86d7-155">**Mesures des modalités de conférence**</span><span class="sxs-lookup"><span data-stu-id="b86d7-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="b86d7-156">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b86d7-156">**Name**</span></span>|<span data-ttu-id="b86d7-157">**Description**</span><span class="sxs-lookup"><span data-stu-id="b86d7-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b86d7-158">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b86d7-158">**User**</span></span> <br/> |<span data-ttu-id="b86d7-159">Adresse SIP de l’utilisateur qui a participé à la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-160">**Heure d’arrivée**</span><span class="sxs-lookup"><span data-stu-id="b86d7-160">**Join time**</span></span> <br/> |<span data-ttu-id="b86d7-161">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-162">**Heure de départ**</span><span class="sxs-lookup"><span data-stu-id="b86d7-162">**Leave time**</span></span> <br/> |<span data-ttu-id="b86d7-163">Date et heure auxquelles un participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-164">**URI du serveur de conférence**</span><span class="sxs-lookup"><span data-stu-id="b86d7-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="b86d7-165">URI du serveur de conférence utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="b86d7-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="b86d7-166">**Rapports de diagnostic**</span><span class="sxs-lookup"><span data-stu-id="b86d7-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="b86d7-p105">Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="b86d7-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


