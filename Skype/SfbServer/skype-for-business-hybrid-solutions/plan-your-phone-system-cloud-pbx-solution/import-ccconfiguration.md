---
title: Import-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importe le Skype pour la configuration du connecteur du nuage Professionnel à partir d’un fichier local vers le serveur hôte nuage connecteur.
ms.openlocfilehash: c48ce321b4cf40626cc67de8ff32107bf08e5443
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569725"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="5b489-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="5b489-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="5b489-104">Importe le Skype pour la configuration du connecteur du nuage Professionnel à partir d’un fichier local vers le serveur hôte nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="5b489-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="5b489-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="5b489-105">Examples</span></span>
<span data-ttu-id="5b489-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b489-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="5b489-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5b489-107">Example 1</span></span>

<span data-ttu-id="5b489-108">L’exemple suivant copie la CloudConnector.ini à partir du répertoire d’application de l’instance du nuage connecteur au répertoire %SystemDrive%\ProgramData\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="5b489-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="5b489-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="5b489-109">Detailed Description</span></span>
<span data-ttu-id="5b489-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b489-110"></span></span>

<span data-ttu-id="5b489-111">Cette applet de commande copie la CloudConnector.ini à partir du répertoire d’application de la solution de nuage connecteur dans le répertoire %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="5b489-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="5b489-112">L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5b489-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="5b489-113">L’applet de commande remplace tous les fichiers existants dans % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="5b489-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="5b489-114">Cette commande s’applique à nuage connecteur Edition version 2.0.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="5b489-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5b489-115">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5b489-115">Parameters</span></span>
<span data-ttu-id="5b489-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b489-116"></span></span>

|<span data-ttu-id="5b489-117">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="5b489-117">**Parameter**</span></span>|<span data-ttu-id="5b489-118">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="5b489-118">**Required**</span></span>|<span data-ttu-id="5b489-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="5b489-119">**Type**</span></span>|<span data-ttu-id="5b489-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="5b489-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b489-121">Force</span><span class="sxs-lookup"><span data-stu-id="5b489-121">Force</span></span>  <br/> |<span data-ttu-id="5b489-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="5b489-122">Optional</span></span>  <br/> |<span data-ttu-id="5b489-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5b489-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5b489-124">Remplacer un fichier existant dans %SystemDrive%\ProgramData\CloudConnector sans notification.</span><span class="sxs-lookup"><span data-stu-id="5b489-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5b489-125">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="5b489-125">Input Types</span></span>
<span data-ttu-id="5b489-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b489-126"></span></span>

<span data-ttu-id="5b489-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5b489-127">None.</span></span> <span data-ttu-id="5b489-128">La cmdlet Import-CcConfiguration n’accepte pas la saisie de données redirigées.</span><span class="sxs-lookup"><span data-stu-id="5b489-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5b489-129">Types de retours</span><span class="sxs-lookup"><span data-stu-id="5b489-129">Return Types</span></span>
<span data-ttu-id="5b489-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b489-130"></span></span>

<span data-ttu-id="5b489-131">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5b489-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b489-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b489-132">See also</span></span>
<span data-ttu-id="5b489-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b489-133"></span></span>

<span data-ttu-id="5b489-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="5b489-134">Export-CcConfiguration</span></span>
  

