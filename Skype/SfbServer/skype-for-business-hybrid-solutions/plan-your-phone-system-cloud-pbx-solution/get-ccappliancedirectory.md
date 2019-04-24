---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire. '
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233973"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="2d2ef-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="2d2ef-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="2d2ef-p102">L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire. </span><span class="sxs-lookup"><span data-stu-id="2d2ef-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="2d2ef-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="2d2ef-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2d2ef-108">Parameters</span></span>

<span data-ttu-id="2d2ef-109">Aucun</span><span class="sxs-lookup"><span data-stu-id="2d2ef-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2d2ef-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="2d2ef-110">Examples</span></span>
<span data-ttu-id="2d2ef-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d2ef-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="2d2ef-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="2d2ef-112">Example 1</span></span>

<span data-ttu-id="2d2ef-113">L’exemple suivant montre le dossier actif où sont stockés les fichiers de configuration et machine virtuelle des composants de nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="2d2ef-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="2d2ef-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="2d2ef-114">Detailed Description</span></span>
<span data-ttu-id="2d2ef-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2d2ef-115"></span></span>

<span data-ttu-id="2d2ef-116">L’applet de commande Get-CcApplianceDirectory indique où tous les fichiers de configuration et les ordinateurs virtuels, des journaux et les certificats externes sont stockées pour la solution de nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="2d2ef-117">Chaque appliance nuage connecteur comporte quatre composants : serveur de médiation, magasin Central de gestion, serveur de périphérie et un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="2d2ef-118">Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="2d2ef-119">Vous pouvez modifier ce dossier en utilisant l'applet de commande Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2d2ef-120">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="2d2ef-120">Input Types</span></span>
<span data-ttu-id="2d2ef-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d2ef-121"></span></span>

<span data-ttu-id="2d2ef-p104">Aucun. L’applet de commande Get-CCApplianceDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2d2ef-124">Types de retours</span><span class="sxs-lookup"><span data-stu-id="2d2ef-124">Return Types</span></span>
<span data-ttu-id="2d2ef-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d2ef-125"></span></span>

<span data-ttu-id="2d2ef-126">La commande renvoie un chemin d’accès de fichier.</span><span class="sxs-lookup"><span data-stu-id="2d2ef-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d2ef-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d2ef-127">See also</span></span>
<span data-ttu-id="2d2ef-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d2ef-128"></span></span>

[<span data-ttu-id="2d2ef-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="2d2ef-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

