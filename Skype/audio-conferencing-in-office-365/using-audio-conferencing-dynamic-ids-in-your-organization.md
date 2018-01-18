---
title: "À l’aide des ID dynamiques d’audioconférence de votre organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Le service Conférence de données Audio est mis à jour pour fournir chaque Skype pour une réunion commerciale et Teams de Microsoft avec l’ID de conférence différent. ID de conférence dynamiques représentent une amélioration notable sur la conférence static ID, car ils permettent de :"
ms.openlocfilehash: 0838014e8a88d5e27b6bd84838ea105b9f75025a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="3789c-104">À l’aide des ID dynamiques d’audioconférence de votre organisation</span><span class="sxs-lookup"><span data-stu-id="3789c-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="3789c-105">Le service Conférence de données Audio est mis à jour pour fournir chaque Skype pour une réunion commerciale et Teams de Microsoft avec l’ID de conférence différent.</span><span class="sxs-lookup"><span data-stu-id="3789c-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="3789c-106">ID de conférence dynamiques représentent une amélioration notable sur la conférence static ID, car ils permettent de :</span><span class="sxs-lookup"><span data-stu-id="3789c-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="3789c-107">**Sécurité accrue** La conférence ID sont uniques pour chaque Skype pour une réunion commerciale ou Teams de Microsoft et sont générés lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="3789c-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="3789c-108">**Une meilleure expérience pour les réunions consécutives et simultanées :** des informations de rendez-vous spécifiques sont fournies aux réunions pour un même organisateur, ce qui empêche les participants téléphoniques à une réunion de s'ajouter aux participants d'une autre réunion lorsqu'elles sont prévues à peu de temps d'intervalle.</span><span class="sxs-lookup"><span data-stu-id="3789c-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="3789c-109">**Une transition transparente :** lorsque votre organisation active les ID de conférence dynamiques, toutes les réunions qui ont déjà été planifiées dans votre organisation avec des ID de conférence statiques auront lieu.</span><span class="sxs-lookup"><span data-stu-id="3789c-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="3789c-110">ID dynamiques sont uniquement disponibles pour les utilisateurs qui sont activés pour ** Audio conférence ** et demander à Microsoft de définir comme leur fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="3789c-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="3789c-111">Vous pouvez [Affecter de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md) pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3789c-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="3789c-112">Les modifications que verront les utilisateurs de mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="3789c-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="3789c-113">Après l’activation des ID de conférence dynamique pour votre organisation, tout nouveau Skype pour entreprise ou Teams de Microsoft de réunion qui est prévue par les utilisateurs de votre organisation qui sont activés pour l’audioconférence aura conférence ID sera différente de la ID de conférence statique qu’avant.</span><span class="sxs-lookup"><span data-stu-id="3789c-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="3789c-114">Organisateurs qui avaient statique ID de conférence avant doivent rappeler les utilisateurs de joindre leurs réunions qu’ils doivent désormais utiliser un nouvel ID de conférence dans l’invitation à la réunion, avant de pouvoir le rejoindre.</span><span class="sxs-lookup"><span data-stu-id="3789c-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3789c-115">Réunions qui ont été planifiées par un utilisateur avec l’ID de conférence statique avant l’activation de l’organisation pour la conférence dynamique ID continueront d’avoir l’ID de conférence statique, afin qu’ils vous continuer planifier des réunions sans impact.</span><span class="sxs-lookup"><span data-stu-id="3789c-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="3789c-116">Ces exemples vous montrent la nouvelle expérience pour deux Skype pour les réunions d’entreprise qui ont été organisés par le même utilisateur, mais les deux aura maintenant deux ID de conférence différent :</span><span class="sxs-lookup"><span data-stu-id="3789c-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="3789c-117">La **réunion 1** a été programmée de 9 h 00 à 10 h 00 et son ID de conférence est 93907123 :</span><span class="sxs-lookup"><span data-stu-id="3789c-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="3789c-119">La **réunion 2** a été programmée par le même utilisateur de 10 h 00 à 11 h 00 et son ID de conférence est 16353789 :</span><span class="sxs-lookup"><span data-stu-id="3789c-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="3789c-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="3789c-121">Related topics</span></span>

- [<span data-ttu-id="3789c-122">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3789c-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="3789c-123">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="3789c-123">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
    
- <span data-ttu-id="3789c-124">Pour en savoir plus, reportez-vous à la rubrique [Conférence rendez-vous dans Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="3789c-124">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
    

