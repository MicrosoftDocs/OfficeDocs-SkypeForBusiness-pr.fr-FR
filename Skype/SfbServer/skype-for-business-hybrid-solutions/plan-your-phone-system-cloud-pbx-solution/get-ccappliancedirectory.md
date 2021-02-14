---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: La cmdlet Get-CcApplianceDirectory récupère l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont stockés dans ce répertoire.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800844"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="ecdc3-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ecdc3-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="ecdc3-105">La cmdlet Get-CcApplianceDirectory récupère l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="ecdc3-106">Tous les fichiers de déploiement sont stockés dans ce répertoire.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="ecdc3-107">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="ecdc3-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ecdc3-108">Parameters</span></span>

<span data-ttu-id="ecdc3-109">Aucun</span><span class="sxs-lookup"><span data-stu-id="ecdc3-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ecdc3-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="ecdc3-110">Examples</span></span>
<span data-ttu-id="ecdc3-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ecdc3-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ecdc3-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ecdc3-112">Example 1</span></span>

<span data-ttu-id="ecdc3-113">L’exemple suivant montre le dossier actuel dans lequel les fichiers de configuration et de machine virtuelle des composants Cloud Connector sont stockés :</span><span class="sxs-lookup"><span data-stu-id="ecdc3-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="ecdc3-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="ecdc3-114">Detailed Description</span></span>
<span data-ttu-id="ecdc3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ecdc3-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ecdc3-116">LGet-CcApplianceDirectory cmdlet indique où tous les fichiers de configuration et de machine virtuelle, journaux et certificats externes sont stockés pour l’appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="ecdc3-117">Chaque appliance Cloud Connector possède quatre composants : serveur de médiation, magasin central de gestion, serveur Edge et contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="ecdc3-118">Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="ecdc3-119">Vous pouvez modifier ce dossier à l’aide Set-CCApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ecdc3-120">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="ecdc3-120">Input Types</span></span>
<span data-ttu-id="ecdc3-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ecdc3-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ecdc3-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-122">None.</span></span> <span data-ttu-id="ecdc3-123">La cmdlet Get-CCApplianceDirectory n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ecdc3-124">Types de retour</span><span class="sxs-lookup"><span data-stu-id="ecdc3-124">Return Types</span></span>
<span data-ttu-id="ecdc3-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ecdc3-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ecdc3-126">La commande renvoie un chemin d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="ecdc3-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ecdc3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecdc3-127">See also</span></span>
<span data-ttu-id="ecdc3-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ecdc3-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ecdc3-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ecdc3-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

