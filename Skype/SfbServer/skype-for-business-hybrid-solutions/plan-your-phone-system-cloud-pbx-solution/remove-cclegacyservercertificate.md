---
title: Remove-CcLegacyServerCertificate
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
ms.openlocfilehash: dc52351d9c66ff310329da62dbd69da74b19c222
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569839"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="88ebd-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="88ebd-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="88ebd-104">L’applet de commande Remove-CcLegacyServerCertificate supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="88ebd-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="88ebd-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="88ebd-105">Examples</span></span>
<span data-ttu-id="88ebd-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="88ebd-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="88ebd-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="88ebd-107">Example 1</span></span>

<span data-ttu-id="88ebd-108">L’exemple suivant supprime les anciens certificats délivrés pour le magasin central de gestion, le serveur de médiation et le serveur Edge après le renouvellement des certificats :</span><span class="sxs-lookup"><span data-stu-id="88ebd-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="88ebd-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="88ebd-109">Example 2</span></span>

<span data-ttu-id="88ebd-110">L’exemple suivant supprime les certificats délivrés pour le serveur de médiation et le serveur Edge après le renouvellement des certificats : </span><span class="sxs-lookup"><span data-stu-id="88ebd-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="88ebd-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="88ebd-111">Parameters</span></span>
<span data-ttu-id="88ebd-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="88ebd-112"></span></span>

|<span data-ttu-id="88ebd-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="88ebd-113">**Parameter**</span></span>|<span data-ttu-id="88ebd-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="88ebd-114">**Required**</span></span>|<span data-ttu-id="88ebd-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="88ebd-115">**Type**</span></span>|<span data-ttu-id="88ebd-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="88ebd-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="88ebd-117">Rôles</span><span class="sxs-lookup"><span data-stu-id="88ebd-117">Roles</span></span> <br/> |<span data-ttu-id="88ebd-118">Facultatif</span><span class="sxs-lookup"><span data-stu-id="88ebd-118">Optional</span></span>  <br/> |<span data-ttu-id="88ebd-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="88ebd-119">System.Array</span></span>  <br/> | <span data-ttu-id="88ebd-120">Série de rôles des serveurs de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="88ebd-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="88ebd-121">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="88ebd-121">Input Types</span></span>
<span data-ttu-id="88ebd-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88ebd-122"></span></span>

<span data-ttu-id="88ebd-p101">Aucun. L’applet de commande Remove-CcLegacyServerCertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="88ebd-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="88ebd-125">Types de retours</span><span class="sxs-lookup"><span data-stu-id="88ebd-125">Return Types</span></span>
<span data-ttu-id="88ebd-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88ebd-126"></span></span>

<span data-ttu-id="88ebd-127">Aucun</span><span class="sxs-lookup"><span data-stu-id="88ebd-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88ebd-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88ebd-128">See also</span></span>
<span data-ttu-id="88ebd-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88ebd-129"></span></span>

[<span data-ttu-id="88ebd-130">CcServerCertificate renouveler</span><span class="sxs-lookup"><span data-stu-id="88ebd-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="88ebd-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="88ebd-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="88ebd-132">CcCACertificate renouveler</span><span class="sxs-lookup"><span data-stu-id="88ebd-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="88ebd-133">Mise à jour-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="88ebd-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

