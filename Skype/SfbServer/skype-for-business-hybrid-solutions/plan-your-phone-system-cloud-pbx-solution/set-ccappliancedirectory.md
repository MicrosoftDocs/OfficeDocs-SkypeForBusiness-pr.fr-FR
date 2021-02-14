---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: La cmdlet Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont stockés dans ce répertoire.
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824220"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="342b4-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="342b4-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="342b4-105">La cmdlet Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="342b4-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="342b4-106">Tous les fichiers de déploiement sont stockés dans ce répertoire.</span><span class="sxs-lookup"><span data-stu-id="342b4-106">All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="342b4-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="342b4-107">Examples</span></span>
<span data-ttu-id="342b4-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="342b4-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="342b4-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="342b4-109">Example 1</span></span>

<span data-ttu-id="342b4-110">L’exemple suivant définit le répertoire de travail sur le serveur hôte sur c:\cloudconnector\applianceroot :</span><span class="sxs-lookup"><span data-stu-id="342b4-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="342b4-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="342b4-111">Parameters</span></span>
<span data-ttu-id="342b4-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="342b4-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="342b4-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="342b4-113">**Parameter**</span></span>|<span data-ttu-id="342b4-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="342b4-114">**Required**</span></span>|<span data-ttu-id="342b4-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="342b4-115">**Type**</span></span>|<span data-ttu-id="342b4-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="342b4-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="342b4-117">Path</span><span class="sxs-lookup"><span data-stu-id="342b4-117">Path</span></span> <br/> | <span data-ttu-id="342b4-118">Requis</span><span class="sxs-lookup"><span data-stu-id="342b4-118">Required</span></span> <br/> |<span data-ttu-id="342b4-119">System.String</span><span class="sxs-lookup"><span data-stu-id="342b4-119">System.String</span></span>  <br/> | <span data-ttu-id="342b4-120">Spécifie le chemin d’accès où sont stockés tous les fichiers de déploiement.</span><span class="sxs-lookup"><span data-stu-id="342b4-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="342b4-121">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="342b4-121">Input Types</span></span>
<span data-ttu-id="342b4-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="342b4-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="342b4-123">Aucun.</span><span class="sxs-lookup"><span data-stu-id="342b4-123">None.</span></span> <span data-ttu-id="342b4-124">La cmdlet Set-CcApplianceDirectory n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="342b4-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="342b4-125">Types de retour</span><span class="sxs-lookup"><span data-stu-id="342b4-125">Return Types</span></span>
<span data-ttu-id="342b4-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="342b4-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="342b4-127">Aucun</span><span class="sxs-lookup"><span data-stu-id="342b4-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="342b4-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="342b4-128">See also</span></span>
<span data-ttu-id="342b4-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="342b4-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="342b4-130">Aucun</span><span class="sxs-lookup"><span data-stu-id="342b4-130">None</span></span>
  

