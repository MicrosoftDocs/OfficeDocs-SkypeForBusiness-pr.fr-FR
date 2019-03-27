---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882459"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="9f7f9-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9f7f9-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="9f7f9-104">L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="9f7f9-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="9f7f9-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="9f7f9-105">Examples</span></span>
<span data-ttu-id="9f7f9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f7f9-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9f7f9-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="9f7f9-107">Example 1</span></span>

<span data-ttu-id="9f7f9-108">L’exemple suivant supprime les anciens certificats délivrés pour le magasin central de gestion, le serveur de médiation et le serveur Edge après le renouvellement des certificats :</span><span class="sxs-lookup"><span data-stu-id="9f7f9-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="9f7f9-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="9f7f9-109">Example 2</span></span>

<span data-ttu-id="9f7f9-110">L’exemple suivant supprime les certificats délivrés pour le serveur de médiation et le serveur Edge après le renouvellement des certificats : </span><span class="sxs-lookup"><span data-stu-id="9f7f9-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="9f7f9-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9f7f9-111">Parameters</span></span>
<span data-ttu-id="9f7f9-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f7f9-112"></span></span>

|<span data-ttu-id="9f7f9-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="9f7f9-113">**Parameter**</span></span>|<span data-ttu-id="9f7f9-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="9f7f9-114">**Required**</span></span>|<span data-ttu-id="9f7f9-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="9f7f9-115">**Type**</span></span>|<span data-ttu-id="9f7f9-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="9f7f9-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9f7f9-117">Rôles</span><span class="sxs-lookup"><span data-stu-id="9f7f9-117">Roles</span></span> <br/> |<span data-ttu-id="9f7f9-118">Facultatif</span><span class="sxs-lookup"><span data-stu-id="9f7f9-118">Optional</span></span>  <br/> |<span data-ttu-id="9f7f9-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="9f7f9-119">System.Array</span></span>  <br/> | <span data-ttu-id="9f7f9-120">Série de rôles des serveurs de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9f7f9-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9f7f9-121">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="9f7f9-121">Input Types</span></span>
<span data-ttu-id="9f7f9-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f7f9-122"></span></span>

<span data-ttu-id="9f7f9-p101">Aucun. L’applet de commande Remove-CcLegacyServerCertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="9f7f9-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9f7f9-125">Types de retours</span><span class="sxs-lookup"><span data-stu-id="9f7f9-125">Return Types</span></span>
<span data-ttu-id="9f7f9-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f7f9-126"></span></span>

<span data-ttu-id="9f7f9-127">Aucun</span><span class="sxs-lookup"><span data-stu-id="9f7f9-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9f7f9-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f7f9-128">See also</span></span>
<span data-ttu-id="9f7f9-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f7f9-129"></span></span>

[<span data-ttu-id="9f7f9-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9f7f9-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="9f7f9-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9f7f9-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="9f7f9-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9f7f9-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="9f7f9-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9f7f9-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

