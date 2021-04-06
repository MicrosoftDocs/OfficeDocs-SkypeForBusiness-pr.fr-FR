---
title: Désaffecter votre environnement Skype Entreprise local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instructions pour la mise hors service de votre environnement Skype Entreprise local.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593883"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="e6e36-103">Désaffecter votre environnement Skype Entreprise local</span><span class="sxs-lookup"><span data-stu-id="e6e36-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="e6e36-104">Si votre organisation utilise Teams ou Skype Entreprise Online avec un déploiement local de Skype Entreprise Server, vous pouvez migrer ces environnements entièrement vers le cloud, puis retirer votre déploiement local de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e6e36-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="e6e36-105">Avant de désaffecter votre environnement local, vous devez configurer la connectivité hybride entre votre déploiement local et Microsoft 365. [](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="e6e36-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="e6e36-106">Après avoir configuré la connectivité hybride, vous pouvez migrer les utilisateurs vers le cloud, lors de la migration de leurs réunions à partir de l’local et de la migration de tous les contacts de Skype Entreprise Server vers Teams.</span><span class="sxs-lookup"><span data-stu-id="e6e36-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="e6e36-107">La configuration de la connectivité hybride est une étape requise pour migrer les utilisateurs de l’local vers le cloud et garantir l’ensemble des fonctionnalités de Teams.</span><span class="sxs-lookup"><span data-stu-id="e6e36-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="e6e36-108">Pour effectuer votre déplacement de l’environnement local vers le cloud et désaffecter votre environnement Skype Entreprise Server local, vous devez effectuer les étapes suivantes dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="e6e36-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="e6e36-109">**Étape 1.**</span><span class="sxs-lookup"><span data-stu-id="e6e36-109">**Step 1.**</span></span> <span data-ttu-id="e6e36-110">[Déplacez tous les utilisateurs et points de terminaison d’application requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="e6e36-110">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="e6e36-111">**Étape 2.**</span><span class="sxs-lookup"><span data-stu-id="e6e36-111">**Step 2.**</span></span> <span data-ttu-id="e6e36-112">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="e6e36-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="e6e36-113">**Étape 3.**</span><span class="sxs-lookup"><span data-stu-id="e6e36-113">**Step 3.**</span></span> <span data-ttu-id="e6e36-114">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="e6e36-114">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

