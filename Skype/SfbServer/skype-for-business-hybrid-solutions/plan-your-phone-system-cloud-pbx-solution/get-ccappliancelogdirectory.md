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
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: L’applet de commande Get-CcApplianceLogDirectory affiche l’annuaire actuel regroupant les journaux de l’appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 675e89f49c7c1384edc7cfa5944c8aee3f236c79
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287369"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="a66d7-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="a66d7-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="a66d7-104">L’applet de commande Get-CcApplianceLogDirectory affiche l’annuaire actuel regroupant les journaux de l’appliance de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a66d7-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="a66d7-105">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a66d7-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="a66d7-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a66d7-106">Parameters</span></span>

<span data-ttu-id="a66d7-107">Aucun</span><span class="sxs-lookup"><span data-stu-id="a66d7-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a66d7-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="a66d7-108">Examples</span></span>
<span data-ttu-id="a66d7-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a66d7-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="a66d7-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="a66d7-110">Example 1</span></span>

<span data-ttu-id="a66d7-111">L’exemple suivant montre le dossier actuel dans lequel sont stockés les journaux de l’appliance actuelle du connecteur Cloud:</span><span class="sxs-lookup"><span data-stu-id="a66d7-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="a66d7-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="a66d7-112">Detailed Description</span></span>
<span data-ttu-id="a66d7-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a66d7-113"></span></span>

<span data-ttu-id="a66d7-114">L’applet de connexion Get-CcApplianceLogDirectory affiche le répertoire actuel dans lequel se trouvent les journaux pour un appareil de connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="a66d7-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="a66d7-115">Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="a66d7-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="a66d7-116">Vous pouvez modifier l’annuaire en utilisant l’applet de commande Set-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="a66d7-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="a66d7-117">Remarque : Il n’existe aucune applet de commande qui change uniquement l’emplacement du dossier de journal sans modifier l’annuaire d’appliances.</span><span class="sxs-lookup"><span data-stu-id="a66d7-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a66d7-118">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="a66d7-118">Input Types</span></span>
<span data-ttu-id="a66d7-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a66d7-119"></span></span>

<span data-ttu-id="a66d7-p102">Aucun. L’applet de commande Get-CcApplianceLogDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="a66d7-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a66d7-122">Types de retours</span><span class="sxs-lookup"><span data-stu-id="a66d7-122">Return Types</span></span>
<span data-ttu-id="a66d7-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a66d7-123"></span></span>

<span data-ttu-id="a66d7-124">Cette commande renvoie un chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="a66d7-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a66d7-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a66d7-125">See also</span></span>
<span data-ttu-id="a66d7-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a66d7-126"></span></span>

[<span data-ttu-id="a66d7-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a66d7-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

