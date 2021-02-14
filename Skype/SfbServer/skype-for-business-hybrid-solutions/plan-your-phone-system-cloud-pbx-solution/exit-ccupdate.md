---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: LExit-CcUpdate cmdlet quitte le mode maintenance des mises à jour sur le serveur hôte de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801764"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="a972a-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="a972a-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="a972a-104">LExit-CcUpdate cmdlet quitte le mode maintenance des mises à jour sur le serveur hôte de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a972a-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="a972a-105">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a972a-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="a972a-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a972a-106">Parameters</span></span>

<span data-ttu-id="a972a-107">Aucun</span><span class="sxs-lookup"><span data-stu-id="a972a-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a972a-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="a972a-108">Examples</span></span>
<span data-ttu-id="a972a-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a972a-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a972a-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="a972a-110">Example 1</span></span>

<span data-ttu-id="a972a-111">La commande suivante place l’appliance sur laquelle elle s’exécute à nouveau en mode production :</span><span class="sxs-lookup"><span data-stu-id="a972a-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="a972a-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="a972a-112">Detailed Description</span></span>
<span data-ttu-id="a972a-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a972a-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a972a-114">Si vous avez des appliances que vous avez mises en mode maintenance en spécifiant l'Enter-CcUpdate cmdlet, l'Exit-CcUpdate les place en mode production.</span><span class="sxs-lookup"><span data-stu-id="a972a-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="a972a-115">Pour plus d’informations sur la mise en mode maintenance des appliances, voir Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="a972a-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a972a-116">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="a972a-116">Input Types</span></span>
<span data-ttu-id="a972a-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a972a-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a972a-118">Aucun.</span><span class="sxs-lookup"><span data-stu-id="a972a-118">None.</span></span> <span data-ttu-id="a972a-119">La cmdlet Exit-CcUpdate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="a972a-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a972a-120">Types de retour</span><span class="sxs-lookup"><span data-stu-id="a972a-120">Return Types</span></span>
<span data-ttu-id="a972a-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a972a-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a972a-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="a972a-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a972a-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a972a-123">See also</span></span>
<span data-ttu-id="a972a-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a972a-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a972a-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="a972a-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

