---
title: Installer le magasin Local Configuration Invoke (configuration)
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
description: Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie à partir de la Central déjà installé et configuré Magasin de gestion, ou de lecture de la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez récupérer la configuration automatiquement à partir du magasin Central de gestion.
ms.openlocfilehash: 74269ee40116b91097c77702942f42de9f7d882a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installer le magasin Local Configuration Invoke (configuration)
 
Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie à partir de la Central déjà installé et configuré Magasin de gestion, ou de lecture de la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez **récupérer la configuration automatiquement à partir du magasin Central de gestion**.
  
Si vous installez un réplica du magasin Central de gestion sur un serveur Edge, vous permet de lire la copie du document de configuration exportée à partir du média portable, comme un disque mémoire flash USB, disque dur USB, CD-ROM ou autres supports. 
  
> [!IMPORTANT]
> Si vous installez le magasin de configurations Local sur un serveur Edge, les informations de configuration doit être dans un format qui a été exporté à partir de l’administration centrale stocker en exécutant l’applet de commande Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Une fois que vous avez sélectionné l’option appropriée, cliquez sur **suivant**.
  

