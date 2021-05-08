---
title: Configurer le mode de confidentialité de la présence
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: 'Découvrez comment configurer le mode de confidentialité pour vos utilisateurs afin qu’ils contrôlent mieux la façon dont les utilisateurs voient leur disponibilité. '
ms.openlocfilehash: f8589dfb648693f0c0c4331a1a16119a3d7fe748
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239951"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="8aecc-103">Configurer le mode de confidentialité de la présence</span><span class="sxs-lookup"><span data-stu-id="8aecc-103">Configure presence privacy mode</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="8aecc-104">Le Microsoft Teams d’administration a remplacé Skype Entreprise centre d’administration principal (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="8aecc-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="8aecc-105">Tous les paramètres de gestion des Skype Entreprise sont désormais dans le Centre Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="8aecc-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="8aecc-106">Le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur global ou de l’administrateur de Skype Entreprise vous doit être attribué pour gérer les fonctionnalités de gestion des Skype Entreprise dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="8aecc-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="8aecc-107">Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="8aecc-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="8aecc-108">Le Skype Entreprise de présence en ligne donne aux personnes davantage de contrôle sur les personnes qui peuvent voir s’ils sont disponibles, en réunion ou en dehors du bureau.</span><span class="sxs-lookup"><span data-stu-id="8aecc-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="8aecc-109">Pour plus d’informations sur Skype Entreprise de présence et de confidentialité, voir Configurer la présence [dans Skype Entreprise Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="8aecc-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="8aecc-110">Choisir le paramètre de présence en ligne par défaut pour tous les membres de votre organisation</span><span class="sxs-lookup"><span data-stu-id="8aecc-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="8aecc-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="8aecc-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="8aecc-112">Allez dans le Centre Skype Entreprise’administration en ligne > **organisation > général.**</span><span class="sxs-lookup"><span data-stu-id="8aecc-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="8aecc-113">Sous **Mode de confidentialité de la** présence, sélectionnez le paramètre, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="8aecc-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="8aecc-114">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="8aecc-114">**Setting**</span></span>|<span data-ttu-id="8aecc-115">**Qui peut afficher la présence d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="8aecc-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8aecc-116">**Afficher automatiquement des informations de présence**</span><span class="sxs-lookup"><span data-stu-id="8aecc-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="8aecc-117">Tout Skype Entreprise utilisateur qui n’appartient pas **au** groupe de confidentialité externe **ou** bloqué.</span><span class="sxs-lookup"><span data-stu-id="8aecc-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="8aecc-118">**Afficher les informations de présence uniquement aux contacts d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="8aecc-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="8aecc-119">Toute personne dans la liste des contacts d’un utilisateur qui n’appartient pas au groupe de confidentialité **Externe** **ou** Bloqué.</span><span class="sxs-lookup"><span data-stu-id="8aecc-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="8aecc-120">Les utilisateurs individuels peuvent modifier ce paramètre dans la boîte Skype Entreprise **Options** de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8aecc-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="8aecc-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8aecc-121">Related topics</span></span>
[<span data-ttu-id="8aecc-122">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8aecc-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8aecc-123">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="8aecc-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
