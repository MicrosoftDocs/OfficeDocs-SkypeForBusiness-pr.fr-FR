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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: L’applet de commande Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont recensés dans cet annuaire.
ms.openlocfilehash: 56a13da740b0c23adee7e05ddbcc1bbc82f0f1cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287054"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="6b376-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="6b376-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="6b376-p102">L’applet de commande Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont recensés dans cet annuaire.</span><span class="sxs-lookup"><span data-stu-id="6b376-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="6b376-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="6b376-107">Examples</span></span>
<span data-ttu-id="6b376-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6b376-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6b376-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="6b376-109">Example 1</span></span>

<span data-ttu-id="6b376-110">L’exemple suivant définit le répertoire de travail sur le serveur hôte sur c:\cloudconnector\applianceroot :</span><span class="sxs-lookup"><span data-stu-id="6b376-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="6b376-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6b376-111">Parameters</span></span>
<span data-ttu-id="6b376-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6b376-112"></span></span>

|<span data-ttu-id="6b376-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="6b376-113">**Parameter**</span></span>|<span data-ttu-id="6b376-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="6b376-114">**Required**</span></span>|<span data-ttu-id="6b376-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="6b376-115">**Type**</span></span>|<span data-ttu-id="6b376-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="6b376-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6b376-117"> Path</span><span class="sxs-lookup"><span data-stu-id="6b376-117">Path</span></span> <br/> | <span data-ttu-id="6b376-118">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="6b376-118">Required</span></span> <br/> |<span data-ttu-id="6b376-119">System.String</span><span class="sxs-lookup"><span data-stu-id="6b376-119">System.String</span></span>  <br/> | <span data-ttu-id="6b376-120"> Spécifie le chemin de stockage de tous les fichiers de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6b376-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6b376-121">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="6b376-121">Input Types</span></span>
<span data-ttu-id="6b376-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b376-122"></span></span>

<span data-ttu-id="6b376-p103">Aucun. L’applet de commande Set-CcApplianceDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="6b376-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6b376-125">Types de retours</span><span class="sxs-lookup"><span data-stu-id="6b376-125">Return Types</span></span>
<span data-ttu-id="6b376-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b376-126"></span></span>

<span data-ttu-id="6b376-127">Aucune</span><span class="sxs-lookup"><span data-stu-id="6b376-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6b376-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b376-128">See also</span></span>
<span data-ttu-id="6b376-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b376-129"></span></span>

<span data-ttu-id="6b376-130">Aucun</span><span class="sxs-lookup"><span data-stu-id="6b376-130">None</span></span>
  

