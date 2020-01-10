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
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003334"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="79ff7-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="79ff7-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="79ff7-104">Permet d’importer la configuration de Skype entreprise version Cloud Connector à partir d’un fichier local sur le serveur hôte du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="79ff7-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="79ff7-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="79ff7-105">Examples</span></span>
<span data-ttu-id="79ff7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="79ff7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="79ff7-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="79ff7-107">Example 1</span></span>

<span data-ttu-id="79ff7-108">Dans l’exemple suivant, la CloudConnector. ini est copiée à partir de l’annuaire d’application de l’instance Cloud Connector vers l’annuaire%SystemDrive%\ProgramData\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="79ff7-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="79ff7-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="79ff7-109">Detailed Description</span></span>
<span data-ttu-id="79ff7-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="79ff7-110"></span></span>

<span data-ttu-id="79ff7-111">Cette applet de connexion copie le CloudConnector. ini du répertoire de l’application Cloud Connector vers le répertoire%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="79ff7-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="79ff7-112">L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="79ff7-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="79ff7-113">L’applet de lecture écrasera tout fichier existant dans%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="79ff7-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="79ff7-114">Cette commande s’applique à la version 2.0.1 et versions ultérieures de l’édition Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="79ff7-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="79ff7-115">Paramètres</span><span class="sxs-lookup"><span data-stu-id="79ff7-115">Parameters</span></span>
<span data-ttu-id="79ff7-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="79ff7-116"></span></span>

|<span data-ttu-id="79ff7-117">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="79ff7-117">**Parameter**</span></span>|<span data-ttu-id="79ff7-118">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="79ff7-118">**Required**</span></span>|<span data-ttu-id="79ff7-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="79ff7-119">**Type**</span></span>|<span data-ttu-id="79ff7-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="79ff7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79ff7-121">Force</span><span class="sxs-lookup"><span data-stu-id="79ff7-121">Force</span></span>  <br/> |<span data-ttu-id="79ff7-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="79ff7-122">Optional</span></span>  <br/> |<span data-ttu-id="79ff7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="79ff7-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="79ff7-124">Remplacez le fichier existant dans%SystemDrive%\ProgramData\CloudConnector sans notification.</span><span class="sxs-lookup"><span data-stu-id="79ff7-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="79ff7-125">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="79ff7-125">Input Types</span></span>
<span data-ttu-id="79ff7-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="79ff7-126"></span></span>

<span data-ttu-id="79ff7-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="79ff7-127">None.</span></span> <span data-ttu-id="79ff7-128">L’applet de commande Import-CcConfiguration n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="79ff7-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="79ff7-129">Types de retours</span><span class="sxs-lookup"><span data-stu-id="79ff7-129">Return Types</span></span>
<span data-ttu-id="79ff7-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="79ff7-130"></span></span>

<span data-ttu-id="79ff7-131">Aucun.</span><span class="sxs-lookup"><span data-stu-id="79ff7-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79ff7-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79ff7-132">See also</span></span>
<span data-ttu-id="79ff7-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="79ff7-133"></span></span>

<span data-ttu-id="79ff7-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="79ff7-134">Export-CcConfiguration</span></span>
  

