---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: La cmdlet Get-CcSiteDirectory affiche le répertoire actuel dans lequel les fichiers de configuration au niveau du site sont stockés. Le dossier contient les fichiers d’installation vhD de base et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799864"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="ac85c-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="ac85c-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="ac85c-106">La cmdlet Get-CcSiteDirectory affiche le répertoire actuel dans lequel les fichiers de configuration au niveau du site sont stockés.</span><span class="sxs-lookup"><span data-stu-id="ac85c-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="ac85c-107">Le dossier contient les fichiers d’installation vhD de base et Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ac85c-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="ac85c-108">Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ac85c-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="ac85c-109">Cette cmdlet s’applique à Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ac85c-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="ac85c-110">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ac85c-110">Parameters</span></span>

<span data-ttu-id="ac85c-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="ac85c-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ac85c-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="ac85c-112">Examples</span></span>
<span data-ttu-id="ac85c-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ac85c-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ac85c-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ac85c-114">Example 1</span></span>

<span data-ttu-id="ac85c-115">L’exemple suivant montre le dossier actuel dans lequel sont stockés les fichiers de configuration et de machines virtuelles des composants Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="ac85c-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="ac85c-116">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="ac85c-116">Detailed Description</span></span>
<span data-ttu-id="ac85c-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ac85c-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ac85c-118">Pour fournir une affinité de passerelle et une haute disponibilité, les appliances Cloud Connector peuvent être combinées dans des sites.</span><span class="sxs-lookup"><span data-stu-id="ac85c-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="ac85c-119">Les utilisateurs sont affectés à des sites au lieu d’appliances Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ac85c-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="ac85c-120">Chaque site possède un dossier partagé dans lequel sont stockés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ac85c-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="ac85c-121">Les appliances utilisent ce dossier pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ac85c-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="ac85c-122">Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="ac85c-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="ac85c-123">Vous pouvez modifier le chemin d’accès à l’aide Set-CcSiteDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ac85c-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ac85c-124">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="ac85c-124">Input Types</span></span>
<span data-ttu-id="ac85c-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ac85c-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ac85c-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="ac85c-126">None.</span></span> <span data-ttu-id="ac85c-127">La cmdlet Get-CcSiteDirectory n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="ac85c-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ac85c-128">Types de retour</span><span class="sxs-lookup"><span data-stu-id="ac85c-128">Return Types</span></span>
<span data-ttu-id="ac85c-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ac85c-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ac85c-130">Cette commande renvoie un chemin d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="ac85c-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac85c-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac85c-131">See also</span></span>
<span data-ttu-id="ac85c-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ac85c-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ac85c-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="ac85c-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

