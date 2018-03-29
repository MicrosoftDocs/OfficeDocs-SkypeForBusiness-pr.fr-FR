---
title: Get-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec tous les autres équipements d’un site connecteur du nuage.
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="9a516-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="9a516-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="9a516-106">L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site.</span><span class="sxs-lookup"><span data-stu-id="9a516-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="9a516-107">Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9a516-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="9a516-108">Ce dossier doit être partagé avec tous les autres équipements d’un site connecteur du nuage.</span><span class="sxs-lookup"><span data-stu-id="9a516-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="9a516-109">Cette applet de commande s’applique à Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="9a516-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="9a516-110">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9a516-110">Parameters</span></span>

<span data-ttu-id="9a516-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="9a516-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9a516-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="9a516-112">Examples</span></span>
<span data-ttu-id="9a516-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9a516-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="9a516-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="9a516-114">Example 1</span></span>

<span data-ttu-id="9a516-115">L’exemple suivant affiche le dossier en cours, où se trouvent les fichiers de configuration et les machines virtuelles de composants du connecteur du nuage :</span><span class="sxs-lookup"><span data-stu-id="9a516-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="9a516-116">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="9a516-116">Detailed Description</span></span>
<span data-ttu-id="9a516-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9a516-117"></span></span>

<span data-ttu-id="9a516-118">Pour fournir une affinité de passerelle et de haute disponibilité, appareils de nuage connecteur peuvent être combinés dans des sites.</span><span class="sxs-lookup"><span data-stu-id="9a516-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="9a516-119">Les utilisateurs sont affectés à des sites plutôt que des appareils de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="9a516-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="9a516-120">Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9a516-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="9a516-121">Appliances utilisent ce dossier pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="9a516-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="9a516-122">Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="9a516-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="9a516-123">Vous pouvez modifier le chemin d’accès à l’aide de l’applet de commande Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="9a516-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9a516-124">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="9a516-124">Input Types</span></span>
<span data-ttu-id="9a516-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a516-125"></span></span>

<span data-ttu-id="9a516-p104">Aucun. L’applet de commande Get-CcSiteDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="9a516-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9a516-128">Types de retours</span><span class="sxs-lookup"><span data-stu-id="9a516-128">Return Types</span></span>
<span data-ttu-id="9a516-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a516-129"></span></span>

<span data-ttu-id="9a516-130">Cette commande renvoie un chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="9a516-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a516-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a516-131">See also</span></span>
<span data-ttu-id="9a516-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a516-132"></span></span>

[<span data-ttu-id="9a516-133">Ensemble-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="9a516-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

