---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
ms.openlocfilehash: 1ed9aaa8b7caf1edd5324d082094fa247c858853
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898535"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="424e5-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="424e5-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="424e5-104">L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.</span><span class="sxs-lookup"><span data-stu-id="424e5-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="424e5-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="424e5-105">Parameters</span></span>

<span data-ttu-id="424e5-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="424e5-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="424e5-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="424e5-107">Examples</span></span>
<span data-ttu-id="424e5-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="424e5-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="424e5-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="424e5-109">Example 1</span></span>

<span data-ttu-id="424e5-110">L’exemple suivant réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.</span><span class="sxs-lookup"><span data-stu-id="424e5-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="424e5-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="424e5-111">Detailed Description</span></span>
<span data-ttu-id="424e5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="424e5-112"></span></span>

<span data-ttu-id="424e5-113">Si le certificat de l’AC est compromis ou plus sécurisé, vous devez mettre à jour le certificat de l’AC racine ainsi que tous les certificats délivrés par l’AC racine.</span><span class="sxs-lookup"><span data-stu-id="424e5-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="424e5-114">L’applet de commande Reset-CcCACertificate révoque tous les certificats, désinstalle et réinstalle l’autorité de certification puis nettoie tous les certificats liés à l’ancien service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="424e5-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="424e5-115">Pour plus d’informations, voir « Certificat certificats d’autorité internes émis à CMS, serveur de médiation et serveur de transport Edge sont bientôt expirer ou les certificats sont compromises » dans le dépannage de votre déploiement en nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="424e5-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="424e5-116">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="424e5-116">Input Types</span></span>
<span data-ttu-id="424e5-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="424e5-117"></span></span>

<span data-ttu-id="424e5-p102">Aucun. L’applet de commande Reset-CcCACertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="424e5-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="424e5-120">Types de retours</span><span class="sxs-lookup"><span data-stu-id="424e5-120">Return Types</span></span>
<span data-ttu-id="424e5-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="424e5-121"></span></span>

<span data-ttu-id="424e5-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="424e5-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="424e5-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="424e5-123">See also</span></span>
<span data-ttu-id="424e5-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="424e5-124"></span></span>

<span data-ttu-id="424e5-125">[CcCACertificate renouveler](renew-cccacertificate.md) Version 1.4.2</span><span class="sxs-lookup"><span data-stu-id="424e5-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="424e5-126">[CcServerCertificate renouveler](renew-ccservercertificate.md) Version 1.4.2</span><span class="sxs-lookup"><span data-stu-id="424e5-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="424e5-127">[Mise à jour-CcCACertificate](update-cccacertificate.md) Version 2.0 et versions ultérieure</span><span class="sxs-lookup"><span data-stu-id="424e5-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="424e5-128">[CcServerCertificate renouveler](renew-ccservercertificate.md) Version 2.0 et versions ultérieure</span><span class="sxs-lookup"><span data-stu-id="424e5-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="424e5-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="424e5-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

