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
description: L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824188"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="2edc0-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2edc0-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="2edc0-105">L’applet de commande Set-CcSiteDirectory définit le répertoire dans lequel les fichiers de configuration de niveau site pour la version Cloud Connector de Skype Entreprise sont conservés.</span><span class="sxs-lookup"><span data-stu-id="2edc0-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="2edc0-106">Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2edc0-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="2edc0-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2edc0-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="2edc0-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="2edc0-108">Examples</span></span>
<span data-ttu-id="2edc0-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2edc0-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2edc0-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="2edc0-110">Example 1</span></span>

<span data-ttu-id="2edc0-111">L’exemple suivant définit le répertoire racine du site \\sur SiteShare\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="2edc0-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="2edc0-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="2edc0-112">Detailed Description</span></span>
<span data-ttu-id="2edc0-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2edc0-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2edc0-114">Pour fournir une affinité et une haute disponibilité de la passerelle, les appareils de connexion Cloud peuvent être combinés dans les sites.</span><span class="sxs-lookup"><span data-stu-id="2edc0-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="2edc0-115">Les utilisateurs sont affectés à des sites au lieu de périphériques Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2edc0-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="2edc0-116">Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2edc0-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="2edc0-117">Les appareils utilisent ce dossier lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="2edc0-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="2edc0-118">Ce dossier doit être partagé avec toutes les autres applications dans un site Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2edc0-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="2edc0-119">Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="2edc0-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="2edc0-120">Le chemin d’accès est visible à l’aide de l’applet de commande Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="2edc0-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2edc0-121">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2edc0-121">Parameters</span></span>
<span data-ttu-id="2edc0-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2edc0-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="2edc0-123">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="2edc0-123">**Parameter**</span></span>|<span data-ttu-id="2edc0-124">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="2edc0-124">**Required**</span></span>|<span data-ttu-id="2edc0-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="2edc0-125">**Type**</span></span>|<span data-ttu-id="2edc0-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="2edc0-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2edc0-127"> Path</span><span class="sxs-lookup"><span data-stu-id="2edc0-127">Path</span></span> <br/> | <span data-ttu-id="2edc0-128">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2edc0-128">Required</span></span> <br/> | <span data-ttu-id="2edc0-129">System.String</span><span class="sxs-lookup"><span data-stu-id="2edc0-129">System.String</span></span> <br/> |<span data-ttu-id="2edc0-130">Indique le chemin d’accès du dossier dans lequel les fichiers de site Cloud Connector seront stockés.</span><span class="sxs-lookup"><span data-stu-id="2edc0-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2edc0-131">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="2edc0-131">Input Types</span></span>
<span data-ttu-id="2edc0-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2edc0-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2edc0-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="2edc0-133">None.</span></span> <span data-ttu-id="2edc0-134">L’applet de commande Set-CcSiteDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="2edc0-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2edc0-135">Types de retours</span><span class="sxs-lookup"><span data-stu-id="2edc0-135">Return Types</span></span>
<span data-ttu-id="2edc0-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2edc0-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2edc0-137">Aucun</span><span class="sxs-lookup"><span data-stu-id="2edc0-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2edc0-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2edc0-138">See also</span></span>
<span data-ttu-id="2edc0-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2edc0-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2edc0-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2edc0-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

