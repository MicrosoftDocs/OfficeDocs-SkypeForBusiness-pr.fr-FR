---
title: Rapport détaillé de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Résumé : Découvrez le rapport détaillé de conférence utilisé dans Skype Entreprise Server.'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816904"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="dcac4-103">Rapport détaillé de conférence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dcac4-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="dcac4-104">**Résumé :** Découvrez le rapport détaillé de conférence utilisé dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dcac4-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="dcac4-p101">Le rapport détaillé de conférence donne des informations détaillées sur tous les utilisateurs qui ont participé à une conférence. Vous pouvez par exemple voir des informations, telles que la date et l’heure auxquelles un utilisateur s’est joint à la conférence, la date et l’heure auxquelles l’utilisateur a quitté la conférence et l’agent utilisateur du point de terminaison qui a permis à l’utilisateur de se connecter à la conférence. Vous pouvez également afficher des informations sur le rôle de l’utilisateur dans chaque conférence (par exemple présentateur ou participant). Ce qui est peut-être le plus important, vous pouvez voir rapidement quels utilisateurs ont réussi à rejoindre et suivre la conférence et quels utilisateurs n’ont pas réussi à rejoindre et suivre la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="dcac4-109">Accès au rapport détaillé de conférence</span><span class="sxs-lookup"><span data-stu-id="dcac4-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="dcac4-110">Le rapport détaillé de conférence est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="dcac4-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="dcac4-111">Le [Call Admission Control Report](call-admission-control-report.md) (en cliquant sur la mesure Détails d’une conférence)</span><span class="sxs-lookup"><span data-stu-id="dcac4-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="dcac4-112">Le [Failure List Report](failure-list-report.md) (en cliquant sur la mesure Conférence)</span><span class="sxs-lookup"><span data-stu-id="dcac4-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="dcac4-113">Le [User Activity Report](call-diagnostic-reports-per-user.md) (en cliquant sur la mesure URI de la conférence)</span><span class="sxs-lookup"><span data-stu-id="dcac4-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="dcac4-114">Le rapport détaillé de conférence vous permet d’accéder au [Diagnostic Report](diagnostic-report.md) en cliquant sur la mesure Rapport de diagnostic (détaillé).</span><span class="sxs-lookup"><span data-stu-id="dcac4-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="dcac4-115">Filtres</span><span class="sxs-lookup"><span data-stu-id="dcac4-115">Filters</span></span>

<span data-ttu-id="dcac4-p102">Aucun. Vous ne pouvez pas filtrer sur le rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="dcac4-118">Mesures</span><span class="sxs-lookup"><span data-stu-id="dcac4-118">Metrics</span></span>

