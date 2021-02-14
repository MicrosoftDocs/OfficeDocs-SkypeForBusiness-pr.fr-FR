---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: LUpdate-CcServerCertificate cmdlet renouvelle les certificats pour skype entreprise, version Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824108"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="6df8d-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6df8d-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="6df8d-104">LUpdate-CcServerCertificate cmdlet renouvelle les certificats pour skype entreprise, version Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="6df8d-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="6df8d-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="6df8d-105">Examples</span></span>
<span data-ttu-id="6df8d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6df8d-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6df8d-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="6df8d-107">Example 1</span></span>

<span data-ttu-id="6df8d-108">L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="6df8d-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="6df8d-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="6df8d-109">Example 2</span></span>

<span data-ttu-id="6df8d-110">L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="6df8d-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="6df8d-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="6df8d-111">Detailed Description</span></span>
<span data-ttu-id="6df8d-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6df8d-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="6df8d-113">Les certificats internes Cloud Connector délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans après leur émission à partir d’un service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="6df8d-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="6df8d-114">Si les certificats sont sur le point d’expirer ou ont déjà expiré, exécutez la cmdlet Update-CcServerCertificate pour renouveler les certificats.</span><span class="sxs-lookup"><span data-stu-id="6df8d-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="6df8d-115">Cette commande remplace la cmdlet Renew-CcServerCertificate dans Cloud Connector 2.0 et les version ultérieures.</span><span class="sxs-lookup"><span data-stu-id="6df8d-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6df8d-116">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6df8d-116">Parameters</span></span>
<span data-ttu-id="6df8d-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6df8d-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="6df8d-118">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="6df8d-118">**Parameter**</span></span>|<span data-ttu-id="6df8d-119">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="6df8d-119">**Required**</span></span>|<span data-ttu-id="6df8d-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="6df8d-120">**Type**</span></span>|<span data-ttu-id="6df8d-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="6df8d-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6df8d-122">Rôles</span><span class="sxs-lookup"><span data-stu-id="6df8d-122">Roles</span></span>  <br/> |<span data-ttu-id="6df8d-123">Facultatif</span><span class="sxs-lookup"><span data-stu-id="6df8d-123">Optional</span></span>  <br/> |<span data-ttu-id="6df8d-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="6df8d-124">System.Array</span></span>  <br/> | <span data-ttu-id="6df8d-125">Tableau des rôles serveur Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6df8d-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6df8d-126">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="6df8d-126">Input Types</span></span>
<span data-ttu-id="6df8d-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6df8d-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6df8d-128">Aucun.</span><span class="sxs-lookup"><span data-stu-id="6df8d-128">None.</span></span> <span data-ttu-id="6df8d-129">La cmdlet Update-CcServerCertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="6df8d-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6df8d-130">Types de retour</span><span class="sxs-lookup"><span data-stu-id="6df8d-130">Return Types</span></span>
<span data-ttu-id="6df8d-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6df8d-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6df8d-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="6df8d-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6df8d-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6df8d-133">See also</span></span>
<span data-ttu-id="6df8d-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6df8d-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6df8d-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6df8d-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="6df8d-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6df8d-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="6df8d-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="6df8d-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

