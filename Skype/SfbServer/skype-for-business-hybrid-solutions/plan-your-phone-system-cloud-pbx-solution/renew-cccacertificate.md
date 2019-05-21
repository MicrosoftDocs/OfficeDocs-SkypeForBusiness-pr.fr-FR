---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: L’applet de commande Renew-CcCACertificate renouvelle le certificat de l’AC racine de Skype Entreprise, version Cloud Connector, qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été remplacée par Update-CcCACertificate dans Cloud Connector 2,0 et versions ultérieures.
ms.openlocfilehash: f1e376b5b944468ec5bf508c6221a099a83d4804
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287103"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="be96c-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="be96c-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="be96c-105">L’applet de commande Renew-CcCACertificate renouvelle le certificat de l’AC racine de Skype Entreprise, version Cloud Connector, qui est sur le point d’expirer ou qui a déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="be96c-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="be96c-106">Cette commande a été remplacée par Update-CcCACertificate dans Cloud Connector 2,0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="be96c-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="be96c-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="be96c-107">Parameters</span></span>

<span data-ttu-id="be96c-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="be96c-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="be96c-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="be96c-109">Examples</span></span>
<span data-ttu-id="be96c-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="be96c-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="be96c-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="be96c-111">Example 1</span></span>

<span data-ttu-id="be96c-112">L’exemple suivant renouvelle le certificat de l’AC racine ::  </span><span class="sxs-lookup"><span data-stu-id="be96c-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="be96c-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="be96c-113">Detailed Description</span></span>
<span data-ttu-id="be96c-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="be96c-114"></span></span>

<span data-ttu-id="be96c-115">Le certificat de l’AC racine de Cloud Connector est valide cinq ans à partir de la date d’installation du service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="be96c-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="be96c-p103">Si le certificat racine est sur le point d’expirer ou a déjà expiré, exécutez l’applet de commande Renew-CcCACertificate afin de renouveler le certificat. Après le renouvellement du certificat racine, le serveur AD, le magasin central de gestion et le serveur Edge fournissent automatiquement de nouveaux certificats.</span><span class="sxs-lookup"><span data-stu-id="be96c-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="be96c-118">S’il existe plusieurs appliances dans le même site RTC, exécutez l’applet de commande Renew-CcCACertificate dans toutes les appliances du même site RTC.</span><span class="sxs-lookup"><span data-stu-id="be96c-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="be96c-119">Comme dernière étape, exécutez Export-CcRootCertificate afin d’exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="be96c-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="be96c-120">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="be96c-120">Input Types</span></span>
<span data-ttu-id="be96c-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="be96c-121"></span></span>

<span data-ttu-id="be96c-p104">Aucun. L’applet de commande Renew-CcCACertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="be96c-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="be96c-124">Types de retours</span><span class="sxs-lookup"><span data-stu-id="be96c-124">Return Types</span></span>
<span data-ttu-id="be96c-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="be96c-125"></span></span>

<span data-ttu-id="be96c-126">Aucun</span><span class="sxs-lookup"><span data-stu-id="be96c-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be96c-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be96c-127">See also</span></span>
<span data-ttu-id="be96c-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="be96c-128"></span></span>

[<span data-ttu-id="be96c-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="be96c-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="be96c-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="be96c-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="be96c-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="be96c-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

