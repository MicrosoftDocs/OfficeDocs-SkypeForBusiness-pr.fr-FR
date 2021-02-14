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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: LRenew-CcCACertificate de la cmdlet renouvelle le certificat de l’ac racine de la version Cloud Connector de Skype Entreprise qui est sur le point d’expirer ou qui a déjà expiré. Cette commande a été modifiée Update-CcCACertificate dans Cloud Connector 2.0 et les version ultérieures.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824270"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="f79f7-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f79f7-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="f79f7-105">LRenew-CcCACertificate de la cmdlet renouvelle le certificat de l’ac racine de la version Cloud Connector de Skype Entreprise qui est sur le point d’expirer ou qui a déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="f79f7-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="f79f7-106">Cette commande a été modifiée Update-CcCACertificate dans Cloud Connector 2.0 et les version ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f79f7-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="f79f7-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f79f7-107">Parameters</span></span>

<span data-ttu-id="f79f7-108">Aucun</span><span class="sxs-lookup"><span data-stu-id="f79f7-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f79f7-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="f79f7-109">Examples</span></span>
<span data-ttu-id="f79f7-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f79f7-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f79f7-111">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f79f7-111">Example 1</span></span>

<span data-ttu-id="f79f7-112">L’exemple suivant renouvelle le certificat d’ac racine :</span><span class="sxs-lookup"><span data-stu-id="f79f7-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="f79f7-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="f79f7-113">Detailed Description</span></span>
<span data-ttu-id="f79f7-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f79f7-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f79f7-115">Le certificat de l’autorité de certification racine Cloud Connector est valide pendant cinq ans à partir de la date d’installation du service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="f79f7-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="f79f7-116">Si le certificat racine est sur le point d’expirer ou s’il a déjà expiré, exécutez la cmdlet Renew-CcCACertificate pour renouveler le certificat.</span><span class="sxs-lookup"><span data-stu-id="f79f7-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="f79f7-117">Une fois le certificat racine renouvelé, le serveur AD, le magasin central de gestion et le serveur Edge sont automatiquement émis.</span><span class="sxs-lookup"><span data-stu-id="f79f7-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="f79f7-118">S’il existe plusieurs appliances dans le même site PSTN, exécutez l'Renew-CcCACertificate cmdlet dans toutes les appliances du même site PSTN.</span><span class="sxs-lookup"><span data-stu-id="f79f7-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="f79f7-119">Lors de la dernière étape, exécutez Export-CcRootCertificate pour exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté sur vos passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="f79f7-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f79f7-120">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="f79f7-120">Input Types</span></span>
<span data-ttu-id="f79f7-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f79f7-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f79f7-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f79f7-122">None.</span></span> <span data-ttu-id="f79f7-123">La cmdlet Renew-CcCACertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="f79f7-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f79f7-124">Types de retour</span><span class="sxs-lookup"><span data-stu-id="f79f7-124">Return Types</span></span>
<span data-ttu-id="f79f7-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f79f7-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f79f7-126">Aucun</span><span class="sxs-lookup"><span data-stu-id="f79f7-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f79f7-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f79f7-127">See also</span></span>
<span data-ttu-id="f79f7-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f79f7-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f79f7-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f79f7-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f79f7-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f79f7-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f79f7-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f79f7-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

