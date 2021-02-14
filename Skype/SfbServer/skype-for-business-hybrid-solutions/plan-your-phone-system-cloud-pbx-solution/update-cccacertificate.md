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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: LUpdate-CcCACertificate de la cmdlet renouvelle le certificat de l’ac racine de la version Cloud Connector de Skype Entreprise qui est sur le point d’expirer ou qui a déjà expiré.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824118"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="8db64-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8db64-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="8db64-104">LUpdate-CcCACertificate de la cmdlet renouvelle le certificat de l’ac racine de la version Cloud Connector de Skype Entreprise qui est sur le point d’expirer ou qui a déjà expiré.</span><span class="sxs-lookup"><span data-stu-id="8db64-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="8db64-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8db64-105">Parameters</span></span>

<span data-ttu-id="8db64-106">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8db64-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="8db64-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="8db64-107">Examples</span></span>
<span data-ttu-id="8db64-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8db64-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8db64-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8db64-109">Example 1</span></span>

<span data-ttu-id="8db64-110">L’exemple suivant renouvelle le certificat d’ac racine :</span><span class="sxs-lookup"><span data-stu-id="8db64-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="8db64-111">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="8db64-111">Detailed Description</span></span>
<span data-ttu-id="8db64-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8db64-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8db64-113">Le certificat de l’autorité de certification racine Cloud Connector est valide pendant cinq ans à partir de la date d’installation du service d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="8db64-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="8db64-114">Si le certificat racine est sur le point d’expirer ou s’il a déjà expiré, exécutez la cmdlet Update-CcCACertificate pour renouveler le certificat.</span><span class="sxs-lookup"><span data-stu-id="8db64-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="8db64-115">Une fois le certificat racine renouvelé, le serveur AD, le magasin central de gestion et le serveur Edge sont automatiquement émis.</span><span class="sxs-lookup"><span data-stu-id="8db64-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="8db64-116">S’il existe plusieurs appliances dans le même site PSTN, exécutez l'Update-CcCACertificate cmdlet dans toutes les appliances du même site PSTN.</span><span class="sxs-lookup"><span data-stu-id="8db64-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="8db64-117">Lors de la dernière étape, exécutez Export-CcRootCertificate pour exporter le certificat racine vers un fichier local dans la première appliance, puis copiez et installez le certificat exporté sur vos passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="8db64-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="8db64-118">Cette commande remplace la cmdlet Renew-CcCACertificate dans Cloud Connector 2.0 et les version ultérieures.</span><span class="sxs-lookup"><span data-stu-id="8db64-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8db64-119">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="8db64-119">Input Types</span></span>
<span data-ttu-id="8db64-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8db64-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8db64-121">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8db64-121">None.</span></span> <span data-ttu-id="8db64-122">La cmdlet Update-CcCACertificate n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="8db64-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8db64-123">Types de retour</span><span class="sxs-lookup"><span data-stu-id="8db64-123">Return Types</span></span>
<span data-ttu-id="8db64-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8db64-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8db64-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8db64-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8db64-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8db64-126">See also</span></span>
<span data-ttu-id="8db64-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8db64-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="8db64-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8db64-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="8db64-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="8db64-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="8db64-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="8db64-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

