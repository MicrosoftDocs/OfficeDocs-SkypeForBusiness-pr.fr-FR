---
title: Appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Pour commencer l’installation de la base de données qui contient la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre récupérer la configuration définie publiée à l’aide du Générateur de topologies à partir du magasin central de gestion déjà installé et configuré, ou lire la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez Récupérer la configuration automatiquement à partir du magasin central de gestion.
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827204"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="9d305-104">Appel de l’installation du magasin de configurations local (configuration)</span><span class="sxs-lookup"><span data-stu-id="9d305-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="9d305-105">Pour commencer l’installation de la base de données qui contient la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre récupérer la configuration définie publiée à l’aide du Générateur de topologies à partir du magasin central de gestion déjà installé et configuré, ou lire la configuration définie à partir d’autres supports.</span><span class="sxs-lookup"><span data-stu-id="9d305-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="9d305-106">Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez Récupérer la configuration automatiquement à partir **du magasin central de gestion.**</span><span class="sxs-lookup"><span data-stu-id="9d305-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="9d305-107">Si vous installez un réplica du magasin central de gestion sur un serveur de périphérie, vous devez choisir de lire la copie exportée du document de configuration à partir d’un support portable, comme une clé USB, un disque dur USB, un CD-ROM ou un autre support.</span><span class="sxs-lookup"><span data-stu-id="9d305-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9d305-108">Si vous installez le magasin de configurations local sur un serveur Edge, les informations de configuration doivent être dans un format exporté à partir du magasin central de gestion en exécutant la cmdlet Windows PowerShell :  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="9d305-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="9d305-109">Une fois que vous avez sélectionné l’option qui convient, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9d305-109">After you have selected the appropriate option, click **Next**.</span></span>
  

