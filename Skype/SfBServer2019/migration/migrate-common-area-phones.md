---
title: Migrer des téléphones de partie commune
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Téléphones de partie commune sont IP téléphones que plus souvent se trouvent dans un espace de travail partagé ou la partie commune, comme un atelier de salle d’attente, cuisine ou usine. Téléphones de partie commune est inutile d’être connecté à un ordinateur pour fournir que Skype pour Business Server unifiée la fonctionnalité de communications (UC). Après la migration d’un déploiement à Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec le téléphone en zone commune hérité. À l’aide de Skype pour Business Server Management Shell vous serez tout d’abord récupérer tous les objets contact associés aux anciens téléphones en zone commune, puis déplacer ces objets vers le Skype pour Business Server 2019 pool.
ms.openlocfilehash: d2d30e087d44973379d5f57dd85d137482762e5e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371573"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="bf7d3-106">Migrer des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="bf7d3-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="bf7d3-107">Téléphones de partie commune sont IP téléphones que plus souvent se trouvent dans un espace de travail partagé ou la partie commune, comme un atelier de salle d’attente, cuisine ou usine.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="bf7d3-108">Téléphones de partie commune est inutile d’être connecté à un ordinateur pour fournir que Skype pour Business Server unifiée la fonctionnalité de communications (UC).</span><span class="sxs-lookup"><span data-stu-id="bf7d3-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="bf7d3-109">Après la migration d’un déploiement à Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec le téléphone en zone commune hérité.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="bf7d3-110">À l’aide de Skype pour Business Server Management Shell, vous tout d’abord récupérer tous les objets contact associés aux anciens téléphones en zone commune et puis déplacer ces objets vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="bf7d3-111">Migrer des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="bf7d3-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="bf7d3-112">Skype pour le serveur frontal Business Server 2019, ouvrez Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="bf7d3-113">À partir de la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bf7d3-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="bf7d3-114">Pour vérifier que tous les objets contact ont été déplacés vers le Skype pour le pool d’entreprise Server 2019, à partir de la Skype pour Business Server Management Shell tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bf7d3-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="bf7d3-115">Vérifiez que tous les objets contact sont désormais associé à la Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

