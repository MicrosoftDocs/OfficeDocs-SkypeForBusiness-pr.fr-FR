---
title: Réinitialisation du contrôle d’admission des appels
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer CAC hébergement à un Skype pour Business Server 2019 pool avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027318"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="41fb4-103">Réinitialisation du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="41fb4-103">Reset call admission control</span></span>

<span data-ttu-id="41fb4-104">Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer CAC hébergement à un Skype pour Business Server 2019 pool avant de pouvoir supprimer le pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="41fb4-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="41fb4-105">Pour réinitialiser CAC</span><span class="sxs-lookup"><span data-stu-id="41fb4-105">To reset CAC</span></span>

1. <span data-ttu-id="41fb4-106">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="41fb4-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="41fb4-107">Cliquez sur le nœud du site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="41fb4-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="41fb4-108">Sous **paramètres de contrôle d’Admission des appels**, assurez-vous de **Qu'activer le contrôle d’admission des appels** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="41fb4-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="41fb4-109">Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le Skype pour le pool d’entreprise Server 2019 pour héberger CAC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="41fb4-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="41fb4-110">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="41fb4-110">Publish the topology.</span></span>
    

