---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: ab332f6f0c88de01f59342002f6387ab8a83a13b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287075"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="8a68c-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="8a68c-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="8a68c-104">L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="8a68c-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="8a68c-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="8a68c-105">Examples</span></span>
<span data-ttu-id="8a68c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8a68c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8a68c-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8a68c-107">Example 1</span></span>

<span data-ttu-id="8a68c-108">L’exemple suivant supprime les anciens certificats délivrés pour le magasin central de gestion, le serveur de médiation et le serveur Edge après le renouvellement des certificats :</span><span class="sxs-lookup"><span data-stu-id="8a68c-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="8a68c-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="8a68c-109">Example 2</span></span>

<span data-ttu-id="8a68c-110">L’exemple suivant supprime les certificats délivrés pour le serveur de médiation et le serveur Edge après le renouvellement des certificats : </span><span class="sxs-lookup"><span data-stu-id="8a68c-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="8a68c-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8a68c-111">Parameters</span></span>
<span data-ttu-id="8a68c-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8a68c-112"></span></span>

|<span data-ttu-id="8a68c-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8a68c-113">**Parameter**</span></span>|<span data-ttu-id="8a68c-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="8a68c-114">**Required**</span></span>|<span data-ttu-id="8a68c-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="8a68c-115">**Type**</span></span>|<span data-ttu-id="8a68c-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="8a68c-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8a68c-117">Rôles</span><span class="sxs-lookup"><span data-stu-id="8a68c-117">Roles</span></span> <br/> |<span data-ttu-id="8a68c-118">Facultatif</span><span class="sxs-lookup"><span data-stu-id="8a68c-118">Optional</span></span>  <br/> |<span data-ttu-id="8a68c-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="8a68c-119">System.Array</span></span>  <br/> | <span data-ttu-id="8a68c-120">Série de rôles des serveurs de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8a68c-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8a68c-121">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="8a68c-121">Input Types</span></span>
<span data-ttu-id="8a68c-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8a68c-122"></span></span>

<span data-ttu-id="8a68c-p101">Aucun. L’applet de commande Remove-CcLegacyServerCertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="8a68c-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8a68c-125">Types de retours</span><span class="sxs-lookup"><span data-stu-id="8a68c-125">Return Types</span></span>
<span data-ttu-id="8a68c-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8a68c-126"></span></span>

<span data-ttu-id="8a68c-127">Aucun</span><span class="sxs-lookup"><span data-stu-id="8a68c-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a68c-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a68c-128">See also</span></span>
<span data-ttu-id="8a68c-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8a68c-129"></span></span>

[<span data-ttu-id="8a68c-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="8a68c-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="8a68c-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8a68c-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="8a68c-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8a68c-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="8a68c-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8a68c-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

