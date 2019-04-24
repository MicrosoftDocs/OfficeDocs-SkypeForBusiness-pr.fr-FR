---
title: appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie à partir de la Central déjà installé et configuré Magasin de gestion, ou de lecture de la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez récupérer la configuration automatiquement à partir du magasin Central de gestion.
ms.openlocfilehash: 21cf742be33ab79daa733cbc52aa557b6ccee145
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216052"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="d386a-104">appel de l’installation du magasin de configurations local (configuration)</span><span class="sxs-lookup"><span data-stu-id="d386a-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="d386a-105">Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie à partir de la Central déjà installé et configuré Magasin de gestion, ou de lecture de la configuration définie à partir d’autres supports.</span><span class="sxs-lookup"><span data-stu-id="d386a-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="d386a-106">Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez **récupérer la configuration automatiquement à partir du magasin Central de gestion**.</span><span class="sxs-lookup"><span data-stu-id="d386a-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="d386a-107">Si vous installez un réplica du magasin Central de gestion sur un serveur Edge, vous permet de lire la copie du document de configuration exportée à partir du média portable, comme un disque mémoire flash USB, disque dur USB, CD-ROM ou autres supports.</span><span class="sxs-lookup"><span data-stu-id="d386a-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d386a-108">Si vous installez le magasin de configurations Local sur un serveur Edge, les informations de configuration doit être dans un format qui a été exporté à partir de l’administration centrale stocker en exécutant l’applet de commande Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="d386a-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="d386a-109">Une fois que vous avez sélectionné l’option appropriée, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d386a-109">After you have selected the appropriate option, click **Next**.</span></span>
  

