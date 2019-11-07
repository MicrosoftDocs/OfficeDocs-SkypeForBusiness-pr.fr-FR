---
title: Présence des utilisateurs dans Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informations pour les administrateurs concernant la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b829fbffa728d3449ba19466d0a2cb85f266c9c2
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010597"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="3573c-103">Présence des utilisateurs dans Teams</span><span class="sxs-lookup"><span data-stu-id="3573c-103">User presence in Teams</span></span>

<span data-ttu-id="3573c-104">Les informations de présence font partie du profil d’un utilisateur de Microsoft Teams (et dans l’ensemble d’Office 365), qui indique la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3573c-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="3573c-105">Par défaut, tous les membres de votre organisation utilisant teams peuvent voir (presque en temps réel) si d’autres utilisateurs sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="3573c-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3573c-106">Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office.</span><span class="sxs-lookup"><span data-stu-id="3573c-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="3573c-107">La présence fonctionne correctement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="3573c-107">Presence works fine in Teams.</span></span> <span data-ttu-id="3573c-108">Solution : pour voir la présence dans Outlook (et les autres applications Office), Skype entreprise doit être installé, même si vous exécutez teams en mode **équipes uniquement** .</span><span class="sxs-lookup"><span data-stu-id="3573c-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="3573c-109">Microsoft est courant du problème et travaille activement au développement d’un correctif.</span><span class="sxs-lookup"><span data-stu-id="3573c-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="3573c-110">La présence d’équipes dans Outlook est prise en charge sur l’application de bureau Outlook 2013 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="3573c-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="3573c-111">États de présence dans teams</span><span class="sxs-lookup"><span data-stu-id="3573c-111">Presence states in Teams</span></span>

