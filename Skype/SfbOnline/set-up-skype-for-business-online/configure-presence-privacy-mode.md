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
description: 'Apprenez à configurer le mode de confidentialité pour vos utilisateurs afin qu’ils puissent mieux contrôler la façon dont les personnes voient leur disponibilité. '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753439"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="012ff-103">Configurer le mode de confidentialité de la présence</span><span class="sxs-lookup"><span data-stu-id="012ff-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="012ff-104">Le centre d’administration Microsoft teams a remplacé le centre d’administration Skype entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="012ff-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="012ff-105">Tous les paramètres de gestion de Skype entreprise se trouvent désormais dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="012ff-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="012ff-106">Pour pouvoir gérer les fonctionnalités Skype entreprise dans le centre d’administration Teams, vous devez avoir le rôle d’administrateur [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de l’administrateur général ou de l’administrateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="012ff-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="012ff-107">Pour en savoir plus, voir [gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="012ff-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="012ff-108">Le paramètre de présence de Skype entreprise Online donne aux personnes davantage de contrôle sur qui peut voir si elles sont disponibles, en réunion ou absent (e) du bureau.</span><span class="sxs-lookup"><span data-stu-id="012ff-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="012ff-109">Pour plus d’informations sur les paramètres de présence et de confidentialité de Skype entreprise, reportez-vous à la rubrique [configuration de la présence dans Skype entreprise Online](configure-presence-in-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="012ff-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="012ff-110">Sélectionner le paramètre de présence en ligne par défaut pour tous les membres de votre organisation</span><span class="sxs-lookup"><span data-stu-id="012ff-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="012ff-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="012ff-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="012ff-112">Accédez au centre d’administration de Skype entreprise Online > **> général**de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="012ff-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="012ff-113">Sous **mode de confidentialité**de la présence, choisissez le paramètre, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="012ff-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="012ff-114">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="012ff-114">**Setting**</span></span>|<span data-ttu-id="012ff-115">**Qui peut voir la présence d’un utilisateur ?**</span><span class="sxs-lookup"><span data-stu-id="012ff-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="012ff-116">**Afficher automatiquement des informations de présence**</span><span class="sxs-lookup"><span data-stu-id="012ff-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="012ff-117">Tout utilisateur de Skype entreprise qui n’appartient pas au groupe de confidentialité **externe** ou **bloqué** .</span><span class="sxs-lookup"><span data-stu-id="012ff-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="012ff-118">**Afficher les informations de présence uniquement aux contacts d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="012ff-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="012ff-119">Toute personne figurant dans la liste de contacts d’un utilisateur et qui n’appartient pas au groupe de confidentialité **externe** ou **bloqué** .</span><span class="sxs-lookup"><span data-stu-id="012ff-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="012ff-120">Les utilisateurs individuels peuvent modifier ce paramètre dans la boîte de dialogue **options** Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="012ff-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="012ff-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="012ff-121">Related topics</span></span>
[<span data-ttu-id="012ff-122">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="012ff-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="012ff-123">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="012ff-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
