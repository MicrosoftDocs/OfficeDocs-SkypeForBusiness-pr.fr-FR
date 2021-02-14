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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: LEnter-CcUpdate cmdlet prépare le serveur hôte Skype Entreprise, version Cloud Connector, au processus de mise à jour en le mettant en mode maintenance. L’appliance arrête immédiatement tous les services, mettant fin à tous les appels en cours et rejetant les nouveaux appels.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802174"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="2a64f-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="2a64f-104">Enter-CcUpdate</span></span>

<span data-ttu-id="2a64f-105">LEnter-CcUpdate cmdlet prépare le serveur hôte Skype Entreprise, version Cloud Connector, au processus de mise à jour en le mettant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="2a64f-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="2a64f-106">L’appliance arrête immédiatement tous les services, mettant fin à tous les appels en cours et rejetant les nouveaux appels.</span><span class="sxs-lookup"><span data-stu-id="2a64f-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="2a64f-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2a64f-107">Parameters</span></span>

<span data-ttu-id="2a64f-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="2a64f-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2a64f-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="2a64f-109">Examples</span></span>
<span data-ttu-id="2a64f-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2a64f-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2a64f-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="2a64f-111">Example 1</span></span>

<span data-ttu-id="2a64f-112">L’exemple suivant prépare l’appliance pour le processus de mise à jour en entrant en mode maintenance :</span><span class="sxs-lookup"><span data-stu-id="2a64f-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="2a64f-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="2a64f-113">Detailed Description</span></span>
<span data-ttu-id="2a64f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2a64f-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2a64f-115">La cmdlet Enter-CcUpdate arrêtera immédiatement tous les services mettant fin aux appels en cours et l’appliance rejettera les nouveaux appels transférés vers d’autres appliances de production.</span><span class="sxs-lookup"><span data-stu-id="2a64f-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="2a64f-116">Vous devez vous assurer que les appliances de production restantes ont une capacité suffisante pour gérer les appels provenant de l’appliance que vous préparez à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="2a64f-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="2a64f-117">Le mode maintenance est utile si la mise à jour automatique de votre appliance est activée, par exemple, et que Microsoft libère un correctif logiciel critique.</span><span class="sxs-lookup"><span data-stu-id="2a64f-117">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix.</span></span> <span data-ttu-id="2a64f-118">Le mode maintenance est également utile si vous décidez de désactiver les mises à jour automatiques, mais que vous effectuez des mises à jour manuelles de manière cohérente.</span><span class="sxs-lookup"><span data-stu-id="2a64f-118">Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="2a64f-119">Après avoir installé les mises à jour, l’appliance peut revenir en mode production en exécutant Exit-CcUpdate cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a64f-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a64f-120">Si vous décidez de mettre à jour manuellement une appliance Cloud Connector, vous devez la mettre à jour dans les 60 jours suivant la publication de la version suivante par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a64f-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="2a64f-121">Microsoft prend en charge la version précédemment publiée de Cloud Connector pendant 60 jours après la publication de la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="2a64f-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="2a64f-122">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="2a64f-122">Input Types</span></span>
<span data-ttu-id="2a64f-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a64f-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2a64f-124">Aucun.</span><span class="sxs-lookup"><span data-stu-id="2a64f-124">None.</span></span> <span data-ttu-id="2a64f-125">La cmdlet Enter-CCUpdate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="2a64f-125">The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2a64f-126">Types de retour</span><span class="sxs-lookup"><span data-stu-id="2a64f-126">Return Types</span></span>
<span data-ttu-id="2a64f-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a64f-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2a64f-128">Aucun</span><span class="sxs-lookup"><span data-stu-id="2a64f-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2a64f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a64f-129">See also</span></span>
<span data-ttu-id="2a64f-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a64f-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2a64f-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="2a64f-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

