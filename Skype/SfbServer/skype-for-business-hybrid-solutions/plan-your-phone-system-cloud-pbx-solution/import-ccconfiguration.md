---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Permet d’importer la configuration de Skype entreprise version Cloud Connector à partir d’un fichier local sur le serveur hôte du Cloud Connector.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287278"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="9c1ae-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c1ae-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="9c1ae-104">Permet d’importer la configuration de Skype entreprise version Cloud Connector à partir d’un fichier local sur le serveur hôte du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9c1ae-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="9c1ae-105">Examples</span></span>
<span data-ttu-id="9c1ae-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c1ae-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9c1ae-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="9c1ae-107">Example 1</span></span>

<span data-ttu-id="9c1ae-108">Dans l’exemple suivant, la CloudConnector. ini est copiée à partir de l’annuaire d’application de l’instance Cloud Connector vers l’annuaire%SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="9c1ae-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="9c1ae-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="9c1ae-109">Detailed Description</span></span>
<span data-ttu-id="9c1ae-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c1ae-110"></span></span>

<span data-ttu-id="9c1ae-111">Cette applet de connexion copie le CloudConnector. ini du répertoire de l’application Cloud Connector vers le répertoire%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="9c1ae-112">L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="9c1ae-113">L’applet de lecture écrasera tout fichier existant dans%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="9c1ae-114">Cette commande s’applique à la version 2.0.1 et versions ultérieures de l’édition Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9c1ae-115">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9c1ae-115">Parameters</span></span>
<span data-ttu-id="9c1ae-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c1ae-116"></span></span>

|<span data-ttu-id="9c1ae-117">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="9c1ae-117">**Parameter**</span></span>|<span data-ttu-id="9c1ae-118">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="9c1ae-118">**Required**</span></span>|<span data-ttu-id="9c1ae-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="9c1ae-119">**Type**</span></span>|<span data-ttu-id="9c1ae-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="9c1ae-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c1ae-121">Force</span><span class="sxs-lookup"><span data-stu-id="9c1ae-121">Force</span></span>  <br/> |<span data-ttu-id="9c1ae-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="9c1ae-122">Optional</span></span>  <br/> |<span data-ttu-id="9c1ae-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9c1ae-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9c1ae-124">Remplacez le fichier existant dans%SystemDrive%\ProgramData\CloudConnector sans notification.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9c1ae-125">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="9c1ae-125">Input Types</span></span>
<span data-ttu-id="9c1ae-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c1ae-126"></span></span>

<span data-ttu-id="9c1ae-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-127">None.</span></span> <span data-ttu-id="9c1ae-128">L’applet de commande Import-CcConfiguration n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9c1ae-129">Types de retours</span><span class="sxs-lookup"><span data-stu-id="9c1ae-129">Return Types</span></span>
<span data-ttu-id="9c1ae-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c1ae-130"></span></span>

<span data-ttu-id="9c1ae-131">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c1ae-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c1ae-132">See also</span></span>
<span data-ttu-id="9c1ae-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c1ae-133"></span></span>

<span data-ttu-id="9c1ae-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c1ae-134">Export-CcConfiguration</span></span>
  

