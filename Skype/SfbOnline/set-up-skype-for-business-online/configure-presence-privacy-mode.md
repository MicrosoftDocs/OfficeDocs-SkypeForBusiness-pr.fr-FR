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
ms.openlocfilehash: f0f9237f701be219a9cbce9a44704cbb582f48d4
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739182"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="f9c69-103">Configurer le mode de confidentialité de la présence</span><span class="sxs-lookup"><span data-stu-id="f9c69-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9c69-104">Le centre d’administration Microsoft teams a remplacé le centre d’administration Skype entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="f9c69-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="f9c69-105">Tous les paramètres de gestion de Skype entreprise se trouvent désormais dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="f9c69-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="f9c69-106">Pour en savoir plus, voir [gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f9c69-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="f9c69-107">Le paramètre de présence de Skype entreprise Online donne aux personnes davantage de contrôle sur qui peut voir si elles sont disponibles, en réunion ou absent (e) du bureau.</span><span class="sxs-lookup"><span data-stu-id="f9c69-107">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="f9c69-108">Pour plus d’informations sur les paramètres de présence et de confidentialité de Skype entreprise, reportez-vous à la rubrique [configuration de la présence dans Skype entreprise Online](configure-presence-in-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="f9c69-108">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="f9c69-109">Sélectionner le paramètre de présence en ligne par défaut pour tous les membres de votre organisation</span><span class="sxs-lookup"><span data-stu-id="f9c69-109">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="f9c69-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f9c69-110"><a name="__top"> </a></span></span>

1. <span data-ttu-id="f9c69-111">Accédez au centre d’administration de Skype entreprise Online > **> général**de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="f9c69-111">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="f9c69-112">Sous **mode de confidentialité**de la présence, choisissez le paramètre, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f9c69-112">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="f9c69-113">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="f9c69-113">**Setting**</span></span>|<span data-ttu-id="f9c69-114">**Qui peut voir la présence d’un utilisateur ?**</span><span class="sxs-lookup"><span data-stu-id="f9c69-114">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9c69-115">**Afficher automatiquement des informations de présence**</span><span class="sxs-lookup"><span data-stu-id="f9c69-115">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="f9c69-116">Tout utilisateur de Skype entreprise qui n’appartient pas au groupe de confidentialité **externe** ou **bloqué** .</span><span class="sxs-lookup"><span data-stu-id="f9c69-116">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="f9c69-117">**Afficher les informations de présence uniquement aux contacts d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="f9c69-117">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="f9c69-118">Toute personne figurant dans la liste de contacts d’un utilisateur et qui n’appartient pas au groupe de confidentialité **externe** ou **bloqué** .</span><span class="sxs-lookup"><span data-stu-id="f9c69-118">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="f9c69-119">Les utilisateurs individuels peuvent modifier ce paramètre dans la boîte de dialogue **options** Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f9c69-119">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="f9c69-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9c69-120">Related topics</span></span>
[<span data-ttu-id="f9c69-121">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f9c69-121">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f9c69-122">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="f9c69-122">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
