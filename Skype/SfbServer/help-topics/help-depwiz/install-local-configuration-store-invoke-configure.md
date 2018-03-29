---
title: Appel de magasin de Configuration Local Installation (configurer)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie de la centrale déjà installé et configuré Magasin de gestion, ou la lecture de la configuration définie à partir d’autres supports. Pour une machine qui se trouve sur le réseau interne de votre entreprise, sélectionnez configuration de récupérer automatiquement à partir du magasin Central de gestion.
ms.openlocfilehash: 74269ee40116b91097c77702942f42de9f7d882a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="c67db-104">Appel de magasin de Configuration Local Installation (configurer)</span><span class="sxs-lookup"><span data-stu-id="c67db-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="c67db-105">Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie de la centrale déjà installé et configuré Magasin de gestion, ou la lecture de la configuration définie à partir d’autres supports.</span><span class="sxs-lookup"><span data-stu-id="c67db-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="c67db-106">Pour une machine qui se trouve sur le réseau interne de votre entreprise, sélectionnez **récupérer la configuration automatiquement à partir du magasin Central de gestion**.</span><span class="sxs-lookup"><span data-stu-id="c67db-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="c67db-107">Si vous installez un réplica du magasin Central de gestion sur un serveur Edge, vous permet de lire la copie exportée du document de configuration à partir d’un support amovible, tel qu’un lecteur flash USB, disque dur USB, CD-ROM ou autres supports.</span><span class="sxs-lookup"><span data-stu-id="c67db-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c67db-108">Si vous installez le magasin de Configuration Local sur un serveur Edge, les informations de configuration doivent être dans un format qui a été exporté à partir de la direction centrale stocker en exécutant la cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="c67db-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="c67db-109">Une fois que vous avez sélectionné l’option appropriée, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c67db-109">After you have selected the appropriate option, click **Next**.</span></span>
  