<span data-ttu-id="3573c-112">Les statuts de présence des utilisateurs disponibles dans teams sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3573c-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="3573c-113">Utilisateur configuré</span><span class="sxs-lookup"><span data-stu-id="3573c-113">User configured</span></span>|<span data-ttu-id="3573c-114">Application configurée</span><span class="sxs-lookup"><span data-stu-id="3573c-114">App configured</span></span>|
|:--- |:---|
| ![Coche verte unie, indiquant présence disponible](media/Presence_Available.png) <span data-ttu-id="3573c-116">Disponibles</span><span class="sxs-lookup"><span data-stu-id="3573c-116">Available</span></span>|![Coche verte unie, indiquant présence disponible](media/Presence_Available.png) <span data-ttu-id="3573c-118">Disponibles</span><span class="sxs-lookup"><span data-stu-id="3573c-118">Available</span></span>|
|| ![Ouvrir la coche verte indique qu’il est disponible](media/Presence_Available_OOF.png) <span data-ttu-id="3573c-120">Disponible, absent (e) du Bureau</span><span class="sxs-lookup"><span data-stu-id="3573c-120">Available, Out of Office</span></span> |
|  ![Cercle rouge Uni, indiquant occupé](media/Presence_Busy.png) <span data-ttu-id="3573c-122">Très</span><span class="sxs-lookup"><span data-stu-id="3573c-122">Busy</span></span> |  ![Cercle rouge Uni, indiquant occupé](media/Presence_Busy.png) <span data-ttu-id="3573c-124">Très</span><span class="sxs-lookup"><span data-stu-id="3573c-124">Busy</span></span>  |
|| ![Cercle rouge Uni, indiquant bien occupé lors d’un appel](media/Presence_Busy.png) <span data-ttu-id="3573c-126">En communication</span><span class="sxs-lookup"><span data-stu-id="3573c-126">In a call</span></span>|
|| ![Cercle rouge Uni, indiquant bien occupé lors d’une réunion](media/Presence_Busy.png) <span data-ttu-id="3573c-128">En réunion</span><span class="sxs-lookup"><span data-stu-id="3573c-128">In a meeting</span></span> |
|| ![Ouvrir un cercle rouge, indique occupé](media/Presence_Busy_OOF.png) <span data-ttu-id="3573c-130">En communication, absent (e) du Bureau</span><span class="sxs-lookup"><span data-stu-id="3573c-130">In a call, out of office</span></span>|
|  ![Cercle rouge avec une ligne blanche indiquant ne pas déranger](media/Presence_DND.png) <span data-ttu-id="3573c-132">Ne pas déranger</span><span class="sxs-lookup"><span data-stu-id="3573c-132">Do not disturb</span></span> ||
|| ![Cercle rouge avec une ligne blanche indiquant une présentation](media/Presence_DND.png) <span data-ttu-id="3573c-134">Présente</span><span class="sxs-lookup"><span data-stu-id="3573c-134">Presenting</span></span>|
|| ![Cercle rouge avec ligne blanche indiquant le focus](media/Presence_DND.png) <span data-ttu-id="3573c-136">Focalis</span><span class="sxs-lookup"><span data-stu-id="3573c-136">Focusing</span></span>|
| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) <span data-ttu-id="3573c-138">Disparaître</span><span class="sxs-lookup"><span data-stu-id="3573c-138">Away</span></span>| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) <span data-ttu-id="3573c-140">Disparaître</span><span class="sxs-lookup"><span data-stu-id="3573c-140">Away</span></span>|
|| <span data-ttu-id="3573c-141">![Icône d’horloge jaune indiquant](media/Presence_Away.png) l’heure de la dernière *connexion* affichée</span><span class="sxs-lookup"><span data-stu-id="3573c-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icône d’horloge jaune, indique absent, revenir en arrière](media/Presence_Away.png) <span data-ttu-id="3573c-143">On arrive</span><span class="sxs-lookup"><span data-stu-id="3573c-143">Be right back</span></span>| |
|| ![Icône d’horloge jaune, indiquant qu’il n’est pas opérationnel](media/Presence_Away.png)  <span data-ttu-id="3573c-145">Sur le Bureau</span><span class="sxs-lookup"><span data-stu-id="3573c-145">Off Work</span></span>|
|| ![Cercle gris avec x, indiquant hors ligne](media/Presence_Offline.png) <span data-ttu-id="3573c-147">Mise</span><span class="sxs-lookup"><span data-stu-id="3573c-147">Offline</span></span> |
|| ![Ouverture d’un cercle gris, indiquant le statut inconnu](media/Presence_Unknown.png) <span data-ttu-id="3573c-149">État inconnu</span><span class="sxs-lookup"><span data-stu-id="3573c-149">Status unknown</span></span>|
||![Cercle rouge avec ligne diagonale indiquant bloqué](media/Presence_Blocked.png) <span data-ttu-id="3573c-151">Bloqué</span><span class="sxs-lookup"><span data-stu-id="3573c-151">Blocked</span></span> |
|| ![Cercle violet avec flèche, indiquant qu’il n’est pas du tout le Bureau](media/Presence_OOF.png) <span data-ttu-id="3573c-153">Absent (e) du Bureau</span><span class="sxs-lookup"><span data-stu-id="3573c-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="3573c-154">Les utilisateurs peuvent définir manuellement leur état de présence actuel sur certaines options, et leur état est reflété par tous les autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3573c-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="3573c-155">Des informations supplémentaires sur la présence d’un utilisateur sont également mises à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="3573c-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="3573c-156">Les modifications dépendent de l’activité des utilisateurs (disponible, absent (e), des États du calendrier Outlook (dans une réunion) ou des États des applications Teams (en cours de présentation) pour les États en retrait dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3573c-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> 

<span data-ttu-id="3573c-157">Il y a un délai d’inactivité de 15 minutes, après lequel l’état de présence actuel est remis à absent (e).</span><span class="sxs-lookup"><span data-stu-id="3573c-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="3573c-158">Les utilisateurs peuvent spécifier qui peut se bloquer (c’est-à-dire les contacter malgré un État ne pas déranger).</span><span class="sxs-lookup"><span data-stu-id="3573c-158">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="3573c-159">Ces paramètres sont disponibles dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="3573c-159">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="3573c-160">Paramètres d’administration dans teams par rapport à Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="3573c-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="3573c-161">Les paramètres d’administration suivants Skype entreprise sont différents dans teams :</span><span class="sxs-lookup"><span data-stu-id="3573c-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="3573c-162">Dans Teams, le partage de présence est toujours activé pour les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3573c-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="3573c-163">Les informations sur la confidentialité (dans laquelle vous définissez qui peut voir la présence) ne sont pas disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="3573c-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="3573c-164">Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3573c-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="3573c-165">La liste de contacts (s’il en existe une dans Skype entreprise) est visible sous **discussions > contacts** ou sous **appels > contacts**.</span><span class="sxs-lookup"><span data-stu-id="3573c-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="3573c-166">Le client ne pas déranger et les fonctionnalités d’innovation sont toujours activées pour les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3573c-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="3573c-167">Calendrier (inclut les informations d’absence du bureau et d’autres informations de calendrier) l’intégration est toujours activée pour les utilisateurs lorsque teams est intégré à Outlook.</span><span class="sxs-lookup"><span data-stu-id="3573c-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="3573c-168">Le *dernier vu* ou *absent (e* ), car l’indicateur est toujours activé pour les utilisateurs en équipe si l’organisation utilise également Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="3573c-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="3573c-169">La capacité d’un administrateur d’équipes à personnaliser ces paramètres n’est pas actuellement prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3573c-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="3573c-170">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="3573c-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="3573c-171">Pour plus d’informations sur la façon dont votre organisation utilise également Skype entreprise, voir [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="3573c-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
