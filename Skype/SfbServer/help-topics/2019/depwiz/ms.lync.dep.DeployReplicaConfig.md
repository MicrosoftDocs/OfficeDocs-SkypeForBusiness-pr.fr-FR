---
title: appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias. S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez récupérer automatiquement la configuration dans le magasin central de gestion.
ms.openlocfilehash: b4cc16b26e40b0215a72917c5cab47de8bce5e1b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794723"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="268fc-104">appel de l’installation du magasin de configurations local (configuration)</span><span class="sxs-lookup"><span data-stu-id="268fc-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="268fc-105">Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias.</span><span class="sxs-lookup"><span data-stu-id="268fc-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="268fc-106">S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez **récupérer automatiquement la configuration dans le magasin central de gestion**.</span><span class="sxs-lookup"><span data-stu-id="268fc-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="268fc-107">Si vous installez un réplica du magasin central de gestion sur un serveur Edge, vous pouvez choisir de lire la copie exportée du document de configuration sur un support mobile, tel qu’une clé USB, un disque dur USB, un CD-ROM ou un autre support.</span><span class="sxs-lookup"><span data-stu-id="268fc-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="268fc-108">Si vous installez le magasin de configuration local sur un serveur Edge, les informations de configuration doivent être dans un format qui a été exporté à partir du magasin central de gestion en exécutant l’applet de cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="268fc-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="268fc-109">Après avoir sélectionné l’option appropriée, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="268fc-109">After you have selected the appropriate option, click **Next**.</span></span>
  

