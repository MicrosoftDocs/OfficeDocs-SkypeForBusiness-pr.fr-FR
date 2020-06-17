---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir la fonctionnalité de communications unifiées (UC) Skype entreprise Server. Après avoir migré un déploiement vers Skype entreprise Server 2019, vous devez également migrer les objets contact associés au téléphone de partie commune hérité. À l’aide de Skype entreprise Server Management Shell, vous devez tout d’abord récupérer tous les objets contact associés aux téléphones de la zone commune héritée, puis déplacer ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752706"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="95f5a-106">Migration des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="95f5a-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="95f5a-107">Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier.</span><span class="sxs-lookup"><span data-stu-id="95f5a-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="95f5a-108">Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir la fonctionnalité de communications unifiées (UC) Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="95f5a-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="95f5a-109">Après avoir migré un déploiement vers Skype entreprise Server 2019, vous devez également migrer les objets contact associés au téléphone de partie commune hérité.</span><span class="sxs-lookup"><span data-stu-id="95f5a-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="95f5a-110">À l’aide de Skype entreprise Server Management Shell, vous devez tout d’abord récupérer tous les objets contact associés aux téléphones de la zone commune héritée, puis déplacer ces objets vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="95f5a-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="95f5a-111">Migration des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="95f5a-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="95f5a-112">À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="95f5a-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="95f5a-113">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="95f5a-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="95f5a-114">Pour vérifier que tous les objets contact ont été déplacés vers le pool Skype entreprise Server 2019, à partir de Skype entreprise Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="95f5a-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="95f5a-115">Vérifiez que tous les objets contact sont désormais associés au pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="95f5a-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

