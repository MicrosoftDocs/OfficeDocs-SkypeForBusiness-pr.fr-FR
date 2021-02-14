---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: LGet-CcApplianceLogDirectory cmdlet affiche l’annuaire actuel dans lequel sont stockés les journaux d’une appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800824"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="df7ee-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="df7ee-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="df7ee-104">LGet-CcApplianceLogDirectory cmdlet affiche l’annuaire actuel dans lequel sont stockés les journaux d’une appliance de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df7ee-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="df7ee-105">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="df7ee-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="df7ee-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="df7ee-106">Parameters</span></span>

<span data-ttu-id="df7ee-107">Aucun</span><span class="sxs-lookup"><span data-stu-id="df7ee-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="df7ee-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="df7ee-108">Examples</span></span>
<span data-ttu-id="df7ee-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="df7ee-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="df7ee-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="df7ee-110">Example 1</span></span>

<span data-ttu-id="df7ee-111">L’exemple suivant montre le dossier actuel dans lequel les journaux de l’appliance actuelle de Cloud Connector sont stockés :</span><span class="sxs-lookup"><span data-stu-id="df7ee-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="df7ee-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="df7ee-112">Detailed Description</span></span>
<span data-ttu-id="df7ee-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="df7ee-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="df7ee-114">LGet-CcApplianceLogDirectory cmdlet affiche le répertoire actuel dans lequel les journaux d’une appliance Cloud Connector sont stockés.</span><span class="sxs-lookup"><span data-stu-id="df7ee-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="df7ee-115">Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="df7ee-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="df7ee-116">Vous pouvez modifier le répertoire à l’aide de Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df7ee-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="df7ee-117">Remarque : aucune cmdlet ne modifie uniquement l’emplacement du dossier journal sans modifier le répertoire de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="df7ee-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="df7ee-118">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="df7ee-118">Input Types</span></span>
<span data-ttu-id="df7ee-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="df7ee-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="df7ee-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="df7ee-120">None.</span></span> <span data-ttu-id="df7ee-121">La cmdlet Get-CcApplianceLogDirectory n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="df7ee-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="df7ee-122">Types de retour</span><span class="sxs-lookup"><span data-stu-id="df7ee-122">Return Types</span></span>
<span data-ttu-id="df7ee-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="df7ee-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="df7ee-124">Cette commande renvoie un chemin d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="df7ee-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df7ee-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df7ee-125">See also</span></span>
<span data-ttu-id="df7ee-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="df7ee-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="df7ee-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="df7ee-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

