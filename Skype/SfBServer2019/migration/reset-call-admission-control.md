---
title: Réinitialisation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812802"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="6e46e-103">Réinitialisation du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="6e46e-103">Reset call admission control</span></span>

<span data-ttu-id="6e46e-104">Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="6e46e-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="6e46e-105">Pour réinitialiser le CAC</span><span class="sxs-lookup"><span data-stu-id="6e46e-105">To reset CAC</span></span>

1. <span data-ttu-id="6e46e-106">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6e46e-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="6e46e-107">Cliquez avec le bouton droit sur le nœud site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6e46e-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="6e46e-108">Sous **paramètre de contrôle d’admission des appels**, assurez-vous que l’option **activer le contrôle d’admission des appels** est activée.</span><span class="sxs-lookup"><span data-stu-id="6e46e-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="6e46e-109">Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Skype entreprise Server 2019 d’hébergement CAC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e46e-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="6e46e-110">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="6e46e-110">Publish the topology.</span></span>
    

