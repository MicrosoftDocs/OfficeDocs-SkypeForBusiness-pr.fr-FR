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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: LRemove-CcLegacyServerCertificate cmdlet supprime les certificats de serveur hérités sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824280"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="82bf4-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="82bf4-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="82bf4-104">LRemove-CcLegacyServerCertificate cmdlet supprime les certificats de serveur hérités sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="82bf4-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="82bf4-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="82bf4-105">Examples</span></span>
<span data-ttu-id="82bf4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="82bf4-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="82bf4-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="82bf4-107">Example 1</span></span>

<span data-ttu-id="82bf4-108">L’exemple suivant supprime les certificats hérités émis pour le magasin central de gestion, le serveur de médiation et le serveur Edge après avoir renouvelé les certificats :</span><span class="sxs-lookup"><span data-stu-id="82bf4-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="82bf4-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="82bf4-109">Example 2</span></span>

<span data-ttu-id="82bf4-110">L’exemple suivant supprime les certificats émis pour le serveur de médiation et le serveur Edge après avoir renouvelé les certificats :</span><span class="sxs-lookup"><span data-stu-id="82bf4-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="82bf4-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="82bf4-111">Parameters</span></span>
<span data-ttu-id="82bf4-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="82bf4-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="82bf4-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="82bf4-113">**Parameter**</span></span>|<span data-ttu-id="82bf4-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="82bf4-114">**Required**</span></span>|<span data-ttu-id="82bf4-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="82bf4-115">**Type**</span></span>|<span data-ttu-id="82bf4-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="82bf4-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="82bf4-117">Rôles</span><span class="sxs-lookup"><span data-stu-id="82bf4-117">Roles</span></span> <br/> |<span data-ttu-id="82bf4-118">Facultatif</span><span class="sxs-lookup"><span data-stu-id="82bf4-118">Optional</span></span>  <br/> |<span data-ttu-id="82bf4-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="82bf4-119">System.Array</span></span>  <br/> | <span data-ttu-id="82bf4-120">Tableau des rôles serveur Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="82bf4-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="82bf4-121">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="82bf4-121">Input Types</span></span>
<span data-ttu-id="82bf4-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="82bf4-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="82bf4-123">Aucun.</span><span class="sxs-lookup"><span data-stu-id="82bf4-123">None.</span></span> <span data-ttu-id="82bf4-124">La cmdlet Remove-CcLegacyServerCertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="82bf4-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="82bf4-125">Types de retour</span><span class="sxs-lookup"><span data-stu-id="82bf4-125">Return Types</span></span>
<span data-ttu-id="82bf4-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="82bf4-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="82bf4-127">Aucun</span><span class="sxs-lookup"><span data-stu-id="82bf4-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="82bf4-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82bf4-128">See also</span></span>
<span data-ttu-id="82bf4-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="82bf4-129"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="82bf4-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="82bf4-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="82bf4-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="82bf4-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="82bf4-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="82bf4-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="82bf4-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="82bf4-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

