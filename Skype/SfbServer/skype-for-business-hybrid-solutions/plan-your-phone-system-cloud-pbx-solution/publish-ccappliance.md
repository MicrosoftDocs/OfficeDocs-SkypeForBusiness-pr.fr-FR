---
title: Publish-CcAppliance
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
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: LPublish-CcAppliance cmdlet obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector de Skype Entreprise sur le serveur hôte.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824310"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="1c5ab-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1c5ab-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="1c5ab-104">LPublish-CcAppliance cmdlet obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector de Skype Entreprise sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="1c5ab-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1c5ab-105">Parameters</span></span>

<span data-ttu-id="1c5ab-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="1c5ab-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1c5ab-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="1c5ab-107">Examples</span></span>
<span data-ttu-id="1c5ab-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5ab-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1c5ab-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="1c5ab-109">Example 1</span></span>

<span data-ttu-id="1c5ab-110">L’exemple suivant obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="1c5ab-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="1c5ab-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="1c5ab-111">Detailed Description</span></span>
<span data-ttu-id="1c5ab-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5ab-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1c5ab-113">Les informations de haute disponibilité contiennent les FQDN du serveur de médiation et les adresses IP du site PSTN.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="1c5ab-114">De nouveaux enregistrements DNS A sont ajoutés au serveur AD pour les adresses IP du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="1c5ab-115">Les nouveaux éléments de topologie sont mis à jour dans le magasin central de gestion pour les noms de service et les adresses IP du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="1c5ab-116">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="1c5ab-116">Input Types</span></span>
<span data-ttu-id="1c5ab-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5ab-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1c5ab-118">Aucun.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-118">None.</span></span> <span data-ttu-id="1c5ab-119">La cmdlet Publish-CcAppliance n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1c5ab-120">Types de retour</span><span class="sxs-lookup"><span data-stu-id="1c5ab-120">Return Types</span></span>
<span data-ttu-id="1c5ab-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5ab-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1c5ab-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="1c5ab-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c5ab-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c5ab-123">See also</span></span>
<span data-ttu-id="1c5ab-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5ab-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1c5ab-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1c5ab-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="1c5ab-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1c5ab-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="1c5ab-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1c5ab-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="1c5ab-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1c5ab-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

