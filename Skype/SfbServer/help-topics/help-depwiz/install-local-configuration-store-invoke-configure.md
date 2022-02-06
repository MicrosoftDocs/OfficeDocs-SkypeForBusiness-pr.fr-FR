---
title: Appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 'Pour commencer l’installation de la base de données qui contient la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre récupérer la configuration définie publiée à l’aide du Générateur de topologies à partir du magasin central de gestion déjà installé et configuré, ou lire la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez Récupérer la configuration automatiquement à partir du magasin central de gestion.'
---

# <a name="install-local-configuration-store-invoke-configure"></a>Appel de l’installation du magasin de configurations local (configuration)
 
Pour commencer l’installation de la base de données qui contient la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre récupérer la configuration définie publiée à l’aide du Générateur de topologies à partir du magasin central de gestion déjà installé et configuré, ou lire la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez Récupérer la configuration automatiquement à partir **du magasin central de gestion**.
  
Si vous installez un réplica du magasin central de gestion sur un serveur de périphérie, vous devez choisir de lire la copie exportée du document de configuration à partir d’un support portable, comme une clé USB, un disque dur USB, un CD-ROM ou un autre support. 
  
> [!IMPORTANT]
> Si vous installez le magasin de configurations local sur un serveur Edge, les informations de configuration doivent être dans un format exporté à partir du magasin central de gestion en exécutant la cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Une fois que vous avez sélectionné l’option qui convient, cliquez sur **Suivant**.
  

