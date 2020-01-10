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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: L’applet de connexion Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde de l’autorité de certification dans le dossier autorité de certification sous le répertoire de partage du site pour Skype entreprise version Cloud Connector.
ms.openlocfilehash: d7036633eaf092130fc6e4acaebda39d04ff17df
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003294"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="1501d-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="1501d-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="1501d-104">L’applet de connexion Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde du&lt;service&gt;de l’autorité de certification « SiteRootDirectory \CA\SfB CCE. p12 » dans le dossier ca sous le répertoire de partage de site pour Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1501d-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="1501d-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1501d-105">Parameters</span></span>

<span data-ttu-id="1501d-106">Aucun</span><span class="sxs-lookup"><span data-stu-id="1501d-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1501d-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="1501d-107">Examples</span></span>
<span data-ttu-id="1501d-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1501d-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="1501d-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="1501d-109">Example 1</span></span>

<span data-ttu-id="1501d-110">Dans l’exemple suivant, le fichier de sauvegarde du service&lt;de&gt;l’autorité de certification « SiteRootDirectory \CA\SfB CCE. P12 » est supprimé dans le dossier ca sous le répertoire de partage du site :</span><span class="sxs-lookup"><span data-stu-id="1501d-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="1501d-111">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="1501d-111">Input Types</span></span>
<span data-ttu-id="1501d-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1501d-112"></span></span>

<span data-ttu-id="1501d-p101">Aucun. L’applet de commande Remove-CcCertificationAuthorityFile n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="1501d-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1501d-115">Types de retours</span><span class="sxs-lookup"><span data-stu-id="1501d-115">Return Types</span></span>
<span data-ttu-id="1501d-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1501d-116"></span></span>

<span data-ttu-id="1501d-117">Aucun</span><span class="sxs-lookup"><span data-stu-id="1501d-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1501d-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1501d-118">See also</span></span>
<span data-ttu-id="1501d-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1501d-119"></span></span>

[<span data-ttu-id="1501d-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="1501d-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

