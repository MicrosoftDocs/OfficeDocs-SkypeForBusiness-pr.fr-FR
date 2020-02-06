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
description: 'L’applet de commande Exit-CcUpdate effectue un mode maintenance de la mise à jour sur le serveur hôte de la version Cloud Connector de Skype Entreprise. '
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801764"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="bf9e9-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="bf9e9-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="bf9e9-104">L’applet de commande Exit-CcUpdate effectue un mode maintenance de la mise à jour sur le serveur hôte de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="bf9e9-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="bf9e9-105">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="bf9e9-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="bf9e9-106">Parameters</span></span>

<span data-ttu-id="bf9e9-107">Aucun</span><span class="sxs-lookup"><span data-stu-id="bf9e9-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="bf9e9-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="bf9e9-108">Examples</span></span>
<span data-ttu-id="bf9e9-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9e9-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="bf9e9-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="bf9e9-110">Example 1</span></span>

<span data-ttu-id="bf9e9-111">La commande suivante remet l’appliance en mode production : </span><span class="sxs-lookup"><span data-stu-id="bf9e9-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="bf9e9-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="bf9e9-112">Detailed Description</span></span>
<span data-ttu-id="bf9e9-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9e9-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="bf9e9-114">Si vous disposez d’appliances que vous avez mises en mode maintenance en spécifiant l’applet de commande Enter-CcUpdate, l'applet de commande Exit-CcUpdate les mettra à nouveau en mode production. </span><span class="sxs-lookup"><span data-stu-id="bf9e9-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="bf9e9-115">Pour plus d’informations sur la manière de mettre les appliances en mode maintenance, reportez-vous à la rubrique Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="bf9e9-116">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="bf9e9-116">Input Types</span></span>
<span data-ttu-id="bf9e9-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9e9-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="bf9e9-p101">Aucun. L’applet de commande Exit-CcUpdate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bf9e9-120">Types de retours</span><span class="sxs-lookup"><span data-stu-id="bf9e9-120">Return Types</span></span>
<span data-ttu-id="bf9e9-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9e9-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="bf9e9-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="bf9e9-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bf9e9-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf9e9-123">See also</span></span>
<span data-ttu-id="bf9e9-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bf9e9-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="bf9e9-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="bf9e9-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

