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
description: LBackup-CcCertificationAuthority cmdlet sauvegarde le service d’autorité de certification Skype Entreprise, version Cloud Connector, dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803804"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="4385b-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="4385b-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="4385b-104">LBackup-CcCertificationAuthority cmdlet sauvegarde le service d’autorité de certification Skype Entreprise, version Cloud Connector, dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.</span><span class="sxs-lookup"><span data-stu-id="4385b-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="4385b-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="4385b-105">Parameters</span></span>

<span data-ttu-id="4385b-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="4385b-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4385b-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="4385b-107">Examples</span></span>
<span data-ttu-id="4385b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4385b-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4385b-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="4385b-109">Example 1</span></span>

<span data-ttu-id="4385b-110">L’exemple suivant sauvegarde le service d’autorité de certification dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites :</span><span class="sxs-lookup"><span data-stu-id="4385b-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="4385b-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="4385b-111">Detailed Description</span></span>
<span data-ttu-id="4385b-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4385b-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4385b-113">La sauvegarde de l’autorité de certification peut être utile si vous envisagez de redéployer une appliance Cloud Connector avec le même certificat en cas d’urgence, ou si vous souhaitez déplacer l’appliance vers un nouveau matériel.</span><span class="sxs-lookup"><span data-stu-id="4385b-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="4385b-114">La commande enregistre la copie du service d’autorité de certification Cloud Connector du serveur AD vers « \< SiteRootDirectory \> \CA\SfB CCE Root.p12 ».</span><span class="sxs-lookup"><span data-stu-id="4385b-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4385b-115">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="4385b-115">Input Types</span></span>
<span data-ttu-id="4385b-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4385b-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4385b-117">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4385b-117">None.</span></span> <span data-ttu-id="4385b-118">La cmdlet Backup-CcCertificationAuthority n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="4385b-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4385b-119">Types de retour</span><span class="sxs-lookup"><span data-stu-id="4385b-119">Return Types</span></span>
<span data-ttu-id="4385b-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4385b-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4385b-121">Aucun</span><span class="sxs-lookup"><span data-stu-id="4385b-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4385b-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4385b-122">See also</span></span>
<span data-ttu-id="4385b-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4385b-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4385b-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="4385b-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

