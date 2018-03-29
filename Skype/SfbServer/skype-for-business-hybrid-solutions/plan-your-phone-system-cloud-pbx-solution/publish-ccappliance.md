---
title: Publication-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'L’applet de commande Publish-CcAppliance apporte des informations haute disponibilité à partir de la configuration client en ligne et les publie dans l’appliance du serveur hôte de la version Cloud Connector de Skype Entreprise. '
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a><span data-ttu-id="bbd25-103">Publication-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="bbd25-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="bbd25-104">L’applet de commande Publish-CcAppliance apporte des informations haute disponibilité à partir de la configuration client en ligne et les publie dans l’appliance du serveur hôte de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="bbd25-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="bbd25-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="bbd25-105">Parameters</span></span>

<span data-ttu-id="bbd25-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="bbd25-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="bbd25-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="bbd25-107">Examples</span></span>
<span data-ttu-id="bbd25-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bbd25-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="bbd25-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="bbd25-109">Example 1</span></span>

<span data-ttu-id="bbd25-110">L’exemple suivant obtient les informations de disponibilité à partir de la configuration des clients en ligne et le publie à l’appliance de nuage connecteur sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="bbd25-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="bbd25-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="bbd25-111">Detailed Description</span></span>
<span data-ttu-id="bbd25-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bbd25-112"></span></span>

<span data-ttu-id="bbd25-p101">Les informations sur la haute disponibilité contiennent les noms de domaine complets du serveur de médiation et les adresses IP du site RTC. Les nouveaux enregistrements DNS A sont ajoutés au serveur AD pour les adresses IP du serveur de médiation. Les options de la nouvelle topologie sont mises à jour dans le magasin central de gestion pour les noms de domaine complets et les adresses IP du serveur de médiation. </span><span class="sxs-lookup"><span data-stu-id="bbd25-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="bbd25-116">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="bbd25-116">Input Types</span></span>
<span data-ttu-id="bbd25-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bbd25-117"></span></span>

<span data-ttu-id="bbd25-118">Aucun.</span><span class="sxs-lookup"><span data-stu-id="bbd25-118">None.</span></span> <span data-ttu-id="bbd25-119">L’applet de commande Publish-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="bbd25-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bbd25-120">Types de retours</span><span class="sxs-lookup"><span data-stu-id="bbd25-120">Return Types</span></span>
<span data-ttu-id="bbd25-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bbd25-121"></span></span>

<span data-ttu-id="bbd25-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="bbd25-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbd25-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbd25-123">See also</span></span>
<span data-ttu-id="bbd25-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bbd25-124"></span></span>

[<span data-ttu-id="bbd25-125">Installation-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="bbd25-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="bbd25-126">CcAppliance-désinstaller</span><span class="sxs-lookup"><span data-stu-id="bbd25-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="bbd25-127">Registre-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="bbd25-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="bbd25-128">Annuler l’inscription-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="bbd25-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