<span data-ttu-id="dcac4-119">Le tableau qui suit répertorie les informations fournies dans la section Informations de conférence du rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="dcac4-120">**Mesures des informations de conférence**</span><span class="sxs-lookup"><span data-stu-id="dcac4-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="dcac4-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="dcac4-121">**Name**</span></span>                 | <span data-ttu-id="dcac4-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="dcac4-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dcac4-123">**URI de la conférence**</span><span class="sxs-lookup"><span data-stu-id="dcac4-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="dcac4-p103">URI affectée à la conférence. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dcac4-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="dcac4-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="dcac4-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="dcac4-127">**Nom de domaine complet du pool**</span><span class="sxs-lookup"><span data-stu-id="dcac4-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="dcac4-128">Nom de domaine complet du pool de serveurs d’inscriptions ou serveur Edge impliqué dans une session.</span><span class="sxs-lookup"><span data-stu-id="dcac4-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="dcac4-129">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="dcac4-129">**Start time**</span></span> <br/>     | <span data-ttu-id="dcac4-130">Date et heure auxquelles la conférence a commencé.</span><span class="sxs-lookup"><span data-stu-id="dcac4-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="dcac4-131">**Organizer**</span><span class="sxs-lookup"><span data-stu-id="dcac4-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="dcac4-132">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="dcac4-133">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="dcac4-133">**End time**</span></span> <br/>       | <span data-ttu-id="dcac4-134">Date et heure auxquelles la conférence s’est terminée.</span><span class="sxs-lookup"><span data-stu-id="dcac4-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="dcac4-135">Le tableau qui suit répertorie les informations fournies dans la section Participation à la conférence du rapport détaille de conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="dcac4-136">**Mesures de participation à la conférence**</span><span class="sxs-lookup"><span data-stu-id="dcac4-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="dcac4-137">**Name**</span><span class="sxs-lookup"><span data-stu-id="dcac4-137">**Name**</span></span>|<span data-ttu-id="dcac4-138">**Description**</span><span class="sxs-lookup"><span data-stu-id="dcac4-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dcac4-139">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="dcac4-139">**User**</span></span> <br/> |<span data-ttu-id="dcac4-140">Adresse SIP de l’utilisateur qui a participé à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-141">**Role**</span><span class="sxs-lookup"><span data-stu-id="dcac4-141">**Role**</span></span> <br/> |<span data-ttu-id="dcac4-142">Rôle (par exemple, présentateur) joué par le participant à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="dcac4-143">**Connectivité**</span><span class="sxs-lookup"><span data-stu-id="dcac4-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="dcac4-144">Connectivité réseau (généralement Depuis interne ou Depuis externe) du participant.</span><span class="sxs-lookup"><span data-stu-id="dcac4-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="dcac4-145">**Heure d’arrivée**</span><span class="sxs-lookup"><span data-stu-id="dcac4-145">**Join time**</span></span> <br/> |<span data-ttu-id="dcac4-146">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-147">**Heure de départ**</span><span class="sxs-lookup"><span data-stu-id="dcac4-147">**Leave time**</span></span> <br/> |<span data-ttu-id="dcac4-148">Date et heure auxquelles le participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-149">**Agent utilisateur**</span><span class="sxs-lookup"><span data-stu-id="dcac4-149">**User agent**</span></span> <br/> |<span data-ttu-id="dcac4-150">Identificateur du logiciel utilisé par le point de terminaison du participant.</span><span class="sxs-lookup"><span data-stu-id="dcac4-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="dcac4-151">**Rapports de diagnostic**</span><span class="sxs-lookup"><span data-stu-id="dcac4-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="dcac4-p104">Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="dcac4-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="dcac4-154">Le tableau suivant répertorie les informations fournies dans la section Modalités de conférence du rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="dcac4-155">**Mesures des modalités de conférence**</span><span class="sxs-lookup"><span data-stu-id="dcac4-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="dcac4-156">**Name**</span><span class="sxs-lookup"><span data-stu-id="dcac4-156">**Name**</span></span>|<span data-ttu-id="dcac4-157">**Description**</span><span class="sxs-lookup"><span data-stu-id="dcac4-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dcac4-158">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="dcac4-158">**User**</span></span> <br/> |<span data-ttu-id="dcac4-159">Adresse SIP de l’utilisateur qui a participé à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-160">**Heure d’arrivée**</span><span class="sxs-lookup"><span data-stu-id="dcac4-160">**Join time**</span></span> <br/> |<span data-ttu-id="dcac4-161">Date et heure auxquelles le participant a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-162">**Heure de départ**</span><span class="sxs-lookup"><span data-stu-id="dcac4-162">**Leave time**</span></span> <br/> |<span data-ttu-id="dcac4-163">Date et heure auxquelles un participant a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-164">**URI du serveur de conférence**</span><span class="sxs-lookup"><span data-stu-id="dcac4-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="dcac4-165">URI du serveur de conférence utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="dcac4-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="dcac4-166">**Rapports de diagnostic**</span><span class="sxs-lookup"><span data-stu-id="dcac4-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="dcac4-p105">Fournit des informations de diagnostic et de résolution des problèmes, notamment les codes de réponse SIP, les en-têtes de diagnostic, les temps de connexion à la conférence et les ID de diagnostic des sessions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="dcac4-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


