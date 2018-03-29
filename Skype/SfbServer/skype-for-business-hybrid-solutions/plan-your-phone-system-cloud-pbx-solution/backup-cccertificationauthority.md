---
title: Sauvegarde-CcCertificationAuthority
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: L'applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification de la version Cloud Connector de Skype Entreprise sur un fichier et l'enregistre dans le dossier AC sous l’annuaire de sites.
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="33c22-103">Sauvegarde-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="33c22-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="33c22-104">L'applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification de la version Cloud Connector de Skype Entreprise sur un fichier et l'enregistre dans le dossier AC sous l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="33c22-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="33c22-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="33c22-105">Parameters</span></span>

<span data-ttu-id="33c22-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="33c22-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="33c22-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="33c22-107">Examples</span></span>
<span data-ttu-id="33c22-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="33c22-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="33c22-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="33c22-109">Example 1</span></span>

<span data-ttu-id="33c22-110">L’exemple suivant sauvegarde le service d’autorité de certification sur un fichier et l’enregistre dans un dossier AC sous l’annuaire de sites :</span><span class="sxs-lookup"><span data-stu-id="33c22-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="33c22-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="33c22-111">Detailed Description</span></span>
<span data-ttu-id="33c22-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="33c22-112"></span></span>

<span data-ttu-id="33c22-113">Sauvegarde d’autorité de certification peut être utile si vous prévoyez de redéployer une solution matérielle-logicielle connecteur de nuage avec le même certificat en cas de sinistre, ou si vous souhaitez déplacer l’application vers un nouveau matériel.</span><span class="sxs-lookup"><span data-stu-id="33c22-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="33c22-114">La commande enregistre la copie du service d’autorité de certification Cloud connecteur à partir du serveur Active Directory pour "\<SiteRootDirectory\>\CA\SfB CCE Root.p12 ».</span><span class="sxs-lookup"><span data-stu-id="33c22-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="33c22-115">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="33c22-115">Input Types</span></span>
<span data-ttu-id="33c22-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="33c22-116"></span></span>

<span data-ttu-id="33c22-p102">Aucun. L’applet de commande Backup-CcCertificationAuthority n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="33c22-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="33c22-119">Types de retours</span><span class="sxs-lookup"><span data-stu-id="33c22-119">Return Types</span></span>
<span data-ttu-id="33c22-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="33c22-120"></span></span>

<span data-ttu-id="33c22-121">Aucun</span><span class="sxs-lookup"><span data-stu-id="33c22-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="33c22-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33c22-122">See also</span></span>
<span data-ttu-id="33c22-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="33c22-123"></span></span>

[<span data-ttu-id="33c22-124">Supprimer-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="33c22-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

