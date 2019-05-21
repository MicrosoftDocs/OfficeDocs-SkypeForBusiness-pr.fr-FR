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
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.
ms.openlocfilehash: 3cac8629a52d915df55408a44d8d31701106a5bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287068"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="9ca58-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9ca58-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="9ca58-104">L’applet de commande Reset-CcCACertificate réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.</span><span class="sxs-lookup"><span data-stu-id="9ca58-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="9ca58-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9ca58-105">Parameters</span></span>

<span data-ttu-id="9ca58-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="9ca58-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9ca58-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="9ca58-107">Examples</span></span>
<span data-ttu-id="9ca58-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca58-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="9ca58-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="9ca58-109">Example 1</span></span>

<span data-ttu-id="9ca58-110">L’exemple suivant réinstalle le serveur AD de service d’autorité de certification afin de créer un nouveau certificat de l’AC racine.</span><span class="sxs-lookup"><span data-stu-id="9ca58-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="9ca58-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="9ca58-111">Detailed Description</span></span>
<span data-ttu-id="9ca58-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca58-112"></span></span>

<span data-ttu-id="9ca58-113">Si le certificat de l’AC est compromis ou plus sécurisé, vous devez mettre à jour le certificat de l’AC racine ainsi que tous les certificats délivrés par l’AC racine.</span><span class="sxs-lookup"><span data-stu-id="9ca58-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="9ca58-114">L’applet de commande Reset-CcCACertificate révoque tous les certificats, désinstalle et réinstalle l’autorité de certification puis nettoie tous les certificats liés à l’ancien service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="9ca58-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="9ca58-115">Pour plus d’informations, reportez-vous à la section «certificats d’autorité de certification ou certificats internes émis au SSFM, serveur de médiation et serveur Edge» est proche de la date d’expiration ou de la compromission» dans résolution des problèmes de déploiement de votre Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9ca58-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9ca58-116">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="9ca58-116">Input Types</span></span>
<span data-ttu-id="9ca58-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca58-117"></span></span>

<span data-ttu-id="9ca58-p102">Aucun. L’applet de commande Reset-CcCACertificate n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="9ca58-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9ca58-120">Types de retours</span><span class="sxs-lookup"><span data-stu-id="9ca58-120">Return Types</span></span>
<span data-ttu-id="9ca58-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca58-121"></span></span>

<span data-ttu-id="9ca58-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9ca58-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9ca58-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ca58-123">See also</span></span>
<span data-ttu-id="9ca58-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9ca58-124"></span></span>

<span data-ttu-id="9ca58-125">[Renouveler-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 uniquement</span><span class="sxs-lookup"><span data-stu-id="9ca58-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="9ca58-126">[Renouveler-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 uniquement</span><span class="sxs-lookup"><span data-stu-id="9ca58-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="9ca58-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2,0 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="9ca58-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="9ca58-128">[Renouveler-CcServerCertificate](renew-ccservercertificate.md) Version 2,0 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="9ca58-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="9ca58-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="9ca58-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

