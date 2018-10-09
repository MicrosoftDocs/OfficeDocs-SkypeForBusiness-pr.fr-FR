---
title: Entrez-CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: L’applet de commande Enter-CcUpdate prépare le serveur hôte de la version Cloud Connector de Skype Entreprise au processus de mise à jour en le mettant en mode maintenance. L’appliance isdrained — autrement dit, tous les appels en cours seront termine, mais les nouveaux appels sont rejetés.
ms.openlocfilehash: f9b789bbd76bd3405617dc170af0695f9cbe94ed
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450510"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="9b6ba-104">Entrez-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="9b6ba-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="9b6ba-105">L’applet de commande Enter-CcUpdate prépare le serveur hôte de la version Cloud Connector de Skype Entreprise au processus de mise à jour en le mettant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="9b6ba-106">Le matériel est « drainée » — autrement dit, tous les appels en cours seront termine, mais les nouveaux appels sont rejetés.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="9b6ba-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9b6ba-107">Parameters</span></span>

<span data-ttu-id="9b6ba-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="9b6ba-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9b6ba-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="9b6ba-109">Examples</span></span>
<span data-ttu-id="9b6ba-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6ba-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="9b6ba-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="9b6ba-111">Example 1</span></span>

<span data-ttu-id="9b6ba-112">L’exemple suivant prépare l’appliance au processus de mise à jour en entrant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="9b6ba-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="9b6ba-113">Detailed Description</span></span>
<span data-ttu-id="9b6ba-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6ba-114"></span></span>

<span data-ttu-id="9b6ba-115">L’applet de commande entrée-CcUpdate s’arrête immédiatement tous les services de fin des appels en cours et rejette les nouveaux appels, qui sont transférés à d’autres applications de production.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="9b6ba-116">Vous devez vous assurer que les appliances de production restantes possèdent une capacité suffisante pour supporter les appels de l’appliance que vous vous apprêtez à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="9b6ba-p104">Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="9b6ba-119">Après avoir installé les mises à jour, l’appliance peut à nouveau être mise en mode production en exécutant l’applet de commande Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b6ba-120">Si vous décidez de mettre à jour manuellement une solution de nuage connecteur, vous devez mettre à jour dans les 60 jours après que Microsoft publie la prochaine version.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="9b6ba-121">Microsoft prend en charge la version précédemment du nuage connecteur pendant 60 jours après la publication de la nouvelle version</span><span class="sxs-lookup"><span data-stu-id="9b6ba-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="9b6ba-122">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="9b6ba-122">Input Types</span></span>
<span data-ttu-id="9b6ba-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6ba-123"></span></span>

<span data-ttu-id="9b6ba-p106">Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="9b6ba-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9b6ba-126">Types de retours</span><span class="sxs-lookup"><span data-stu-id="9b6ba-126">Return Types</span></span>
<span data-ttu-id="9b6ba-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6ba-127"></span></span>

<span data-ttu-id="9b6ba-128">Aucun</span><span class="sxs-lookup"><span data-stu-id="9b6ba-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9b6ba-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b6ba-129">See also</span></span>
<span data-ttu-id="9b6ba-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6ba-130"></span></span>

[<span data-ttu-id="9b6ba-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="9b6ba-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

