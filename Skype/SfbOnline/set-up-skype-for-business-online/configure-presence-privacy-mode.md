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
ms.openlocfilehash: 0b708c86d2693228ad7a613755a181fff5b3743d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093468"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="18671-103">Configurer le mode de confidentialité de la présence</span><span class="sxs-lookup"><span data-stu-id="18671-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18671-104">Le Centre d’administration Microsoft Teams a remplacé le Centre d’administration Skype Entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="18671-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="18671-105">Tous les paramètres de gestion de Skype Entreprise sont désormais dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="18671-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="18671-106">Pour gérer les fonctionnalités de Skype Entreprise dans le Centre d’administration Teams, vous devez avoir le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) d’administrateur global ou d’administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="18671-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="18671-107">Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="18671-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="18671-108">Le paramètre de présence de Skype Entreprise Online donne aux utilisateurs davantage de contrôle sur les personnes qui peuvent voir s’ils sont disponibles, en réunion ou en dehors du bureau.</span><span class="sxs-lookup"><span data-stu-id="18671-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="18671-109">Pour plus d’informations sur les paramètres de présence et de confidentialité de Skype Entreprise, consultez Configurer la [présence dans Skype Entreprise Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="18671-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="18671-110">Choisir le paramètre de présence en ligne par défaut pour tous les membres de votre organisation</span><span class="sxs-lookup"><span data-stu-id="18671-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="18671-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="18671-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="18671-112">Dans le Centre d’administration Skype Entreprise Online, > **organisation > général.**</span><span class="sxs-lookup"><span data-stu-id="18671-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="18671-113">Sous **Mode de confidentialité de la** présence, sélectionnez le paramètre, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="18671-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="18671-114">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="18671-114">**Setting**</span></span>|<span data-ttu-id="18671-115">**Qui peut afficher la présence d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="18671-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="18671-116">**Afficher automatiquement des informations de présence**</span><span class="sxs-lookup"><span data-stu-id="18671-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="18671-117">Tout utilisateur Skype Entreprise n’appartenant pas au groupe de confidentialité **externe** **ou** bloqué.</span><span class="sxs-lookup"><span data-stu-id="18671-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="18671-118">**Afficher les informations de présence uniquement aux contacts d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="18671-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="18671-119">Toute personne dans la liste des contacts d’un utilisateur qui n’appartient pas au groupe de confidentialité **Externe** **ou** Bloqué.</span><span class="sxs-lookup"><span data-stu-id="18671-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="18671-120">Les utilisateurs individuels peuvent modifier ce paramètre dans la boîte de dialogue **Options** de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="18671-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="18671-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="18671-121">Related topics</span></span>
[<span data-ttu-id="18671-122">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="18671-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="18671-123">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="18671-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
