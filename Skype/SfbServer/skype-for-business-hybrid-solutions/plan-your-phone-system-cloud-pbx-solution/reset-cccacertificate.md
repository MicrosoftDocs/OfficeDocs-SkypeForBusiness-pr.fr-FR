---
title: Reset-CcCACertificate
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
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: La cmdlet Reset-CcCACertificate réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824250"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="85602-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="85602-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="85602-104">La cmdlet Reset-CcCACertificate réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.</span><span class="sxs-lookup"><span data-stu-id="85602-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="85602-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="85602-105">Parameters</span></span>

<span data-ttu-id="85602-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="85602-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="85602-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="85602-107">Examples</span></span>
<span data-ttu-id="85602-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="85602-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="85602-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="85602-109">Example 1</span></span>

<span data-ttu-id="85602-110">L’exemple suivant réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine :</span><span class="sxs-lookup"><span data-stu-id="85602-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="85602-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="85602-111">Detailed Description</span></span>
<span data-ttu-id="85602-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="85602-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="85602-113">Si le certificat de l’ac racine est compromis ou n’est plus sécurisé, vous devez mettre à jour le certificat de l’ac racine et tous les certificats émis par l’ac racine.</span><span class="sxs-lookup"><span data-stu-id="85602-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="85602-114">La cmdlet Reset-CcCACertificate révoque tous les certificats, désinstalle et réinstalle l’autorité de certification, puis nettoie tous les certificats liés à l’ancien service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="85602-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="85602-115">Pour plus d’informations, voir « Les certificats d’autorité de certification ou les certificats internes délivrés à CMS, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis » dans La résolution des problèmes de déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="85602-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="85602-116">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="85602-116">Input Types</span></span>
<span data-ttu-id="85602-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85602-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="85602-118">Aucun.</span><span class="sxs-lookup"><span data-stu-id="85602-118">None.</span></span> <span data-ttu-id="85602-119">La cmdlet Reset-CcCACertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="85602-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="85602-120">Types de retour</span><span class="sxs-lookup"><span data-stu-id="85602-120">Return Types</span></span>
<span data-ttu-id="85602-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85602-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="85602-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="85602-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85602-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85602-123">See also</span></span>
<span data-ttu-id="85602-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85602-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="85602-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 uniquement</span><span class="sxs-lookup"><span data-stu-id="85602-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="85602-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 uniquement</span><span class="sxs-lookup"><span data-stu-id="85602-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="85602-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 et ultérieures</span><span class="sxs-lookup"><span data-stu-id="85602-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="85602-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 et ultérieures</span><span class="sxs-lookup"><span data-stu-id="85602-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="85602-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="85602-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

