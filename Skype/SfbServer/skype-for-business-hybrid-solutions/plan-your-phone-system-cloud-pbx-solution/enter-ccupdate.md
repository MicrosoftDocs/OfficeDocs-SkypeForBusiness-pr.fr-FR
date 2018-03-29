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
description: L’applet de commande Enter-CcUpdate prépare le serveur hôte de la version Cloud Connector de Skype Entreprise au processus de mise à jour en le mettant en mode maintenance. La solution matérielle-logicielle isdrained — autrement dit, tous les appels existants seront effectue, mais les nouveaux appels sont rejetés.
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a><span data-ttu-id="1be73-104">Entrez-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="1be73-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="1be73-105">L’applet de commande Enter-CcUpdate prépare le serveur hôte de la version Cloud Connector de Skype Entreprise au processus de mise à jour en le mettant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="1be73-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="1be73-106">La solution matérielle-logicielle est « purgé » — autrement dit, tous les appels existants seront effectue, mais les nouveaux appels sont rejetés.</span><span class="sxs-lookup"><span data-stu-id="1be73-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="1be73-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1be73-107">Parameters</span></span>

<span data-ttu-id="1be73-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="1be73-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1be73-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="1be73-109">Examples</span></span>
<span data-ttu-id="1be73-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1be73-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="1be73-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="1be73-111">Example 1</span></span>

<span data-ttu-id="1be73-112">L’exemple suivant prépare l’appliance au processus de mise à jour en entrant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="1be73-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="1be73-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="1be73-113">Detailed Description</span></span>
<span data-ttu-id="1be73-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1be73-114"></span></span>

<span data-ttu-id="1be73-115">L’applet de commande entrée-CcUpdate permet de garantir que tous les appels en cours d’exécution sur un matériel de connecteur de Cloud seront effectue, mais rejette tout nouveaux appels, qui sont transférées à d’autres applications de production.</span><span class="sxs-lookup"><span data-stu-id="1be73-115">The Enter-CcUpdate cmdlet will ensure that all running calls on a Cloud Connector appliance will complete, but the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="1be73-116">Cette applet de commande vous permet de mettre à jour une appliance sans que cela ait une incidence sur la fin des appels d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1be73-116">This cmdlet enables you to update an appliance without affecting end users calls.</span></span> <span data-ttu-id="1be73-117">Vous devez vous assurer que les appliances de production restantes possèdent une capacité suffisante pour supporter les appels de l’appliance que vous vous apprêtez à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="1be73-117">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="1be73-p104">Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.</span><span class="sxs-lookup"><span data-stu-id="1be73-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="1be73-120">Après avoir installé les mises à jour, l’appliance peut à nouveau être mise en mode production en exécutant l’applet de commande Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="1be73-120">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1be73-121">Si vous décidez de mettre à jour manuellement une application Connecteur de nuage, vous devez mettre à jour dans les 60 jours, une fois que Microsoft publie la prochaine version.</span><span class="sxs-lookup"><span data-stu-id="1be73-121">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="1be73-122">Microsoft prend en charge la version précédemment publiée du connecteur de nuage pendant 60 jours après la publication de la nouvelle version</span><span class="sxs-lookup"><span data-stu-id="1be73-122">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="1be73-123">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="1be73-123">Input Types</span></span>
<span data-ttu-id="1be73-124"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1be73-124"></span></span>

<span data-ttu-id="1be73-p106">Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="1be73-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1be73-127">Types de retours</span><span class="sxs-lookup"><span data-stu-id="1be73-127">Return Types</span></span>
<span data-ttu-id="1be73-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1be73-128"></span></span>

<span data-ttu-id="1be73-129">Aucun</span><span class="sxs-lookup"><span data-stu-id="1be73-129">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1be73-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1be73-130">See also</span></span>
<span data-ttu-id="1be73-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1be73-131"></span></span>

[<span data-ttu-id="1be73-132">Quitter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="1be73-132">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

