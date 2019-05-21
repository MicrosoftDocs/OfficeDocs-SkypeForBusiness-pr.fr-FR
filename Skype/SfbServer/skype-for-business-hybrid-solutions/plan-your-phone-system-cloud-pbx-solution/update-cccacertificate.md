---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: L’applet de connexion Update-CcCACertificate renouvelle le certificat de l’autorité de certification racine Skype entreprise Cloud Connector qui est proche de l’expiration ou qui est déjà expiré.
ms.openlocfilehash: e32b910d07aa4f2370af72d0a04bb939b80b3034
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286844"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="5479f-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5479f-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="5479f-104">L’applet de connexion Update-CcCACertificate renouvelle le certificat de l’autorité de certification racine Skype entreprise Cloud Connector qui est proche de l’expiration ou qui est déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="5479f-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="5479f-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5479f-105">Parameters</span></span>

<span data-ttu-id="5479f-106">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5479f-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="5479f-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="5479f-107">Examples</span></span>
<span data-ttu-id="5479f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5479f-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="5479f-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5479f-109">Example 1</span></span>

<span data-ttu-id="5479f-110">L’exemple suivant renouvelle le certificat de l’AC racine ::  </span><span class="sxs-lookup"><span data-stu-id="5479f-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="5479f-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="5479f-111">Detailed Description</span></span>
<span data-ttu-id="5479f-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5479f-112"></span></span>

<span data-ttu-id="5479f-113">Le certificat de l’AC racine de Cloud Connector est valide cinq ans à partir de la date d’installation du service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="5479f-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="5479f-114">Si le certificat racine est proche de l’expiration ou a déjà expiré, exécutez l’applet de certification Update-CcCACertificate pour renouveler le certificat.</span><span class="sxs-lookup"><span data-stu-id="5479f-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="5479f-115">Après le renouvellement du certificat racine, le serveur AD, le magasin central de gestion et le serveur Edge fournissent automatiquement de nouveaux certificats.</span><span class="sxs-lookup"><span data-stu-id="5479f-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="5479f-116">S’il existe plusieurs applications sur le même site RTC, exécutez l’applet de l’applet de mise à jour-CcCACertificate dans tous les appareils du même site PSTN.</span><span class="sxs-lookup"><span data-stu-id="5479f-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="5479f-117">Comme dernière étape, exécutez Export-CcRootCertificate afin d’exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="5479f-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="5479f-118">Cette commande remplace l’applet de commande Renew-CcCACertificate dans Cloud Connector 2,0 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="5479f-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5479f-119">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="5479f-119">Input Types</span></span>
<span data-ttu-id="5479f-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5479f-120"></span></span>

<span data-ttu-id="5479f-121">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5479f-121">None.</span></span> <span data-ttu-id="5479f-122">L’applet de commande Update-CcCACertificate n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="5479f-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5479f-123">Types de retours</span><span class="sxs-lookup"><span data-stu-id="5479f-123">Return Types</span></span>
<span data-ttu-id="5479f-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5479f-124"></span></span>

<span data-ttu-id="5479f-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5479f-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5479f-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5479f-126">See also</span></span>
<span data-ttu-id="5479f-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5479f-127"></span></span>

[<span data-ttu-id="5479f-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5479f-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="5479f-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5479f-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="5479f-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5479f-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

