---
title: Modifier les paramètres Réunion Skype diffusion pour votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- SMB
- ms.lync.lac.BroadcastMeetings
description: Vous pouvez activer Réunion Skype diffusion et modifier les paramètres et les stratégies de ces réunions.
ms.openlocfilehash: fae53601c858bf67db57352e18dbc9799243f996
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238646"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="20f0c-103">Modifier les paramètres Réunion Skype diffusion pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="20f0c-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="20f0c-104">Le Microsoft Teams d’administration a remplacé Skype Entreprise centre d’administration principal (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="20f0c-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="20f0c-105">Tous les paramètres de gestion des Skype Entreprise sont désormais dans le Centre Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="20f0c-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="20f0c-106">Le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur global ou de l’administrateur de Skype Entreprise vous doit être attribué pour gérer les fonctionnalités de gestion des Skype Entreprise dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="20f0c-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="20f0c-107">Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="20f0c-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="20f0c-108">Vous pouvez activer Réunion Skype diffusion et modifier les paramètres et les stratégies de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="20f0c-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="20f0c-109">**Activer Réunion Skype diffusion** Active Réunion Skype diffusion.</span><span class="sxs-lookup"><span data-stu-id="20f0c-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="20f0c-110">Après avoir activé Réunion Skype, vous devez configurer votre réseau pour [Réunion Skype diffusion.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="20f0c-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="20f0c-111">Cette étape est prise en compte si vous souhaitez organiser des webinaires ou d’autres diffusions pour des personnes extérieures à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="20f0c-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="20f0c-112">**Activer Réunion Skype fonctionnalités de prévisualisation de la diffusion pour mon organisation** Les Skype Entreprise clients vous offrent un accès en avant-première aux nouveaux produits et fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="20f0c-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="20f0c-113">Cela permet à votre organisation de découvrir les nouveautés et d’avoir la possibilité de tester les nouvelles fonctionnalités dans votre propre environnement et de faire part de vos commentaires avant la publication des builds de produits au grand public.</span><span class="sxs-lookup"><span data-stu-id="20f0c-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="20f0c-114">Skype Entreprise’aperçu</span><span class="sxs-lookup"><span data-stu-id="20f0c-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="20f0c-115">**Autoriser les organisateurs à planifier des réunions anonymes** Cela permet aux organisateurs de créer des événements de diffusion qui permettent à toute personne extérieure à l’organisation de participer sans avoir à se connecter.</span><span class="sxs-lookup"><span data-stu-id="20f0c-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="20f0c-116">**Autoriser l’enregistrement des réunions diffusées** Ainsi, toutes les réunions que vous devez enregistrer doivent être enregistrées par le présentateur ou l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="20f0c-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="20f0c-117">**URL du support technique pour les participants** Entrez un lien pour permettre aux participants à la réunion diffusée d’obtenir de l’aide pour la connexion ou la participation à une réunion diffusée.</span><span class="sxs-lookup"><span data-stu-id="20f0c-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="20f0c-118">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="20f0c-118">Related topics</span></span>

[<span data-ttu-id="20f0c-119">Configurer votre réseau pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="20f0c-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
