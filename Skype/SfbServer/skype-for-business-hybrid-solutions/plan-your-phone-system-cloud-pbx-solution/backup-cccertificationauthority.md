---
title: Backup-CcCertificationAuthority
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
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: L'applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification de la version Cloud Connector de Skype Entreprise sur un fichier et l'enregistre dans le dossier AC sous l’annuaire de sites.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803804"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="50e5b-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="50e5b-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="50e5b-104">L'applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification de la version Cloud Connector de Skype Entreprise sur un fichier et l'enregistre dans le dossier AC sous l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="50e5b-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="50e5b-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="50e5b-105">Parameters</span></span>

<span data-ttu-id="50e5b-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="50e5b-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="50e5b-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="50e5b-107">Examples</span></span>
<span data-ttu-id="50e5b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50e5b-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="50e5b-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="50e5b-109">Example 1</span></span>

<span data-ttu-id="50e5b-110">L’exemple suivant sauvegarde le service d’autorité de certification sur un fichier et l’enregistre dans un dossier AC sous l’annuaire de sites :</span><span class="sxs-lookup"><span data-stu-id="50e5b-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="50e5b-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="50e5b-111">Detailed Description</span></span>
<span data-ttu-id="50e5b-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50e5b-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="50e5b-113">La sauvegarde d’une autorité de certification peut être utile si vous envisagez de redéployer un appareil Cloud Connector avec le même certificat en cas de sinistre, ou si vous voulez déplacer l’appareil vers un nouveau matériel.</span><span class="sxs-lookup"><span data-stu-id="50e5b-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="50e5b-114">La commande enregistre la copie du service de certification de certification Cloud du serveur AD pour «\<SITEROOTDIRECTORY\>\CA\SfB CCE root. P12 ».</span><span class="sxs-lookup"><span data-stu-id="50e5b-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="50e5b-115">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="50e5b-115">Input Types</span></span>
<span data-ttu-id="50e5b-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50e5b-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="50e5b-p102">Aucun. L’applet de commande Backup-CcCertificationAuthority n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="50e5b-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="50e5b-119">Types de retours</span><span class="sxs-lookup"><span data-stu-id="50e5b-119">Return Types</span></span>
<span data-ttu-id="50e5b-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50e5b-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="50e5b-121">Aucun</span><span class="sxs-lookup"><span data-stu-id="50e5b-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50e5b-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50e5b-122">See also</span></span>
<span data-ttu-id="50e5b-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50e5b-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="50e5b-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="50e5b-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

