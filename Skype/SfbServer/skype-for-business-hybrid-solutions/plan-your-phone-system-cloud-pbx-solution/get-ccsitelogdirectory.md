---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: La cmdlet Get-CcSiteLogDirectory affiche l’annuaire actuel dans lequel sont stockés les journaux au niveau du site pour Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799884"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="d386e-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="d386e-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="d386e-104">La cmdlet Get-CcSiteLogDirectory affiche l’annuaire actuel dans lequel sont stockés les journaux au niveau du site pour Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d386e-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="d386e-105">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="d386e-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="d386e-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d386e-106">Parameters</span></span>

<span data-ttu-id="d386e-107">Aucun</span><span class="sxs-lookup"><span data-stu-id="d386e-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d386e-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="d386e-108">Examples</span></span>
<span data-ttu-id="d386e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d386e-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d386e-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="d386e-110">Example 1</span></span>

<span data-ttu-id="d386e-111">L’exemple suivant montre le dossier actuel dans lequel les fichiers journaux du site Cloud Connector sont stockés :</span><span class="sxs-lookup"><span data-stu-id="d386e-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="d386e-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="d386e-112">Detailed Description</span></span>
<span data-ttu-id="d386e-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d386e-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d386e-114">Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="d386e-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="d386e-115">Vous pouvez modifier le dossier en exécutant l'Set-CcSiteDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d386e-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="d386e-116">Il n’existe aucune cmdlet distincte qui modifie uniquement l’emplacement du dossier journal sans modifier l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="d386e-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d386e-117">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="d386e-117">Input Types</span></span>
<span data-ttu-id="d386e-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d386e-118"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d386e-119">Aucun.</span><span class="sxs-lookup"><span data-stu-id="d386e-119">None.</span></span> <span data-ttu-id="d386e-120">La cmdlet Get-CcSiteLogDirectory n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="d386e-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d386e-121">Types de retour</span><span class="sxs-lookup"><span data-stu-id="d386e-121">Return Types</span></span>
<span data-ttu-id="d386e-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d386e-122"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d386e-123">La commande renvoie un chemin d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="d386e-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d386e-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d386e-124">See also</span></span>
<span data-ttu-id="d386e-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d386e-125"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d386e-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="d386e-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

