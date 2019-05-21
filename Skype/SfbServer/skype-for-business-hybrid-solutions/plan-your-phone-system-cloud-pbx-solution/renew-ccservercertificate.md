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
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: L’applet de commande Renew-CcServerCertificate renouvelle les certificats pour la version Cloud Connector de Skype Entreprise lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré. Cette commande a été remplacée par Update-CcServerCertificate dans Cloud Connector 2,0 et versions ultérieures.
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287061"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="5143a-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5143a-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="5143a-105">L’applet de commande Renew-CcServerCertificate renouvelle les certificats pour la version Cloud Connector de Skype Entreprise lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="5143a-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="5143a-106">Cette commande a été remplacée par Update-CcServerCertificate dans Cloud Connector 2,0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="5143a-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="5143a-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="5143a-107">Examples</span></span>
<span data-ttu-id="5143a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5143a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="5143a-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5143a-109">Example 1</span></span>

<span data-ttu-id="5143a-110">L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="5143a-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="5143a-111">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="5143a-111">Example 2</span></span>

<span data-ttu-id="5143a-112">L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="5143a-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="5143a-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="5143a-113">Detailed Description</span></span>
<span data-ttu-id="5143a-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5143a-114"></span></span>

<span data-ttu-id="5143a-115">Les certificats internes du Cloud Connector émis sur le magasin de gestion central, le serveur de médiation et le serveur Edge sont valides pendant deux ans après leur émission par le biais d’un service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="5143a-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="5143a-116">Si les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré, exécutez l’applet de commande Renew-CcServerCertificate afin de les renouveler.</span><span class="sxs-lookup"><span data-stu-id="5143a-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="5143a-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5143a-117">Parameters</span></span>
<span data-ttu-id="5143a-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5143a-118"></span></span>

|<span data-ttu-id="5143a-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="5143a-119">**Parameter**</span></span>|<span data-ttu-id="5143a-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="5143a-120">**Required**</span></span>|<span data-ttu-id="5143a-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="5143a-121">**Type**</span></span>|<span data-ttu-id="5143a-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="5143a-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5143a-123">Rôles</span><span class="sxs-lookup"><span data-stu-id="5143a-123">Roles</span></span>  <br/> |<span data-ttu-id="5143a-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="5143a-124">Optional</span></span>  <br/> |<span data-ttu-id="5143a-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="5143a-125">System.Array</span></span>  <br/> | <span data-ttu-id="5143a-126">Série de rôles des serveurs de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5143a-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5143a-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="5143a-127">Input Types</span></span>
<span data-ttu-id="5143a-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5143a-128"></span></span>

<span data-ttu-id="5143a-p104">Aucun. L’applet de commande Renew-CcServerCertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="5143a-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5143a-131">Types de retours</span><span class="sxs-lookup"><span data-stu-id="5143a-131">Return Types</span></span>
<span data-ttu-id="5143a-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5143a-132"></span></span>

<span data-ttu-id="5143a-133">Aucun</span><span class="sxs-lookup"><span data-stu-id="5143a-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5143a-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5143a-134">See also</span></span>
<span data-ttu-id="5143a-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5143a-135"></span></span>

[<span data-ttu-id="5143a-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5143a-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="5143a-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5143a-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="5143a-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5143a-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

