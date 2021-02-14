---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: La cmdlet Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde du service d’autorité de certification dans le dossier CA sous l’annuaire de partage de sites pour Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824290"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="fdb89-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="fdb89-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="fdb89-104">L'Remove-CcCertificationAuthorityFile cmdlet supprime le fichier de sauvegarde du service d’autorité de certification « &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12 » dans le dossier CA sous l’annuaire de partage de sites pour Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fdb89-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="fdb89-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fdb89-105">Parameters</span></span>

<span data-ttu-id="fdb89-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="fdb89-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="fdb89-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="fdb89-107">Examples</span></span>
<span data-ttu-id="fdb89-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb89-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="fdb89-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="fdb89-109">Example 1</span></span>

<span data-ttu-id="fdb89-110">L’exemple suivant supprime le fichier de sauvegarde du service d’autorité de certification « &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12 » dans le dossier CA sous l’annuaire de partage de sites :</span><span class="sxs-lookup"><span data-stu-id="fdb89-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="fdb89-111">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="fdb89-111">Input Types</span></span>
<span data-ttu-id="fdb89-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb89-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="fdb89-113">Aucun.</span><span class="sxs-lookup"><span data-stu-id="fdb89-113">None.</span></span> <span data-ttu-id="fdb89-114">La cmdlet Remove-CcCertificationAuthorityFile n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="fdb89-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fdb89-115">Types de retour</span><span class="sxs-lookup"><span data-stu-id="fdb89-115">Return Types</span></span>
<span data-ttu-id="fdb89-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb89-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="fdb89-117">Aucun</span><span class="sxs-lookup"><span data-stu-id="fdb89-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdb89-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdb89-118">See also</span></span>
<span data-ttu-id="fdb89-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb89-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="fdb89-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="fdb89-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

