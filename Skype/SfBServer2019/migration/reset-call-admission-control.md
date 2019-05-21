---
title: Réinitialisation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307097"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="ce5bc-103">Réinitialisation du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="ce5bc-103">Reset call admission control</span></span>

<span data-ttu-id="ce5bc-104">Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="ce5bc-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="ce5bc-105">Pour réinitialiser le CAC</span><span class="sxs-lookup"><span data-stu-id="ce5bc-105">To reset CAC</span></span>

1. <span data-ttu-id="ce5bc-106">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ce5bc-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ce5bc-107">Cliquez avec le bouton droit sur le nœud site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ce5bc-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="ce5bc-108">Sous **paramètre de contrôle d’admission des appels**, assurez-vous que l’option **activer le contrôle d’admission des appels** est activée.</span><span class="sxs-lookup"><span data-stu-id="ce5bc-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="ce5bc-109">Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Skype entreprise Server 2019 d’hébergement CAC, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce5bc-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="ce5bc-110">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="ce5bc-110">Publish the topology.</span></span>
    

