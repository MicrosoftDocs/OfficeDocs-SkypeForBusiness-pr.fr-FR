---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'L’applet de commande Get-CcSiteLogDirectory montre l’annuaire actuel où les journaux de niveau de site de la version Cloud Connector de Skype Entreprise sont conservés. '
ms.openlocfilehash: c4354920ac25d076e550c5eda3a641eef0c8b900
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199075"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="15342-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="15342-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="15342-104">L’applet de commande Get-CcSiteLogDirectory montre l’annuaire actuel où les journaux de niveau de site de la version Cloud Connector de Skype Entreprise sont conservés. </span><span class="sxs-lookup"><span data-stu-id="15342-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="15342-105">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="15342-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="15342-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="15342-106">Parameters</span></span>

<span data-ttu-id="15342-107">Aucun</span><span class="sxs-lookup"><span data-stu-id="15342-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="15342-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="15342-108">Examples</span></span>
<span data-ttu-id="15342-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="15342-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="15342-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="15342-110">Example 1</span></span>

<span data-ttu-id="15342-111">L’exemple suivant montre le dossier actif où sont stockés les fichiers journaux pour le site de connecteur dans le nuage :</span><span class="sxs-lookup"><span data-stu-id="15342-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="15342-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="15342-112">Detailed Description</span></span>
<span data-ttu-id="15342-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="15342-113"></span></span>

<span data-ttu-id="15342-114">Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="15342-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="15342-115">Vous pouvez modifier le dossier en exécutant l’applet de commande Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="15342-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="15342-116">Il n’existe pas d’applet de commande distincte qui modifie uniquement l’emplacement du dossier de connexion sans modifier l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="15342-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="15342-117">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="15342-117">Input Types</span></span>
<span data-ttu-id="15342-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="15342-118"></span></span>

<span data-ttu-id="15342-p102">Aucun. L’applet de commande Get-CcSiteLogDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="15342-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="15342-121">Types de retours</span><span class="sxs-lookup"><span data-stu-id="15342-121">Return Types</span></span>
<span data-ttu-id="15342-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="15342-122"></span></span>

<span data-ttu-id="15342-123">La commande renvoie un chemin d’accès de fichier.</span><span class="sxs-lookup"><span data-stu-id="15342-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15342-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15342-124">See also</span></span>
<span data-ttu-id="15342-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="15342-125"></span></span>

[<span data-ttu-id="15342-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="15342-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

