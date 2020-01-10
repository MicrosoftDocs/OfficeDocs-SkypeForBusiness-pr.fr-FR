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
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: L’applet de connexion Update-CcServerCertificate renouvelle les certificats pour Skype entreprise version Cloud Connector lorsque ceux-ci sont proches de leur expiration ou qui ont déjà expiré.
ms.openlocfilehash: 920770b4ce77e893a7195d1326ea13ac73e0cc70
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003114"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="e7d66-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e7d66-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="e7d66-104">L’applet de connexion Update-CcServerCertificate renouvelle les certificats pour Skype entreprise version Cloud Connector lorsque ceux-ci sont proches de leur expiration ou qui ont déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="e7d66-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="e7d66-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="e7d66-105">Examples</span></span>
<span data-ttu-id="e7d66-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e7d66-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="e7d66-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="e7d66-107">Example 1</span></span>

<span data-ttu-id="e7d66-108">L’exemple suivant renouvelle les certificats pour le magasin central de gestion, le serveur de médiation et le serveur Edge lorsque les certificats sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="e7d66-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="e7d66-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="e7d66-109">Example 2</span></span>

<span data-ttu-id="e7d66-110">L’exemple suivant renouvelle les certificats pour le serveur de médiation et le serveur Edge lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré :</span><span class="sxs-lookup"><span data-stu-id="e7d66-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="e7d66-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="e7d66-111">Detailed Description</span></span>
<span data-ttu-id="e7d66-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e7d66-112"></span></span>

<span data-ttu-id="e7d66-113">Les certificats internes du Cloud Connector émis sur le magasin de gestion central, le serveur de médiation et le serveur Edge sont valides pendant deux ans après leur émission par le biais d’un service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="e7d66-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="e7d66-114">Si les certificats sont bientôt expirés ou sont déjà arrivés à expiration, exécutez l’applet de certification Update-CcServerCertificate pour renouveler les certificats.</span><span class="sxs-lookup"><span data-stu-id="e7d66-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="e7d66-115">Cette commande remplace l’applet de commande Renew-CcServerCertificate dans Cloud Connector 2,0 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="e7d66-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e7d66-116">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e7d66-116">Parameters</span></span>
<span data-ttu-id="e7d66-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e7d66-117"></span></span>

|<span data-ttu-id="e7d66-118">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e7d66-118">**Parameter**</span></span>|<span data-ttu-id="e7d66-119">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="e7d66-119">**Required**</span></span>|<span data-ttu-id="e7d66-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7d66-120">**Type**</span></span>|<span data-ttu-id="e7d66-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="e7d66-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7d66-122">Rôles</span><span class="sxs-lookup"><span data-stu-id="e7d66-122">Roles</span></span>  <br/> |<span data-ttu-id="e7d66-123">Facultatif</span><span class="sxs-lookup"><span data-stu-id="e7d66-123">Optional</span></span>  <br/> |<span data-ttu-id="e7d66-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="e7d66-124">System.Array</span></span>  <br/> | <span data-ttu-id="e7d66-125">Série de rôles des serveurs de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e7d66-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e7d66-126">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="e7d66-126">Input Types</span></span>
<span data-ttu-id="e7d66-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7d66-127"></span></span>

<span data-ttu-id="e7d66-128">Aucun.</span><span class="sxs-lookup"><span data-stu-id="e7d66-128">None.</span></span> <span data-ttu-id="e7d66-129">L’applet de commande Update-CcServerCertificate n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="e7d66-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e7d66-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="e7d66-130">Return Types</span></span>
<span data-ttu-id="e7d66-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7d66-131"></span></span>

<span data-ttu-id="e7d66-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="e7d66-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7d66-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7d66-133">See also</span></span>
<span data-ttu-id="e7d66-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7d66-134"></span></span>

[<span data-ttu-id="e7d66-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e7d66-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="e7d66-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e7d66-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="e7d66-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e7d66-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

