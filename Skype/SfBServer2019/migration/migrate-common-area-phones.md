---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les téléphones portables courants sont les téléphones IP qui se trouvent le plus souvent dans un espace de travail partagé ou une zone commune (par exemple, salle d’attente, cuisine ou étage d’usine). Il n’est pas nécessaire de connecter des téléphones communs à un ordinateur pour fournir une fonctionnalité de communications unifiées (UC) Skype entreprise Server. Après avoir migré un déploiement vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés au numéro local hérité. À l’aide de Skype entreprise Server Management Shell, vous devez tout d’abord récupérer tous les objets de contact associés aux numéros de téléphone de zone commune hérités, puis déplacer ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: f268c22f1d1132b3b5b8c1c1676e5b3a0182cf3f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991149"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="a8ca4-106">Migration des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="a8ca4-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="a8ca4-107">Les téléphones portables courants sont les téléphones IP qui se trouvent le plus souvent dans un espace de travail partagé ou une zone commune (par exemple, salle d’attente, cuisine ou étage d’usine).</span><span class="sxs-lookup"><span data-stu-id="a8ca4-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="a8ca4-108">Il n’est pas nécessaire de connecter des téléphones communs à un ordinateur pour fournir une fonctionnalité de communications unifiées (UC) Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a8ca4-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="a8ca4-109">Après avoir migré un déploiement vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés au numéro local hérité.</span><span class="sxs-lookup"><span data-stu-id="a8ca4-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="a8ca4-110">À l’aide de Skype entreprise Server Management Shell, vous devez tout d’abord récupérer tous les objets de contact associés aux numéros de téléphone de zone commune hérités, puis déplacer ces objets vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8ca4-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="a8ca4-111">Migration des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="a8ca4-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="a8ca4-112">À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a8ca4-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="a8ca4-113">À partir de la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a8ca4-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="a8ca4-114">Pour vérifier que tous les objets de contact ont été déplacés vers le pool Skype entreprise Server 2019, à partir de Skype entreprise Server Management Shell, tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a8ca4-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="a8ca4-115">Vérifiez que tous les objets de contact sont désormais associés au pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a8ca4-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

