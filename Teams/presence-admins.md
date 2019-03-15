---
title: Présence des utilisateurs dans Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Informations administrateurs doivent comprendre sur la présence dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75710a428273a38954de38ef5b6094d412aa3085
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640969"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="cc651-103">Présence des utilisateurs dans Teams</span><span class="sxs-lookup"><span data-stu-id="cc651-103">User Presence in Teams</span></span>

<span data-ttu-id="cc651-104">Fait partie d’un profil utilisateur dans Microsoft Teams (et dans Office 365), de présence et indique la disponibilité actuelle de l’utilisateur et l’état à d’autres utilisateurs dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="cc651-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="cc651-105">Par défaut, tout le monde dans votre organisation à l’aide des équipes permettre voir ou non les autres utilisateurs sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="cc651-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="cc651-106">États de présence dans les équipes</span><span class="sxs-lookup"><span data-stu-id="cc651-106">Presence states in Teams</span></span>

<span data-ttu-id="cc651-107">Les États de présence utilisateur disponibles dans les équipes sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="cc651-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="cc651-108">Configuré utilisateur</span><span class="sxs-lookup"><span data-stu-id="cc651-108">User configured</span></span>|<span data-ttu-id="cc651-109">Application configurée</span><span class="sxs-lookup"><span data-stu-id="cc651-109">App configured</span></span>|
|:--- |:---|
| ![Présence disponible](media/Presence_Available.png) <span data-ttu-id="cc651-111">Disponibles</span><span class="sxs-lookup"><span data-stu-id="cc651-111">Available</span></span>|![Présence disponible](media/Presence_Available.png) <span data-ttu-id="cc651-113">Disponibles</span><span class="sxs-lookup"><span data-stu-id="cc651-113">Available</span></span>|
|| ![oof disponible](media/Presence_Available_OOF.png) <span data-ttu-id="cc651-115">Disponible, absent</span><span class="sxs-lookup"><span data-stu-id="cc651-115">Available, Out of Office</span></span> |
|  ![Occupé (e)](media/Presence_Busy.png) <span data-ttu-id="cc651-117">Occupé (e)</span><span class="sxs-lookup"><span data-stu-id="cc651-117">Busy</span></span> |  ![Occupé (e)](media/Presence_Busy.png) <span data-ttu-id="cc651-119">Occupé (e)</span><span class="sxs-lookup"><span data-stu-id="cc651-119">Busy</span></span>  |
|| ![Occupé (e)](media/Presence_Busy.png) <span data-ttu-id="cc651-121">Dans un appel</span><span class="sxs-lookup"><span data-stu-id="cc651-121">In a call</span></span>|
|| ![Occupé (e)](media/Presence_Busy.png) <span data-ttu-id="cc651-123">Dans une réunion</span><span class="sxs-lookup"><span data-stu-id="cc651-123">In a meeting</span></span> |
|| ![occupé (e) absent du bureau](media/Presence_Busy_OOF.png) <span data-ttu-id="cc651-125">Dans un appel, absent</span><span class="sxs-lookup"><span data-stu-id="cc651-125">In a call, out of office</span></span>|
|  ![Ne pas déranger](media/Presence_DND.png) <span data-ttu-id="cc651-127">Ne pas déranger</span><span class="sxs-lookup"><span data-stu-id="cc651-127">Do not disturb</span></span> ||
|| ![Ne pas déranger](media/Presence_DND.png) <span data-ttu-id="cc651-129">Présentation</span><span class="sxs-lookup"><span data-stu-id="cc651-129">Presenting</span></span>|
| ![Absent (e)](media/Presence_Away.png) <span data-ttu-id="cc651-131">Absent (e)</span><span class="sxs-lookup"><span data-stu-id="cc651-131">Away</span></span>| ![Absent (e)](media/Presence_Away.png) <span data-ttu-id="cc651-133">Absent (e)</span><span class="sxs-lookup"><span data-stu-id="cc651-133">Away</span></span>|
|| <span data-ttu-id="cc651-134">![Absent (e)](media/Presence_Away.png) absent (e) vu dernière *heure*</span><span class="sxs-lookup"><span data-stu-id="cc651-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Absent (e)](media/Presence_Away.png) <span data-ttu-id="cc651-136">On revient</span><span class="sxs-lookup"><span data-stu-id="cc651-136">Be right back</span></span>| |
|| ![Absent (e)](media/Presence_Away.png)  <span data-ttu-id="cc651-138">En congé</span><span class="sxs-lookup"><span data-stu-id="cc651-138">Off Work</span></span>|
|| ![hors-ligne](media/Presence_Offline.png) <span data-ttu-id="cc651-140">hors-ligne</span><span class="sxs-lookup"><span data-stu-id="cc651-140">Offline</span></span> |
|| ![inconnu](media/Presence_Unknown.png) <span data-ttu-id="cc651-142">État inconnu</span><span class="sxs-lookup"><span data-stu-id="cc651-142">Status unknown</span></span>|
||![bloqué](media/Presence_Blocked.png) <span data-ttu-id="cc651-144">Bloqué</span><span class="sxs-lookup"><span data-stu-id="cc651-144">Blocked</span></span> |
|| ![Absent](media/Presence_OOF.png) <span data-ttu-id="cc651-146">Absent</span><span class="sxs-lookup"><span data-stu-id="cc651-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="cc651-147">Les utilisateurs peuvent définir manuellement leur statut de présence actuel à certaines options, et leur état obtient à tous les autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc651-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="cc651-148">Plus d’informations de présence utilisateur supplémentaires sont également automatiquement mis à jour en fonction d’activité de l’utilisateur (telles que disponible ou absent (e)), les États de calendrier de Outlook (comme dans une réunion) ou les États d’application équipes (dans un appel de la présentation), aux États qui sont mis en retrait dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cc651-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="cc651-149">Il existe un délai d’inactivité de 15 minutes, après lequel état de présence actuel de vos utilisateurs est réinitialisée à Absent (e).</span><span class="sxs-lookup"><span data-stu-id="cc651-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="cc651-150">Les utilisateurs peuvent spécifier qui peut adresser directement (contacter remplacement d’un paramètre de ne pas déranger).</span><span class="sxs-lookup"><span data-stu-id="cc651-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="cc651-151">Ces paramètres ne sont disponibles dans l’application.</span><span class="sxs-lookup"><span data-stu-id="cc651-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="cc651-152">Équipes n’est pas Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="cc651-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="cc651-153">Les paramètres d’administration suivants dans Skype pour les entreprises sont différentes dans les équipes :</span><span class="sxs-lookup"><span data-stu-id="cc651-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="cc651-154">Partage de présence est toujours activé dans les équipes pour les utilisateurs dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="cc651-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="cc651-155">Configuration de la confidentialité (déterminer qui peut voir présence) n’est pas disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="cc651-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="cc651-156">Présence partage avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="cc651-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="cc651-157">Leur liste des contacts (si elles avaient dans SfB) est visible sous **conversation > Contacts** ou **les appels > Contacts**.</span><span class="sxs-lookup"><span data-stu-id="cc651-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="cc651-158">Fonctionnalités client ne pas déranger et innovante sont toujours activées pour les utilisateurs dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="cc651-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="cc651-159">Calendrier (inclut les autres informations du calendrier & OOF) intégration est toujours activée pour les utilisateurs dans les équipes si intégré à Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc651-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="cc651-160">La *dernière détection* ou *Absent (e) depuis* (le cas dans un environnement double avec Skype pour les entreprises) indicateur est toujours activé pour les utilisateurs dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="cc651-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>
- <span data-ttu-id="cc651-161">Définir un statut de présence personnalisé n’est pas activé pour les utilisateurs dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="cc651-161">Setting a custom presence status is not enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cc651-162">La capacité d’un administrateur d’équipes pour personnaliser ces paramètres n’est pas actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="cc651-162">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="cc651-163">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="cc651-163">Coexistence with Skype for Business</span></span>

<span data-ttu-id="cc651-164">Pour plus d’informations sur le fonctionne de présence des équipes lors de la coexistence avec Skype pour les entreprises, consultez [Coexistence avec Skype pour les entreprises](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="cc651-164">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 