---
title: Présence de l’utilisateur dans teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Les administrateurs d’informations doivent comprendre la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30b50972dd53300905f580c51a410d699ebb1bff
ms.sourcegitcommit: 21a5550e3c0feafaa57dbcdc428ed13eedd276b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/06/2019
ms.locfileid: "34748442"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="cd879-103">Présence de l’utilisateur dans teams</span><span class="sxs-lookup"><span data-stu-id="cd879-103">User presence in Teams</span></span>

<span data-ttu-id="cd879-104">Les informations de présence font partie du profil d’un utilisateur dans Microsoft Teams (et dans Office 365), et indiquent la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="cd879-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="cd879-105">Par défaut, tous les membres de votre organisation qui utilisent teams peuvent voir-en presque en temps réel, qu’ils soient ou non disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="cd879-105">By default, anyone in your organization using Teams can see - in nearly real time - whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="cd879-106">États de présence dans teams</span><span class="sxs-lookup"><span data-stu-id="cd879-106">Presence states in Teams</span></span>

<span data-ttu-id="cd879-107">Les statuts de présence des utilisateurs disponibles dans teams sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="cd879-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="cd879-108">Utilisateur configuré</span><span class="sxs-lookup"><span data-stu-id="cd879-108">User configured</span></span>|<span data-ttu-id="cd879-109">Application configurée</span><span class="sxs-lookup"><span data-stu-id="cd879-109">App configured</span></span>|
|:--- |:---|
| ![Marque verte CHEK, indiquant la présence disponible](media/Presence_Available.png) <span data-ttu-id="cd879-111">Disponibles</span><span class="sxs-lookup"><span data-stu-id="cd879-111">Available</span></span>|![Marque verte CHEK, indiquant la présence disponible](media/Presence_Available.png) <span data-ttu-id="cd879-113">Disponibles</span><span class="sxs-lookup"><span data-stu-id="cd879-113">Available</span></span>|
|| ![Ouvrir la marque verte CHEK, indiquant que le OOF est disponible](media/Presence_Available_OOF.png) <span data-ttu-id="cd879-115">Disponible, absent (e) du Bureau</span><span class="sxs-lookup"><span data-stu-id="cd879-115">Available, Out of Office</span></span> |
|  ![Cercle rouge continu indiquant Busy](media/Presence_Busy.png) <span data-ttu-id="cd879-117">Très</span><span class="sxs-lookup"><span data-stu-id="cd879-117">Busy</span></span> |  ![Cercle rouge continu indiquant Busy](media/Presence_Busy.png) <span data-ttu-id="cd879-119">Très</span><span class="sxs-lookup"><span data-stu-id="cd879-119">Busy</span></span>  |
|| ![Cercle rouge continu indiquant qu’il est occupé pendant un appel](media/Presence_Busy.png) <span data-ttu-id="cd879-121">En communication</span><span class="sxs-lookup"><span data-stu-id="cd879-121">In a call</span></span>|
|| ![Cercle rouge continu indiquant qu’il est occupé dans une réunion](media/Presence_Busy.png) <span data-ttu-id="cd879-123">En réunion</span><span class="sxs-lookup"><span data-stu-id="cd879-123">In a meeting</span></span> |
|| ![Cercle rouge pour indiquer qu’il est occupé](media/Presence_Busy_OOF.png) <span data-ttu-id="cd879-125">En communication, absent (e) du Bureau</span><span class="sxs-lookup"><span data-stu-id="cd879-125">In a call, out of office</span></span>|
|  ![Cercle rouge avec ligne blanche indiquant ne pas déranger](media/Presence_DND.png) <span data-ttu-id="cd879-127">Ne pas déranger</span><span class="sxs-lookup"><span data-stu-id="cd879-127">Do not disturb</span></span> ||
|| ![Cercle rouge avec une ligne blanche indiquant une présentation](media/Presence_DND.png) <span data-ttu-id="cd879-129">Présente</span><span class="sxs-lookup"><span data-stu-id="cd879-129">Presenting</span></span>|
| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) <span data-ttu-id="cd879-131">Disparaître</span><span class="sxs-lookup"><span data-stu-id="cd879-131">Away</span></span>| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) <span data-ttu-id="cd879-133">Disparaître</span><span class="sxs-lookup"><span data-stu-id="cd879-133">Away</span></span>|
|| <span data-ttu-id="cd879-134">![Icône d’horloge jaune indiquant](media/Presence_Away.png) l' *heure* de la dernière vue</span><span class="sxs-lookup"><span data-stu-id="cd879-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icône d’horloge jaune, indiquant qu’il n’y a plus de retour](media/Presence_Away.png) <span data-ttu-id="cd879-136">On arrive</span><span class="sxs-lookup"><span data-stu-id="cd879-136">Be right back</span></span>| |
|| ![Icône d’horloge jaune, indiquant qu’il n’est pas opérationnel](media/Presence_Away.png)  <span data-ttu-id="cd879-138">Sur le Bureau</span><span class="sxs-lookup"><span data-stu-id="cd879-138">Off Work</span></span>|
|| ![Cercle gris avec x, indiquant hors ligne](media/Presence_Offline.png) <span data-ttu-id="cd879-140">Mise</span><span class="sxs-lookup"><span data-stu-id="cd879-140">Offline</span></span> |
|| ![Cercle gris ouvert indiquant le statut inconnu](media/Presence_Unknown.png) <span data-ttu-id="cd879-142">État inconnu</span><span class="sxs-lookup"><span data-stu-id="cd879-142">Status unknown</span></span>|
||![Cercle rouge avec ligne diagonale indiquant le blocage](media/Presence_Blocked.png) <span data-ttu-id="cd879-144">Bloqué</span><span class="sxs-lookup"><span data-stu-id="cd879-144">Blocked</span></span> |
|| ![Cercle violet avec flèche, indiquant qu’il n’est pas du Bureau](media/Presence_OOF.png) <span data-ttu-id="cd879-146">Absent (e) du Bureau</span><span class="sxs-lookup"><span data-stu-id="cd879-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="cd879-147">Les utilisateurs peuvent définir manuellement leur état de présence actuel sur certaines options, et leur état est reflété par tous les autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cd879-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="cd879-148">Des informations supplémentaires sur la présence d’un utilisateur sont également mises à jour automatiquement en fonction de l’activité des utilisateurs (par exemple, disponible ou absent), des États du calendrier Outlook (par exemple, en réunion) ou des États des applications Teams (en cas de présentation) aux États en retrait dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cd879-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="cd879-149">Il y a un délai d’inactivité de 15 minutes, après quoi l’état de présence actuel de vos utilisateurs sera restauré en absent (e).</span><span class="sxs-lookup"><span data-stu-id="cd879-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="cd879-150">Les utilisateurs peuvent spécifier qui peut vous répartir (ils remplacent le paramètre ne pas déranger).</span><span class="sxs-lookup"><span data-stu-id="cd879-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="cd879-151">Ces paramètres sont disponibles dans l’application.</span><span class="sxs-lookup"><span data-stu-id="cd879-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="cd879-152">Teams n’est pas Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="cd879-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="cd879-153">Les paramètres d’administration suivants dans Skype entreprise sont différents dans teams:</span><span class="sxs-lookup"><span data-stu-id="cd879-153">The following admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="cd879-154">Le partage de présence est toujours activé dans teams pour les utilisateurs au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="cd879-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="cd879-155">La configuration de la vie privée (en choisissant qui peut voir la présence) n’est pas disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cd879-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="cd879-156">Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd879-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="cd879-157">La liste de contacts (s’il en existe une dans Skype entreprise) est visible sous **discussions > contacts** ou sous **appels > contacts**.</span><span class="sxs-lookup"><span data-stu-id="cd879-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="cd879-158">Le client ne pas déranger et les fonctionnalités d’innovation sont toujours activées pour les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd879-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="cd879-159">Calendrier (y compris les informations d’absence du bureau et d’autres informations de calendrier) l’intégration est toujours activée pour les utilisateurs en équipe, si ils sont intégrés à Outlook.</span><span class="sxs-lookup"><span data-stu-id="cd879-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="cd879-160">Le *dernier vu* ou *absent depuis* l’indicateur (dans le cas d’un environnement double avec Skype entreprise) est toujours activé pour les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd879-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cd879-161">La capacité d’un administrateur d’équipes à personnaliser ces paramètres n’est pas actuellement prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cd879-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="cd879-162">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="cd879-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="cd879-163">Pour plus d’informations sur la façon dont la présence des équipes dans Skype entreprise, voir [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="cd879-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
