---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: L’applet de commande Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont recensés dans cet annuaire.
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888181"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="61adc-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="61adc-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="61adc-p102">L’applet de commande Set-CcApplianceDirectory définit l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont recensés dans cet annuaire.</span><span class="sxs-lookup"><span data-stu-id="61adc-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="61adc-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="61adc-107">Examples</span></span>
<span data-ttu-id="61adc-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="61adc-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="61adc-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="61adc-109">Example 1</span></span>

<span data-ttu-id="61adc-110">L’exemple suivant définit le répertoire de travail sur le serveur hôte sur c:\cloudconnector\applianceroot :</span><span class="sxs-lookup"><span data-stu-id="61adc-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="61adc-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="61adc-111">Parameters</span></span>
<span data-ttu-id="61adc-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="61adc-112"></span></span>

|<span data-ttu-id="61adc-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="61adc-113">**Parameter**</span></span>|<span data-ttu-id="61adc-114">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="61adc-114">**Required**</span></span>|<span data-ttu-id="61adc-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="61adc-115">**Type**</span></span>|<span data-ttu-id="61adc-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="61adc-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="61adc-117"> Path</span><span class="sxs-lookup"><span data-stu-id="61adc-117">Path</span></span> <br/> | <span data-ttu-id="61adc-118">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="61adc-118">Required</span></span> <br/> |<span data-ttu-id="61adc-119">System.String</span><span class="sxs-lookup"><span data-stu-id="61adc-119">System.String</span></span>  <br/> | <span data-ttu-id="61adc-120"> Spécifie le chemin de stockage de tous les fichiers de déploiement.</span><span class="sxs-lookup"><span data-stu-id="61adc-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="61adc-121">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="61adc-121">Input Types</span></span>
<span data-ttu-id="61adc-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="61adc-122"></span></span>

<span data-ttu-id="61adc-p103">Aucun. L’applet de commande Set-CcApplianceDirectory n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="61adc-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="61adc-125">Types de retours</span><span class="sxs-lookup"><span data-stu-id="61adc-125">Return Types</span></span>
<span data-ttu-id="61adc-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="61adc-126"></span></span>

<span data-ttu-id="61adc-127">Aucune</span><span class="sxs-lookup"><span data-stu-id="61adc-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="61adc-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61adc-128">See also</span></span>
<span data-ttu-id="61adc-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="61adc-129"></span></span>

<span data-ttu-id="61adc-130">Aucun</span><span class="sxs-lookup"><span data-stu-id="61adc-130">None</span></span>
  

