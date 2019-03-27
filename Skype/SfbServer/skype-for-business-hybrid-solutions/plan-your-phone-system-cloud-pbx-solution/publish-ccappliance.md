---
title: Publish-CcAppliance
ms.reviewer: ''
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
ms.openlocfilehash: 119b5e816555eedf221d9db06be15e6a778936d4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879804"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="1b4fd-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1b4fd-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="1b4fd-104">L’applet de commande Publish-CcAppliance apporte des informations haute disponibilité à partir de la configuration client en ligne et les publie dans l’appliance du serveur hôte de la version Cloud Connector de Skype Entreprise. </span><span class="sxs-lookup"><span data-stu-id="1b4fd-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="1b4fd-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1b4fd-105">Parameters</span></span>

<span data-ttu-id="1b4fd-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="1b4fd-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1b4fd-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="1b4fd-107">Examples</span></span>
<span data-ttu-id="1b4fd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1b4fd-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="1b4fd-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="1b4fd-109">Example 1</span></span>

<span data-ttu-id="1b4fd-110">L’exemple suivant obtient des informations de disponibilité à partir de la configuration du client en ligne et publie dans l’application dans le nuage connecteur sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="1b4fd-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="1b4fd-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="1b4fd-111">Detailed Description</span></span>
<span data-ttu-id="1b4fd-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1b4fd-112"></span></span>

<span data-ttu-id="1b4fd-p101">Les informations sur la haute disponibilité contiennent les noms de domaine complets du serveur de médiation et les adresses IP du site RTC. Les nouveaux enregistrements DNS A sont ajoutés au serveur AD pour les adresses IP du serveur de médiation. Les options de la nouvelle topologie sont mises à jour dans le magasin central de gestion pour les noms de domaine complets et les adresses IP du serveur de médiation. </span><span class="sxs-lookup"><span data-stu-id="1b4fd-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="1b4fd-116">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="1b4fd-116">Input Types</span></span>
<span data-ttu-id="1b4fd-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b4fd-117"></span></span>

<span data-ttu-id="1b4fd-118">Aucun.</span><span class="sxs-lookup"><span data-stu-id="1b4fd-118">None.</span></span> <span data-ttu-id="1b4fd-119">L’applet de commande Publish-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="1b4fd-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1b4fd-120">Types de retours</span><span class="sxs-lookup"><span data-stu-id="1b4fd-120">Return Types</span></span>
<span data-ttu-id="1b4fd-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b4fd-121"></span></span>

<span data-ttu-id="1b4fd-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="1b4fd-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b4fd-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b4fd-123">See also</span></span>
<span data-ttu-id="1b4fd-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1b4fd-124"></span></span>

[<span data-ttu-id="1b4fd-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1b4fd-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="1b4fd-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1b4fd-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="1b4fd-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1b4fd-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="1b4fd-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1b4fd-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

