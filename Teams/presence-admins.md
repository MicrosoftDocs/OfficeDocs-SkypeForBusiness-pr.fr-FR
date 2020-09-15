---
title: Présence des utilisateurs dans Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Découvrez les États de présence dans Teams, ainsi qu les paramètres administratifs de la fonctionnalité Présence.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a944616fef0c3fd9821486a41025adf5f0fdbcc
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814573"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="04b09-103">Présence des utilisateurs dans Teams</span><span class="sxs-lookup"><span data-stu-id="04b09-103">User presence in Teams</span></span>

<span data-ttu-id="04b09-104">La présence fait partie du profil d’un utilisateur dans Microsoft Teams (et dans Microsoft 365 ou Office 365), qui indique la disponibilité et l’État actuels de l’utilisateur à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="04b09-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="04b09-105">Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="04b09-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="04b09-106">La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="04b09-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="04b09-107">Pour plus d’informations, voir [fonctionnalités d’équipe par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) .</span><span class="sxs-lookup"><span data-stu-id="04b09-107">See [Team features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) for more information.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="04b09-108">États de présence dans Teams</span><span class="sxs-lookup"><span data-stu-id="04b09-108">Presence states in Teams</span></span>

|<span data-ttu-id="04b09-109">L'utilisateur est configuré</span><span class="sxs-lookup"><span data-stu-id="04b09-109">User configured</span></span>|<span data-ttu-id="04b09-110">L'application est configurée</span><span class="sxs-lookup"><span data-stu-id="04b09-110">App configured</span></span>|
|:--- |:---|
| ![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) <span data-ttu-id="04b09-112">Disponible</span><span class="sxs-lookup"><span data-stu-id="04b09-112">Available</span></span>|![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) <span data-ttu-id="04b09-114">Disponible</span><span class="sxs-lookup"><span data-stu-id="04b09-114">Available</span></span>|
|| ![Une coche verte ouverte indique une Absence du bureau](media/Presence_Available_OOF.png) <span data-ttu-id="04b09-116">Disponible, Absent du bureau</span><span class="sxs-lookup"><span data-stu-id="04b09-116">Available, Out of Office</span></span> |
|  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) <span data-ttu-id="04b09-118">Occupé</span><span class="sxs-lookup"><span data-stu-id="04b09-118">Busy</span></span> |  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) <span data-ttu-id="04b09-120">Occupé</span><span class="sxs-lookup"><span data-stu-id="04b09-120">Busy</span></span>  |
|| ![Un cercle rouge plein indique Occupé au téléphone](media/Presence_Busy.png) <span data-ttu-id="04b09-122">Au téléphone</span><span class="sxs-lookup"><span data-stu-id="04b09-122">On a call</span></span>|
|| ![Un cercle rouge plein indique Occupé en réunion](media/Presence_Busy.png) <span data-ttu-id="04b09-124">En réunion</span><span class="sxs-lookup"><span data-stu-id="04b09-124">In a meeting</span></span> |
|| ![Un cercle rouge ouvert indique Occupé](media/Presence_Busy_OOF.png) <span data-ttu-id="04b09-126">Au téléphone, absent du bureau</span><span class="sxs-lookup"><span data-stu-id="04b09-126">On a call, out of office</span></span>|
|  ![Un cercle rouge avec une ligne blanche indique Ne pas déranger](media/Presence_DND.png) <span data-ttu-id="04b09-128">Ne pas déranger</span><span class="sxs-lookup"><span data-stu-id="04b09-128">Do not disturb</span></span> ||
|| ![Un cercle rouge avec une ligne blanche indique En cours de présentation](media/Presence_DND.png) <span data-ttu-id="04b09-130">En cours de présentation</span><span class="sxs-lookup"><span data-stu-id="04b09-130">Presenting</span></span>|
|| ![Un cercle rouge avec une ligne blanche indique un Travail individuel en cours](media/Presence_DND.png) <span data-ttu-id="04b09-132">Travail individuel en cours</span><span class="sxs-lookup"><span data-stu-id="04b09-132">Focusing</span></span>|
| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) <span data-ttu-id="04b09-134">Absent</span><span class="sxs-lookup"><span data-stu-id="04b09-134">Away</span></span>| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) <span data-ttu-id="04b09-136">Absent</span><span class="sxs-lookup"><span data-stu-id="04b09-136">Away</span></span>|
|| <span data-ttu-id="04b09-137">![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent, *heure* de Vu pour la dernière fois</span><span class="sxs-lookup"><span data-stu-id="04b09-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Une icône d’horloge jaune indique l’absence, de retour dans quelques minutes](media/Presence_Away.png) <span data-ttu-id="04b09-139">De retour dans quelques minutes</span><span class="sxs-lookup"><span data-stu-id="04b09-139">Be right back</span></span>| |
|| ![Une icône d’horloge jaune indique l’absence, congé](media/Presence_Away.png)  <span data-ttu-id="04b09-141">Congé</span><span class="sxs-lookup"><span data-stu-id="04b09-141">Off Work</span></span>|
|| ![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) <span data-ttu-id="04b09-143">Hors connexion</span><span class="sxs-lookup"><span data-stu-id="04b09-143">Offline</span></span> |
|| ![Un cercle gris ouvert indique un statut inconnu](media/Presence_Unknown.png) <span data-ttu-id="04b09-145">Statut inconnu</span><span class="sxs-lookup"><span data-stu-id="04b09-145">Status unknown</span></span>|
||![Un cercle rouge ouvert avec une ligne diagonale indique bloqué](media/Presence_Blocked.png) <span data-ttu-id="04b09-147">Bloqué</span><span class="sxs-lookup"><span data-stu-id="04b09-147">Blocked</span></span> |
|| ![Un cercle violet avec une flèche indique absent du bureau](media/Presence_OOF.png) <span data-ttu-id="04b09-149">Absent du bureau</span><span class="sxs-lookup"><span data-stu-id="04b09-149">Out of Office</span></span>|
|||

<span data-ttu-id="04b09-150">Les états de présence configurés par l’application sont basés sur l’activité des utilisateurs (Disponible, Absent), les états du calendrier Outlook (En réunion) ou l’état de l’application Teams (Au téléphone, En cours de présentation).</span><span class="sxs-lookup"><span data-stu-id="04b09-150">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="04b09-151">Notez que lorsque vous êtes en mode focus en fonction de votre calendrier, le focus peut être considéré comme ne pas déranger dans les autres produits.</span><span class="sxs-lookup"><span data-stu-id="04b09-151">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="04b09-152">Votre état de présence actuel passe à Absent lorsque vous verrouillez votre ordinateur ou lorsqu’il entre en mode d’inactivité ou de veille.</span><span class="sxs-lookup"><span data-stu-id="04b09-152">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="04b09-153">Sur les appareils mobiles, le statut de présence passe à Absent lorsque l’application Teams est en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="04b09-153">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="04b09-154">Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence.</span><span class="sxs-lookup"><span data-stu-id="04b09-154">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="04b09-155">Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne.</span><span class="sxs-lookup"><span data-stu-id="04b09-155">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="04b09-156">Si un utilisateur est défini sur Ne pas déranger, il reçoit les messages de conversation, mais les notifications de bannière ne s’affichent pas.</span><span class="sxs-lookup"><span data-stu-id="04b09-156">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="04b09-157">Les utilisateurs reçoivent des appels quel que soit l'état de présence, à l’exception de l’état Ne pas déranger dans lequel les appels entrants sont redirigés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="04b09-157">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="04b09-158">Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="04b09-158">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="04b09-159">Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="04b09-159">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="04b09-160">Les contacts disposant d’un accès prioritaire peuvent contacter l’utilisateur, même lorsque celui-ci est défini sur Ne pas déranger.</span><span class="sxs-lookup"><span data-stu-id="04b09-160">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="04b09-161">Paramètres d’administrateur dans Teams comparé à ceux de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="04b09-161">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="04b09-162">Les paramètres d’administration suivants de Skype Entreprise sont différents de ceux dans Teams :</span><span class="sxs-lookup"><span data-stu-id="04b09-162">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="04b09-163">Le partage de présence est toujours activé dans Teams pour les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="04b09-163">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="04b09-164">La configuration de la confidentialité (dans laquelle vous définissez les personnes pouvant voir la présence) n’est pas disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="04b09-164">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="04b09-165">Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Teams.</span><span class="sxs-lookup"><span data-stu-id="04b09-165">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="04b09-166">Leur liste de contacts (s'ils en avaient une dans Skype Entreprise) est visible sous **Conversation > Contacts** ou sous **Appels > Contacts**.</span><span class="sxs-lookup"><span data-stu-id="04b09-166">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="04b09-167">Les fonctionnalités du client Ne sont pas déranger et Autorisé à appeler sont toujours activées pour les utilisateurs Teams.</span><span class="sxs-lookup"><span data-stu-id="04b09-167">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="04b09-168">L'intégration du calendrier (comprend les informations d’absence du bureau et d’autres informations de calendrier) est toujours activée pour les utilisateurs lorsque Teams est intégrée à Outlook.</span><span class="sxs-lookup"><span data-stu-id="04b09-168">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="04b09-169">L'indicateur *Vu pour la dernière fois* ou *Absent depuis* est toujours activé pour les utilisateurs Teams si l’organisation utilise également Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="04b09-169">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="04b09-170">La possibilité pour un administrateur Teams de personnaliser ces paramètres n’est pas prise en charge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="04b09-170">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="04b09-171">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="04b09-171">Coexistence with Skype for Business</span></span>

<span data-ttu-id="04b09-172">Pour plus d’informations sur les fonctions de présence Teams lorsque votre organisation utilise également Skype Entreprise, voir [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="04b09-172">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
