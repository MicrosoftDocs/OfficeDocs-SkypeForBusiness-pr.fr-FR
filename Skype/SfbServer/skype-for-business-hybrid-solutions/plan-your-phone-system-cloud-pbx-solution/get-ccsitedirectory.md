---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec tous les autres équipements d’un site dans le nuage connecteur.
ms.openlocfilehash: d0869f3cbd1c43e523107a0ff8dce6fd769889a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882396"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="106bb-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="106bb-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="106bb-106">L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site.</span><span class="sxs-lookup"><span data-stu-id="106bb-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="106bb-107">Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="106bb-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="106bb-108">Ce dossier doit être partagé avec tous les autres équipements d’un site dans le nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="106bb-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="106bb-109">Cette applet de commande s’applique à Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="106bb-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="106bb-110">Paramètres</span><span class="sxs-lookup"><span data-stu-id="106bb-110">Parameters</span></span>

<span data-ttu-id="106bb-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="106bb-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="106bb-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="106bb-112">Examples</span></span>
<span data-ttu-id="106bb-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="106bb-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="106bb-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="106bb-114">Example 1</span></span>

<span data-ttu-id="106bb-115">L’exemple suivant montre le dossier actif où sont stockés les fichiers de configuration et les machines virtuelles des composants de connecteur dans le nuage :</span><span class="sxs-lookup"><span data-stu-id="106bb-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="106bb-116">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="106bb-116">Detailed Description</span></span>
<span data-ttu-id="106bb-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="106bb-117"></span></span>

<span data-ttu-id="106bb-118">Pour fournir une haute disponibilité et l’affinité de passerelle, appliances nuage connecteur peuvent être combinés dans les sites.</span><span class="sxs-lookup"><span data-stu-id="106bb-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="106bb-119">Les utilisateurs sont affectés à des sites au lieu d’appliances nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="106bb-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="106bb-120">Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="106bb-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="106bb-121">Appliances utilisent ce dossier lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="106bb-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="106bb-122">Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="106bb-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="106bb-123">Vous pouvez modifier le chemin d’accès à l’aide de l’applet de commande Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="106bb-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="106bb-124">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="106bb-124">Input Types</span></span>
<span data-ttu-id="106bb-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="106bb-125"></span></span>

<span data-ttu-id="106bb-p104">Aucun. L’applet de commande Get-CcSiteDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="106bb-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="106bb-128">Types de retours</span><span class="sxs-lookup"><span data-stu-id="106bb-128">Return Types</span></span>
<span data-ttu-id="106bb-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="106bb-129"></span></span>

<span data-ttu-id="106bb-130">Cette commande renvoie un chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="106bb-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="106bb-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="106bb-131">See also</span></span>
<span data-ttu-id="106bb-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="106bb-132"></span></span>

[<span data-ttu-id="106bb-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="106bb-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

