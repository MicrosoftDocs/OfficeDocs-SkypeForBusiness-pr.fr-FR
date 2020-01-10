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
ms.openlocfilehash: 694faf7f03fb672ec61ee97db08fb61bcf0dc532
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003454"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="caead-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="caead-104">Enter-CcUpdate</span></span>

<span data-ttu-id="caead-105">L’applet de connexion Enter-CcUpdate prépare le serveur hôte Cloud Connector Skype entreprise pour le processus de mise à jour en le plaçant en mode de maintenance.</span><span class="sxs-lookup"><span data-stu-id="caead-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="caead-106">L’application arrête immédiatement tous les services, fin des appels en cours et rejette tout nouvel appel.</span><span class="sxs-lookup"><span data-stu-id="caead-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="caead-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="caead-107">Parameters</span></span>

<span data-ttu-id="caead-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="caead-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="caead-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="caead-109">Examples</span></span>
<span data-ttu-id="caead-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="caead-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="caead-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="caead-111">Example 1</span></span>

<span data-ttu-id="caead-112">L’exemple suivant prépare l’appliance au processus de mise à jour en entrant en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="caead-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="caead-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="caead-113">Detailed Description</span></span>
<span data-ttu-id="caead-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="caead-114"></span></span>

<span data-ttu-id="caead-115">L’applet de commande Enter-CcUpdate arrête immédiatement tous les services mettant fin à des appels en cours et l’application refusera tout nouveau appel, qui sont transférés vers d’autres appareils de production.</span><span class="sxs-lookup"><span data-stu-id="caead-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="caead-116">Vous devez vous assurer que les autres appareils de production ne disposent pas de capacités suffisantes pour gérer les appels à partir de l’appareil que vous préparez à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="caead-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="caead-p104">Le mode maintenance est utile si votre appliance possède une mise à jour automatique, par exemple, et si Microsoft possède un correctif d’intervention. Le mode maintenance est également utile si vous décidez d’interrompre les mises à jour automatiques mais que vous effectuez systématiquement des mises à jour manuelles.</span><span class="sxs-lookup"><span data-stu-id="caead-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="caead-119">Après l’installation des mises à jour, l’application peut être rétablie en mode de production en exécutant l’applet de passe Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="caead-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caead-120">Si vous décidez de mettre à jour manuellement un appareil de connexion Cloud, vous devez le mettre à jour dans 60 jours après la publication de la prochaine version par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="caead-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="caead-121">Microsoft prend en charge la version précédemment publiée du Cloud Connector pour 60 jours après la sortie de la nouvelle version</span><span class="sxs-lookup"><span data-stu-id="caead-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="caead-122">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="caead-122">Input Types</span></span>
<span data-ttu-id="caead-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="caead-123"></span></span>

<span data-ttu-id="caead-p106">Aucun. L’applet de commande Enter-CCUpdate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="caead-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="caead-126">Types de retours</span><span class="sxs-lookup"><span data-stu-id="caead-126">Return Types</span></span>
<span data-ttu-id="caead-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="caead-127"></span></span>

<span data-ttu-id="caead-128">Aucun</span><span class="sxs-lookup"><span data-stu-id="caead-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="caead-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="caead-129">See also</span></span>
<span data-ttu-id="caead-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="caead-130"></span></span>

[<span data-ttu-id="caead-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="caead-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

