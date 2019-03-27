---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: L’applet de commande Update-CcServerCertificate renouvelle les certificats pour Skype pour l’édition de connecteur Business Cloud lorsqu’ils sont bientôt expirer ou déjà arrivé à expiration.
ms.openlocfilehash: 92f914db04d3a3621624efd5b6a72e249b3eb19e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899658"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="b645d-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="b645d-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="b645d-104">L’applet de commande Update-CcServerCertificate renouvelle les certificats pour Skype pour l’édition de connecteur Business Cloud lorsqu’ils sont bientôt expirer ou déjà arrivé à expiration.</span><span class="sxs-lookup"><span data-stu-id="b645d-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="b645d-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="b645d-105">Examples</span></span>
<span data-ttu-id="b645d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b645d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b645d-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="b645d-107">Example 1</span></span>

<span data-ttu-id="b645d-108">L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="b645d-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="b645d-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="b645d-109">Example 2</span></span>

<span data-ttu-id="b645d-110">L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="b645d-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="b645d-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="b645d-111">Detailed Description</span></span>
<span data-ttu-id="b645d-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b645d-112"></span></span>

<span data-ttu-id="b645d-113">Nuage connecteur internes certificats émis vers le magasin Central de gestion, le serveur de médiation et le serveur de périphérie sont valides pour les deux ans après que qu’ils sont émis à partir d’un service de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="b645d-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="b645d-114">Si les certificats sont près d’expiration ou déjà expirés, exécutez l’applet de commande Update-CcServerCertificate pour renouveler les certificats.</span><span class="sxs-lookup"><span data-stu-id="b645d-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="b645d-115">Cette commande remplace l’applet de commande renouveler-CcServerCertificate dans le nuage connecteur 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="b645d-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b645d-116">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b645d-116">Parameters</span></span>
<span data-ttu-id="b645d-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b645d-117"></span></span>

|<span data-ttu-id="b645d-118">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="b645d-118">**Parameter**</span></span>|<span data-ttu-id="b645d-119">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="b645d-119">**Required**</span></span>|<span data-ttu-id="b645d-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="b645d-120">**Type**</span></span>|<span data-ttu-id="b645d-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="b645d-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b645d-122">Rôles</span><span class="sxs-lookup"><span data-stu-id="b645d-122">Roles</span></span>  <br/> |<span data-ttu-id="b645d-123">Facultatif</span><span class="sxs-lookup"><span data-stu-id="b645d-123">Optional</span></span>  <br/> |<span data-ttu-id="b645d-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="b645d-124">System.Array</span></span>  <br/> | <span data-ttu-id="b645d-125">Série de rôles des serveurs de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b645d-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b645d-126">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="b645d-126">Input Types</span></span>
<span data-ttu-id="b645d-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b645d-127"></span></span>

<span data-ttu-id="b645d-128">Aucun.</span><span class="sxs-lookup"><span data-stu-id="b645d-128">None.</span></span> <span data-ttu-id="b645d-129">L’applet de commande Update-CcServerCertificate n’accepte pas la saisie de données redirigées.</span><span class="sxs-lookup"><span data-stu-id="b645d-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b645d-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="b645d-130">Return Types</span></span>
<span data-ttu-id="b645d-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b645d-131"></span></span>

<span data-ttu-id="b645d-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="b645d-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b645d-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b645d-133">See also</span></span>
<span data-ttu-id="b645d-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b645d-134"></span></span>

[<span data-ttu-id="b645d-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="b645d-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="b645d-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="b645d-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="b645d-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="b645d-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

