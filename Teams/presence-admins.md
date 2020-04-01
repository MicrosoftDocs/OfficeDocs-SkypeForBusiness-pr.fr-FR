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
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096969"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="20547-103">Présence des utilisateurs dans Teams</span><span class="sxs-lookup"><span data-stu-id="20547-103">User presence in Teams</span></span>

<span data-ttu-id="20547-104">Les informations de présence font partie du profil d’un utilisateur de Microsoft Teams (et dans l’ensemble d’Office 365), qui indique la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="20547-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="20547-105">Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="20547-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20547-106">Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office.</span><span class="sxs-lookup"><span data-stu-id="20547-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="20547-107">La présence fonctionne correctement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="20547-107">Presence works fine in Teams.</span></span> <span data-ttu-id="20547-108">Solution de contournement :pour afficher la présence dans Outlook (et d'autres applications Office), Skype Entreprise doit être installé, même si vous exécutez Teams en mode **Teams uniquement**.</span><span class="sxs-lookup"><span data-stu-id="20547-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="20547-109">Microsoft est sensibilisé à ce problème et travaille activement au développement d’un correctif.</span><span class="sxs-lookup"><span data-stu-id="20547-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="20547-110">La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="20547-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="20547-111">États de présence dans Teams</span><span class="sxs-lookup"><span data-stu-id="20547-111">Presence states in Teams</span></span>

|<span data-ttu-id="20547-112">L'utilisateur est configuré</span><span class="sxs-lookup"><span data-stu-id="20547-112">User configured</span></span>|<span data-ttu-id="20547-113">L'application est configurée</span><span class="sxs-lookup"><span data-stu-id="20547-113">App configured</span></span>|
|:--- |:---|
| ![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) <span data-ttu-id="20547-115">Disponible</span><span class="sxs-lookup"><span data-stu-id="20547-115">Available</span></span>|![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) <span data-ttu-id="20547-117">Disponible</span><span class="sxs-lookup"><span data-stu-id="20547-117">Available</span></span>|
|| ![Une coche verte ouverte indique une Absence du bureau](media/Presence_Available_OOF.png) <span data-ttu-id="20547-119">Disponible, Absent du bureau</span><span class="sxs-lookup"><span data-stu-id="20547-119">Available, Out of Office</span></span> |
|  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) <span data-ttu-id="20547-121">Occupé</span><span class="sxs-lookup"><span data-stu-id="20547-121">Busy</span></span> |  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) <span data-ttu-id="20547-123">Occupé</span><span class="sxs-lookup"><span data-stu-id="20547-123">Busy</span></span>  |
|| ![Un cercle rouge plein indique Occupé au téléphone](media/Presence_Busy.png) <span data-ttu-id="20547-125">Au téléphone</span><span class="sxs-lookup"><span data-stu-id="20547-125">On a call</span></span>|
|| ![Un cercle rouge plein indique Occupé en réunion](media/Presence_Busy.png) <span data-ttu-id="20547-127">En réunion</span><span class="sxs-lookup"><span data-stu-id="20547-127">In a meeting</span></span> |
|| ![Un cercle rouge ouvert indique Occupé](media/Presence_Busy_OOF.png) <span data-ttu-id="20547-129">Au téléphone, absent du bureau</span><span class="sxs-lookup"><span data-stu-id="20547-129">On a call, out of office</span></span>|
|  ![Un cercle rouge avec une ligne blanche indique Ne pas déranger](media/Presence_DND.png) <span data-ttu-id="20547-131">Ne pas déranger</span><span class="sxs-lookup"><span data-stu-id="20547-131">Do not disturb</span></span> ||
|| ![Un cercle rouge avec une ligne blanche indique En cours de présentation](media/Presence_DND.png) <span data-ttu-id="20547-133">En cours de présentation</span><span class="sxs-lookup"><span data-stu-id="20547-133">Presenting</span></span>|
|| ![Un cercle rouge avec une ligne blanche indique un Travail individuel en cours](media/Presence_DND.png) <span data-ttu-id="20547-135">Travail individuel en cours</span><span class="sxs-lookup"><span data-stu-id="20547-135">Focusing</span></span>|
| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) <span data-ttu-id="20547-137">Absent</span><span class="sxs-lookup"><span data-stu-id="20547-137">Away</span></span>| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) <span data-ttu-id="20547-139">Absent</span><span class="sxs-lookup"><span data-stu-id="20547-139">Away</span></span>|
|| <span data-ttu-id="20547-140">![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent, *heure* de Vu pour la dernière fois</span><span class="sxs-lookup"><span data-stu-id="20547-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Une icône d’horloge jaune indique l’absence, de retour dans quelques minutes](media/Presence_Away.png) <span data-ttu-id="20547-142">De retour dans quelques minutes</span><span class="sxs-lookup"><span data-stu-id="20547-142">Be right back</span></span>| |
|| ![Une icône d’horloge jaune indique l’absence, congé](media/Presence_Away.png)  <span data-ttu-id="20547-144">Congé</span><span class="sxs-lookup"><span data-stu-id="20547-144">Off Work</span></span>|
|| ![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) <span data-ttu-id="20547-146">Hors connexion</span><span class="sxs-lookup"><span data-stu-id="20547-146">Offline</span></span> |
|| ![Un cercle gris ouvert indique un statut inconnu](media/Presence_Unknown.png) <span data-ttu-id="20547-148">Statut inconnu</span><span class="sxs-lookup"><span data-stu-id="20547-148">Status unknown</span></span>|
||![Un cercle rouge ouvert avec une ligne diagonale indique bloqué](media/Presence_Blocked.png) <span data-ttu-id="20547-150">Bloqué</span><span class="sxs-lookup"><span data-stu-id="20547-150">Blocked</span></span> |
|| ![Un cercle violet avec une flèche indique absent du bureau](media/Presence_OOF.png) <span data-ttu-id="20547-152">Absent du bureau</span><span class="sxs-lookup"><span data-stu-id="20547-152">Out of Office</span></span>|
|||

<span data-ttu-id="20547-153">Les statuts de présence configurés par l’application dépendent de l’activité des utilisateurs (disponible, absent), des États du calendrier Outlook (dans une réunion) ou des États des applications Teams (en cours de présentation).</span><span class="sxs-lookup"><span data-stu-id="20547-153">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="20547-154">Votre statut de présence actuel passe à absent (e) lorsque vous verrouillez votre ordinateur ou lorsque le mode veille est entré.</span><span class="sxs-lookup"><span data-stu-id="20547-154">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="20547-155">Sur les appareils mobiles, votre statut de présence passe à absent (e) lorsque l’application teams est en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="20547-155">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="20547-156">Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence.</span><span class="sxs-lookup"><span data-stu-id="20547-156">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="20547-157">Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne.</span><span class="sxs-lookup"><span data-stu-id="20547-157">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="20547-158">Si un utilisateur est en mode ne pas déranger, il continue à recevoir des messages de la conversation, mais les notifications de bannière n’apparaissent pas.</span><span class="sxs-lookup"><span data-stu-id="20547-158">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="20547-159">Les utilisateurs reçoivent les appels dans tous les pays, à l’exception de ne pas déranger, dans lesquels les appels entrants sont dirigés vers la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="20547-159">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="20547-160">Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="20547-160">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="20547-161">Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="20547-161">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="20547-162">Les personnes disposant d’un accès prioritaire peuvent contacter l’utilisateur, même si celui-ci est en ne pas déranger.</span><span class="sxs-lookup"><span data-stu-id="20547-162">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="20547-163">Paramètres d’administrateur dans Teams comparé à ceux de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="20547-163">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="20547-164">Les paramètres d’administration suivants de Skype Entreprise sont différents de ceux dans Teams :</span><span class="sxs-lookup"><span data-stu-id="20547-164">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="20547-165">Le partage de présence est toujours activé dans Teams pour les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="20547-165">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="20547-166">La configuration de la confidentialité (dans laquelle vous définissez les personnes pouvant voir la présence) n’est pas disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="20547-166">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="20547-167">Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Teams.</span><span class="sxs-lookup"><span data-stu-id="20547-167">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="20547-168">Leur liste de contacts (s'ils en avaient une dans Skype Entreprise) est visible sous **Conversation > Contacts** ou sous **Appels > Contacts**.</span><span class="sxs-lookup"><span data-stu-id="20547-168">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="20547-169">Les fonctionnalités du client Ne sont pas déranger et Autorisé à appeler sont toujours activées pour les utilisateurs Teams.</span><span class="sxs-lookup"><span data-stu-id="20547-169">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="20547-170">L'intégration du calendrier (comprend les informations d’absence du bureau et d’autres informations de calendrier) est toujours activée pour les utilisateurs lorsque Teams est intégrée à Outlook.</span><span class="sxs-lookup"><span data-stu-id="20547-170">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="20547-171">L'indicateur *Vu pour la dernière fois* ou *Absent depuis* est toujours activé pour les utilisateurs Teams si l’organisation utilise également Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="20547-171">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="20547-172">La possibilité pour un administrateur Teams de personnaliser ces paramètres n’est pas prise en charge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="20547-172">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="20547-173">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="20547-173">Coexistence with Skype for Business</span></span>

<span data-ttu-id="20547-174">Pour plus d’informations sur les fonctions de présence Teams lorsque votre organisation utilise également Skype Entreprise, voir [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="20547-174">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
