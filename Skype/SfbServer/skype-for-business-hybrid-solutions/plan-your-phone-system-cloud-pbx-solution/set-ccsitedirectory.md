---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: La cmdlet Set-CcSiteDirectory définit l’annuaire dans lequel les fichiers de configuration au niveau du site pour Skype Entreprise, version Cloud Connector seront stockés. Le dossier contient les fichiers de configuration vhD de base et Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824188"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="8be62-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="8be62-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="8be62-105">La cmdlet Set-CcSiteDirectory définit l’annuaire dans lequel les fichiers de configuration au niveau du site pour Skype Entreprise, version Cloud Connector seront stockés.</span><span class="sxs-lookup"><span data-stu-id="8be62-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="8be62-106">Le dossier contient les fichiers de configuration vhD de base et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8be62-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="8be62-107">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="8be62-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="8be62-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="8be62-108">Examples</span></span>
<span data-ttu-id="8be62-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8be62-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8be62-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8be62-110">Example 1</span></span>

<span data-ttu-id="8be62-111">L’exemple suivant définit le répertoire racine du site \\ sur SiteShare\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="8be62-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="8be62-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="8be62-112">Detailed Description</span></span>
<span data-ttu-id="8be62-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8be62-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8be62-114">Pour fournir une affinité de passerelle et une haute disponibilité, les appliances Cloud Connector peuvent être combinées dans des sites.</span><span class="sxs-lookup"><span data-stu-id="8be62-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="8be62-115">Les utilisateurs sont affectés à des sites au lieu d’appliances Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8be62-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="8be62-116">Chaque site possède un dossier partagé dans lequel sont stockés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8be62-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="8be62-117">Les appliances utilisent ce dossier pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8be62-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="8be62-118">Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8be62-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="8be62-119">Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="8be62-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="8be62-120">Le chemin d’accès peut être vu à l’aide Get-CcSiteDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8be62-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8be62-121">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8be62-121">Parameters</span></span>
<span data-ttu-id="8be62-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8be62-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="8be62-123">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8be62-123">**Parameter**</span></span>|<span data-ttu-id="8be62-124">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="8be62-124">**Required**</span></span>|<span data-ttu-id="8be62-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="8be62-125">**Type**</span></span>|<span data-ttu-id="8be62-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="8be62-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8be62-127">Path</span><span class="sxs-lookup"><span data-stu-id="8be62-127">Path</span></span> <br/> | <span data-ttu-id="8be62-128">Requis</span><span class="sxs-lookup"><span data-stu-id="8be62-128">Required</span></span> <br/> | <span data-ttu-id="8be62-129">System.String</span><span class="sxs-lookup"><span data-stu-id="8be62-129">System.String</span></span> <br/> |<span data-ttu-id="8be62-130">Fournit le chemin d’accès au dossier dans lequel les fichiers de site Cloud Connector seront stockés.</span><span class="sxs-lookup"><span data-stu-id="8be62-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8be62-131">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="8be62-131">Input Types</span></span>
<span data-ttu-id="8be62-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8be62-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8be62-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8be62-133">None.</span></span> <span data-ttu-id="8be62-134">La cmdlet Set-CcSiteDirectory n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="8be62-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8be62-135">Types de retour</span><span class="sxs-lookup"><span data-stu-id="8be62-135">Return Types</span></span>
<span data-ttu-id="8be62-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8be62-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8be62-137">Aucun</span><span class="sxs-lookup"><span data-stu-id="8be62-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8be62-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8be62-138">See also</span></span>
<span data-ttu-id="8be62-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8be62-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="8be62-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="8be62-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

