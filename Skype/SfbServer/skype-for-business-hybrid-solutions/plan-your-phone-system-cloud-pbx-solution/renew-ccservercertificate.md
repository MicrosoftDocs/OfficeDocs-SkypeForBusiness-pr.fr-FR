---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: LRenew-CcServerCertificate cmdlet renouvelle les certificats pour skype entreprise, version Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été modifiée Update-CcServerCertificate dans Cloud Connector 2.0 et les version ultérieures.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824260"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="12b7f-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="12b7f-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="12b7f-105">LRenew-CcServerCertificate cmdlet renouvelle les certificats pour skype entreprise, version Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="12b7f-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="12b7f-106">Cette commande a été modifiée Update-CcServerCertificate dans Cloud Connector 2.0 et les version ultérieures.</span><span class="sxs-lookup"><span data-stu-id="12b7f-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="12b7f-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="12b7f-107">Examples</span></span>
<span data-ttu-id="12b7f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="12b7f-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="12b7f-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="12b7f-109">Example 1</span></span>

<span data-ttu-id="12b7f-110">L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="12b7f-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="12b7f-111">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="12b7f-111">Example 2</span></span>

<span data-ttu-id="12b7f-112">L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="12b7f-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="12b7f-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="12b7f-113">Detailed Description</span></span>
<span data-ttu-id="12b7f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="12b7f-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="12b7f-115">Les certificats internes Cloud Connector délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans après leur émission à partir d’un service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="12b7f-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="12b7f-116">Si les certificats sont sur le point d’expirer ou ont déjà expiré, exécutez la cmdlet Renew-CcServerCertificate pour renouveler les certificats.</span><span class="sxs-lookup"><span data-stu-id="12b7f-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="12b7f-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="12b7f-117">Parameters</span></span>
<span data-ttu-id="12b7f-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="12b7f-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="12b7f-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="12b7f-119">**Parameter**</span></span>|<span data-ttu-id="12b7f-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="12b7f-120">**Required**</span></span>|<span data-ttu-id="12b7f-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="12b7f-121">**Type**</span></span>|<span data-ttu-id="12b7f-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="12b7f-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12b7f-123">Rôles</span><span class="sxs-lookup"><span data-stu-id="12b7f-123">Roles</span></span>  <br/> |<span data-ttu-id="12b7f-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="12b7f-124">Optional</span></span>  <br/> |<span data-ttu-id="12b7f-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="12b7f-125">System.Array</span></span>  <br/> | <span data-ttu-id="12b7f-126">Tableau des rôles serveur Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="12b7f-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="12b7f-127">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="12b7f-127">Input Types</span></span>
<span data-ttu-id="12b7f-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12b7f-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="12b7f-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="12b7f-129">None.</span></span> <span data-ttu-id="12b7f-130">La cmdlet Renew-CcServerCertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="12b7f-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="12b7f-131">Types de retour</span><span class="sxs-lookup"><span data-stu-id="12b7f-131">Return Types</span></span>
<span data-ttu-id="12b7f-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12b7f-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="12b7f-133">Aucun</span><span class="sxs-lookup"><span data-stu-id="12b7f-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12b7f-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12b7f-134">See also</span></span>
<span data-ttu-id="12b7f-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12b7f-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="12b7f-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="12b7f-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="12b7f-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="12b7f-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="12b7f-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="12b7f-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

