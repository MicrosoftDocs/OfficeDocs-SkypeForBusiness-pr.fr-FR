---
title: Définition de vos paramètres de coexistence
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Cela vous permettra de choisir le mode de coexistence et définir les autres paramètres de coexistence.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: add6436d66c088d6ffa14867cc03268cb082f0b3
ms.sourcegitcommit: 265fbdc1a8ac566751e707874656bd6b90de980d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2018
---
# <a name="setting-your-coexistence-settings"></a><span data-ttu-id="1f865-103">Définition de vos paramètres de coexistence</span><span class="sxs-lookup"><span data-stu-id="1f865-103">Setting your coexistence settings</span></span>


> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<Intro text here>

[<span data-ttu-id="1f865-104">Comprendre la coexistence et de mettre à niveau des modes de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="1f865-104">Understand coexistence and upgrade modes for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="setting-your-upgrade-options-for-your-users"></a><span data-ttu-id="1f865-105">Définition de vos options de mise à niveau pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1f865-105">Setting your upgrade options for your users</span></span>

<span data-ttu-id="1f865-106">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="1f865-106">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="1f865-107">Dans la navigation de gauche, accédez à **paramètres à l’échelle de la société** > **équipes de mise à niveau**.</span><span class="sxs-lookup"><span data-stu-id="1f865-107">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="1f865-108">En haut de la page de la **page de mise à niveau des équipes** , apportez les modifications suivantes si elles ne fonctionnera pour vous.</span><span class="sxs-lookup"><span data-stu-id="1f865-108">At the top of the **Teams upgrade page** page, make the following changes if they will work for you.</span></span>
- <span data-ttu-id="1f865-109">Définir le mode de **Coexistence**</span><span class="sxs-lookup"><span data-stu-id="1f865-109">Set the **Coexistence** mode</span></span>
    - <span data-ttu-id="1f865-110">**(Îles)** - Utilisez ce paramètre lorsque vous avez des utilisateurs sur Skype pour les entreprises et certains utilisateurs qui utilisent des équipes.</span><span class="sxs-lookup"><span data-stu-id="1f865-110">**Islands** - use this setting when you have some users on Skype for Business and some users that use Teams.</span></span>
    - <span data-ttu-id="1f865-111">**Skype pour les entreprises uniquement** - Utilisez ce paramètre si vous ne disposez Skype pour les utilisateurs professionnels.</span><span class="sxs-lookup"><span data-stu-id="1f865-111">**Skype for Business only** - use this setting if you only have Skype for Business users.</span></span>
    - <span data-ttu-id="1f865-112">**Équipes uniquement** - Utilisez ce paramètre si vous ne disposez que les utilisateurs des équipes.</span><span class="sxs-lookup"><span data-stu-id="1f865-112">**Teams only** - use this setting if you only have Teams users.</span></span>
- <span data-ttu-id="1f865-113">La valeur **Skype notifier pour les utilisateurs professionnels, équipes est disponible pour la mise à niveau.**</span><span class="sxs-lookup"><span data-stu-id="1f865-113">Set **Notify Skype for Business users that Teams is available for upgrade.**</span></span>
    - <span data-ttu-id="1f865-114">Si vous activez ce, elle indique la Skype pour les utilisateurs professionnels qui ils peuvent mettre à niveau l’application d’équipes.</span><span class="sxs-lookup"><span data-stu-id="1f865-114">If you turn this on, it will tell the Skype for Business users that they can upgrade to the Teams app.</span></span>
- <span data-ttu-id="1f865-115">Définir l' **application par défaut pour les utilisateurs à participer à Skype pour les réunions d’entreprise** , ce paramètre détermine l’application qui est utilisée pour participer à des Skype pour les réunions d’entreprise et est respectée, quelle que soit la valeur de mode de coexistence.</span><span class="sxs-lookup"><span data-stu-id="1f865-115">Set the **Preferred app for users to join Skype for Business meetings**  This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
    - <span data-ttu-id="1f865-116">**Application Skype réunions (par défaut)**</span><span class="sxs-lookup"><span data-stu-id="1f865-116">**Skype Meetings app (default)**</span></span>
    - <span data-ttu-id="1f865-117">**Skype pour les entreprises avec des fonctionnalités limitées**</span><span class="sxs-lookup"><span data-stu-id="1f865-117">**Skype for Business with limited features**</span></span>
- <span data-ttu-id="1f865-118">Définir si pour **Télécharger l’application d’équipes en arrière-plan pour Skype pour les utilisateurs professionnels** ce paramètre télécharge en mode silencieux l’application équipes pour les utilisateurs Skype pour les entreprises en cours d’exécution sur un ordinateur Windows.</span><span class="sxs-lookup"><span data-stu-id="1f865-118">Set whether to **Download the Teams app in the background for Skype for Business users**  This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="1f865-119">Elle est respectée uniquement si le mode de coexistence pour l’utilisateur est équipes uniquement, ou si des notifications en attente de mise à niveau sont activées dans Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="1f865-119">It is honored only if coexistence mode for the user is Teams Only, or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
1. <span data-ttu-id="1f865-120">Une fois que vous apportez vos modifications, cliquez sur **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="1f865-120">Click **Save** after you make your changes.</span></span>


### <a name="related-topics"></a><span data-ttu-id="1f865-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="1f865-121">Related topics</span></span>
<span data-ttu-id="1f865-122">[Planifier le voyage](upgrade-plan-journey.md)
[comprendre la coexistence et modes de Skype pour professionnels et les équipes de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1f865-122">[Plan the journey](upgrade-plan-journey.md)
[Understand coexistence and upgrade modes for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span></span>