---
title: Présence des utilisateurs dans Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informations destinées aux administrateurs sur la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab24c6ee27f3e99a30a18af82f0a26196a049528
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510773"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="c89c5-103">Présence des utilisateurs dans Teams</span><span class="sxs-lookup"><span data-stu-id="c89c5-103">User presence in Teams</span></span>

<span data-ttu-id="c89c5-104">La présence fait partie du profil d’un utilisateur dans Microsoft Teams (et dans Office 365) et elle indique aux autres utilisateurs sa disponibilité et son statut actuels.</span><span class="sxs-lookup"><span data-stu-id="c89c5-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="c89c5-105">Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="c89c5-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="c89c5-106">La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="c89c5-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="c89c5-107">États de présence dans Teams</span><span class="sxs-lookup"><span data-stu-id="c89c5-107">Presence states in Teams</span></span>

|<span data-ttu-id="c89c5-108">L'utilisateur est configuré</span><span class="sxs-lookup"><span data-stu-id="c89c5-108">User configured</span></span>|<span data-ttu-id="c89c5-109">L'application est configurée</span><span class="sxs-lookup"><span data-stu-id="c89c5-109">App configured</span></span>|
|:--- |:---|
| ![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) <span data-ttu-id="c89c5-111">Disponible</span><span class="sxs-lookup"><span data-stu-id="c89c5-111">Available</span></span>|![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) <span data-ttu-id="c89c5-113">Disponible</span><span class="sxs-lookup"><span data-stu-id="c89c5-113">Available</span></span>|
|| ![Une coche verte ouverte indique une Absence du bureau](media/Presence_Available_OOF.png) <span data-ttu-id="c89c5-115">Disponible, Absent du bureau</span><span class="sxs-lookup"><span data-stu-id="c89c5-115">Available, Out of Office</span></span> |
|  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) <span data-ttu-id="c89c5-117">Occupé</span><span class="sxs-lookup"><span data-stu-id="c89c5-117">Busy</span></span> |  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) <span data-ttu-id="c89c5-119">Occupé</span><span class="sxs-lookup"><span data-stu-id="c89c5-119">Busy</span></span>  |
|| ![Un cercle rouge plein indique Occupé au téléphone](media/Presence_Busy.png) <span data-ttu-id="c89c5-121">Au téléphone</span><span class="sxs-lookup"><span data-stu-id="c89c5-121">On a call</span></span>|
|| ![Un cercle rouge plein indique Occupé en réunion](media/Presence_Busy.png) <span data-ttu-id="c89c5-123">En réunion</span><span class="sxs-lookup"><span data-stu-id="c89c5-123">In a meeting</span></span> |
|| ![Un cercle rouge ouvert indique Occupé](media/Presence_Busy_OOF.png) <span data-ttu-id="c89c5-125">Au téléphone, absent du bureau</span><span class="sxs-lookup"><span data-stu-id="c89c5-125">On a call, out of office</span></span>|
|  ![Un cercle rouge avec une ligne blanche indique Ne pas déranger](media/Presence_DND.png) <span data-ttu-id="c89c5-127">Ne pas déranger</span><span class="sxs-lookup"><span data-stu-id="c89c5-127">Do not disturb</span></span> ||
|| ![Un cercle rouge avec une ligne blanche indique En cours de présentation](media/Presence_DND.png) <span data-ttu-id="c89c5-129">En cours de présentation</span><span class="sxs-lookup"><span data-stu-id="c89c5-129">Presenting</span></span>|
|| ![Un cercle rouge avec une ligne blanche indique un Travail individuel en cours](media/Presence_DND.png) <span data-ttu-id="c89c5-131">Travail individuel en cours</span><span class="sxs-lookup"><span data-stu-id="c89c5-131">Focusing</span></span>|
| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) <span data-ttu-id="c89c5-133">Absent</span><span class="sxs-lookup"><span data-stu-id="c89c5-133">Away</span></span>| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) <span data-ttu-id="c89c5-135">Absent</span><span class="sxs-lookup"><span data-stu-id="c89c5-135">Away</span></span>|
|| <span data-ttu-id="c89c5-136">![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent, *heure* de Vu pour la dernière fois</span><span class="sxs-lookup"><span data-stu-id="c89c5-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Une icône d’horloge jaune indique l’absence, de retour dans quelques minutes](media/Presence_Away.png) <span data-ttu-id="c89c5-138">De retour dans quelques minutes</span><span class="sxs-lookup"><span data-stu-id="c89c5-138">Be right back</span></span>| |
|| ![Une icône d’horloge jaune indique l’absence, congé](media/Presence_Away.png)  <span data-ttu-id="c89c5-140">Congé</span><span class="sxs-lookup"><span data-stu-id="c89c5-140">Off Work</span></span>|
|| ![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) <span data-ttu-id="c89c5-142">Hors connexion</span><span class="sxs-lookup"><span data-stu-id="c89c5-142">Offline</span></span> |
|| ![Un cercle gris ouvert indique un statut inconnu](media/Presence_Unknown.png) <span data-ttu-id="c89c5-144">Statut inconnu</span><span class="sxs-lookup"><span data-stu-id="c89c5-144">Status unknown</span></span>|
||![Un cercle rouge ouvert avec une ligne diagonale indique bloqué](media/Presence_Blocked.png) <span data-ttu-id="c89c5-146">Bloqué</span><span class="sxs-lookup"><span data-stu-id="c89c5-146">Blocked</span></span> |
|| ![Un cercle violet avec une flèche indique absent du bureau](media/Presence_OOF.png) <span data-ttu-id="c89c5-148">Absent du bureau</span><span class="sxs-lookup"><span data-stu-id="c89c5-148">Out of Office</span></span>|
|||

<span data-ttu-id="c89c5-149">Les états de présence configurés par l’application sont basés sur l’activité des utilisateurs (Disponible, Absent), les états du calendrier Outlook (En réunion) ou l’état de l’application Teams (Au téléphone, En cours de présentation).</span><span class="sxs-lookup"><span data-stu-id="c89c5-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="c89c5-150">Votre état de présence actuel passe à Absent lorsque vous verrouillez votre ordinateur ou lorsqu’il entre en mode d’inactivité ou de veille.</span><span class="sxs-lookup"><span data-stu-id="c89c5-150">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="c89c5-151">Sur les appareils mobiles, le statut de présence passe à Absent lorsque l’application Teams est en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="c89c5-151">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="c89c5-152">Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence.</span><span class="sxs-lookup"><span data-stu-id="c89c5-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="c89c5-153">Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne.</span><span class="sxs-lookup"><span data-stu-id="c89c5-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="c89c5-154">Si un utilisateur est défini sur Ne pas déranger, il reçoit les messages de conversation, mais les notifications de bannière ne s’affichent pas.</span><span class="sxs-lookup"><span data-stu-id="c89c5-154">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="c89c5-155">Les utilisateurs reçoivent des appels quel que soit l'état de présence, à l’exception de l’état Ne pas déranger dans lequel les appels entrants sont redirigés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c89c5-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="c89c5-156">Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="c89c5-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="c89c5-157">Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c89c5-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="c89c5-158">Les contacts disposant d’un accès prioritaire peuvent contacter l’utilisateur, même lorsque celui-ci est défini sur Ne pas déranger.</span><span class="sxs-lookup"><span data-stu-id="c89c5-158">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="c89c5-159">Paramètres d’administrateur dans Teams comparé à ceux de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c89c5-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="c89c5-160">Les paramètres d’administration suivants de Skype Entreprise sont différents de ceux dans Teams :</span><span class="sxs-lookup"><span data-stu-id="c89c5-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="c89c5-161">Le partage de présence est toujours activé dans Teams pour les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c89c5-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="c89c5-162">La configuration de la confidentialité (dans laquelle vous définissez les personnes pouvant voir la présence) n’est pas disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c89c5-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="c89c5-163">Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Teams.</span><span class="sxs-lookup"><span data-stu-id="c89c5-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="c89c5-164">Leur liste de contacts (s'ils en avaient une dans Skype Entreprise) est visible sous **Conversation > Contacts** ou sous **Appels > Contacts**.</span><span class="sxs-lookup"><span data-stu-id="c89c5-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="c89c5-165">Les fonctionnalités du client Ne sont pas déranger et Autorisé à appeler sont toujours activées pour les utilisateurs Teams.</span><span class="sxs-lookup"><span data-stu-id="c89c5-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="c89c5-166">L'intégration du calendrier (comprend les informations d’absence du bureau et d’autres informations de calendrier) est toujours activée pour les utilisateurs lorsque Teams est intégrée à Outlook.</span><span class="sxs-lookup"><span data-stu-id="c89c5-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="c89c5-167">L'indicateur *Vu pour la dernière fois* ou *Absent depuis* est toujours activé pour les utilisateurs Teams si l’organisation utilise également Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c89c5-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="c89c5-168">La possibilité pour un administrateur Teams de personnaliser ces paramètres n’est pas prise en charge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="c89c5-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="c89c5-169">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c89c5-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="c89c5-170">Pour plus d’informations sur les fonctions de présence Teams lorsque votre organisation utilise également Skype Entreprise, voir [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="c89c5-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
