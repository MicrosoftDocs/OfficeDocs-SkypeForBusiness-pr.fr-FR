---
title: Réinitialisation du contrôle d’admission des appels
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
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement cac vers un pool Skype Entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753296"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="58bb2-103">Réinitialisation du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="58bb2-103">Reset call admission control</span></span>

<span data-ttu-id="58bb2-104">Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement cac vers un pool Skype Entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="58bb2-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="58bb2-105">Pour réinitialiser le service Contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="58bb2-105">To reset CAC</span></span>

1. <span data-ttu-id="58bb2-106">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="58bb2-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="58bb2-107">Cliquez avec le bouton droit sur le nœud du site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="58bb2-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="58bb2-108">Sous **Définition du contrôle d’admission des appels**, assurez-vous que l’option **Activer le contrôle d’admission des appels** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58bb2-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="58bb2-109">Sous **pool frontal pour** exécuter le contrôle d’admission des appels , sélectionnez le pool Skype Entreprise Server 2019 qui doit héberger le contrôle d’admission des appels, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="58bb2-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="58bb2-110">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="58bb2-110">Publish the topology.</span></span>
    

