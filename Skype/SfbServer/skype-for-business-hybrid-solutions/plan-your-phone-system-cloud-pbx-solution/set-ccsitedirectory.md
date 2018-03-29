---
title: Ensemble-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="ef235-104">Ensemble-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="ef235-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="ef235-105">L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés.</span><span class="sxs-lookup"><span data-stu-id="ef235-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="ef235-106">Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ef235-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="ef235-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ef235-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="ef235-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="ef235-108">Examples</span></span>
<span data-ttu-id="ef235-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ef235-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="ef235-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ef235-110">Example 1</span></span>

<span data-ttu-id="ef235-111">L’exemple suivant définit le répertoire racine du site \\SiteShare\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="ef235-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="ef235-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="ef235-112">Detailed Description</span></span>
<span data-ttu-id="ef235-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ef235-113"></span></span>

<span data-ttu-id="ef235-114">Pour fournir une affinité de passerelle et de haute disponibilité, appareils de nuage connecteur peuvent être combinés dans des sites.</span><span class="sxs-lookup"><span data-stu-id="ef235-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="ef235-115">Les utilisateurs sont affectés à des sites plutôt que des appareils de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="ef235-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="ef235-116">Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ef235-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="ef235-117">Appliances utilisent ce dossier pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef235-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="ef235-118">Ce dossier doit être partagé avec tous les autres équipements dans un site connecteur du nuage.</span><span class="sxs-lookup"><span data-stu-id="ef235-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="ef235-119">Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="ef235-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="ef235-120">Le chemin d’accès est visible à l’aide de l’applet de commande Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="ef235-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ef235-121">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ef235-121">Parameters</span></span>
<span data-ttu-id="ef235-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ef235-122"></span></span>

|<span data-ttu-id="ef235-123">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ef235-123">**Parameter**</span></span>|<span data-ttu-id="ef235-124">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="ef235-124">**Required**</span></span>|<span data-ttu-id="ef235-125">**Type de**</span><span class="sxs-lookup"><span data-stu-id="ef235-125">**Type**</span></span>|<span data-ttu-id="ef235-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="ef235-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ef235-127"> Path</span><span class="sxs-lookup"><span data-stu-id="ef235-127">Path</span></span> <br/> | <span data-ttu-id="ef235-128">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="ef235-128">Required</span></span> <br/> | <span data-ttu-id="ef235-129">System.String</span><span class="sxs-lookup"><span data-stu-id="ef235-129">System.String</span></span> <br/> |<span data-ttu-id="ef235-130">Fournit le chemin d’accès au dossier où seront stockés les fichiers du site connecteur du nuage.</span><span class="sxs-lookup"><span data-stu-id="ef235-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ef235-131">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="ef235-131">Input Types</span></span>
<span data-ttu-id="ef235-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef235-132"></span></span>

<span data-ttu-id="ef235-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="ef235-133">None.</span></span> <span data-ttu-id="ef235-134">L’applet de commande Set-CcSiteDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="ef235-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ef235-135">Types de retours</span><span class="sxs-lookup"><span data-stu-id="ef235-135">Return Types</span></span>
<span data-ttu-id="ef235-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef235-136"></span></span>

<span data-ttu-id="ef235-137">Aucun</span><span class="sxs-lookup"><span data-stu-id="ef235-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef235-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef235-138">See also</span></span>
<span data-ttu-id="ef235-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ef235-139"></span></span>

[<span data-ttu-id="ef235-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="ef235-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

