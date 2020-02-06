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
description: L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector. Ce dossier doit être partagé avec toutes les autres applications d’un site Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799864"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="778b1-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="778b1-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="778b1-106">L’applet de commande Get-CcSiteDirectory affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site.</span><span class="sxs-lookup"><span data-stu-id="778b1-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="778b1-107">Le dossier contient les fichiers d’installation de base de VHD et Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="778b1-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="778b1-108">Ce dossier doit être partagé avec toutes les autres applications d’un site Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="778b1-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="778b1-109">Cette applet de commande s’applique à Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="778b1-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="778b1-110">Paramètres</span><span class="sxs-lookup"><span data-stu-id="778b1-110">Parameters</span></span>

<span data-ttu-id="778b1-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="778b1-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="778b1-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="778b1-112">Examples</span></span>
<span data-ttu-id="778b1-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="778b1-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="778b1-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="778b1-114">Example 1</span></span>

<span data-ttu-id="778b1-115">L’exemple suivant montre le dossier actuel dans lequel se trouvent les fichiers de configuration et d’ordinateurs virtuels des composants Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="778b1-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="778b1-116">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="778b1-116">Detailed Description</span></span>
<span data-ttu-id="778b1-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="778b1-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="778b1-118">Pour fournir une affinité et une haute disponibilité de la passerelle, les appareils de connexion Cloud peuvent être combinés dans les sites.</span><span class="sxs-lookup"><span data-stu-id="778b1-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="778b1-119">Les utilisateurs sont affectés à des sites au lieu de périphériques Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="778b1-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="778b1-120">Chaque site possède un dossier partagé dans lequel sont conservés les fichiers d’installation de base de VHD et Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="778b1-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="778b1-121">Les appareils utilisent ce dossier lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="778b1-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="778b1-122">Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="778b1-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="778b1-123">Vous pouvez modifier le chemin d’accès à l’aide de l’applet de commande Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="778b1-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="778b1-124">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="778b1-124">Input Types</span></span>
<span data-ttu-id="778b1-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="778b1-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="778b1-p104">Aucun. L’applet de commande Get-CcSiteDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="778b1-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="778b1-128">Types de retours</span><span class="sxs-lookup"><span data-stu-id="778b1-128">Return Types</span></span>
<span data-ttu-id="778b1-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="778b1-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="778b1-130">Cette commande renvoie un chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="778b1-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="778b1-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="778b1-131">See also</span></span>
<span data-ttu-id="778b1-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="778b1-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="778b1-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="778b1-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

