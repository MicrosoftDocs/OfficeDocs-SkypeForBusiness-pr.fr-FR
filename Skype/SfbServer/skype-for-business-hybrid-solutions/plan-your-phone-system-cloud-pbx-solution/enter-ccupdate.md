---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance. L’application arrête immédiatement tous les services, fin des appels en cours et rejette tout nouvel appel.
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "34740057"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="5404d-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="5404d-104">Enter-CcUpdate</span></span>

<span data-ttu-id="5404d-105">L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5404d-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="5404d-106">L’application arrête immédiatement tous les services, fin des appels en cours et rejette tout nouvel appel.</span><span class="sxs-lookup"><span data-stu-id="5404d-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="5404d-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5404d-107">Parameters</span></span>

<span data-ttu-id="5404d-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="5404d-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5404d-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="5404d-109">Examples</span></span>
<span data-ttu-id="5404d-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5404d-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="5404d-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5404d-111">Example 1</span></span>

<span data-ttu-id="5404d-112">L’exemple suivant prépare l’appliance au processus de mise à jour en entrant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="5404d-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="5404d-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="5404d-113">Detailed Description</span></span>
<span data-ttu-id="5404d-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5404d-114"></span></span>

<span data-ttu-id="5404d-115">L’applet de commande Enter-CcUpdate arrête immédiatement tous les services mettant fin à des appels en cours et l’application refusera tout nouveau appel, qui sont transférés vers d’autres appareils de production.</span><span class="sxs-lookup"><span data-stu-id="5404d-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="5404d-116">Vous devez vous assurer que les autres appareils de production ne disposent pas de capacités suffisantes pour gérer les appels à partir de l’appareil que vous préparez à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="5404d-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="5404d-p104">Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.</span><span class="sxs-lookup"><span data-stu-id="5404d-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="5404d-119">Après l’installation des mises à jour, l’application peut être rétablie en mode de production en exécutant l’applet de passe Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="5404d-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5404d-120">Si vous décidez de mettre à jour manuellement un appareil de connexion Cloud, vous devez le mettre à jour dans 60 jours après la publication de la prochaine version par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5404d-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="5404d-121">Microsoft prend en charge la version précédemment publiée du Cloud Connector pour 60 jours après la sortie de la nouvelle version</span><span class="sxs-lookup"><span data-stu-id="5404d-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="5404d-122">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="5404d-122">Input Types</span></span>
<span data-ttu-id="5404d-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5404d-123"></span></span>

<span data-ttu-id="5404d-p106">Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="5404d-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5404d-126">Types de retours</span><span class="sxs-lookup"><span data-stu-id="5404d-126">Return Types</span></span>
<span data-ttu-id="5404d-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5404d-127"></span></span>

<span data-ttu-id="5404d-128">Aucun</span><span class="sxs-lookup"><span data-stu-id="5404d-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5404d-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5404d-129">See also</span></span>
<span data-ttu-id="5404d-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5404d-130"></span></span>

[<span data-ttu-id="5404d-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="5404d-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

