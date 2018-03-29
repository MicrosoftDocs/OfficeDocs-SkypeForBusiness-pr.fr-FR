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
# <a name="install-local-configuration-store-invoke-configure"></a>Appel de magasin de Configuration Local Installation (configurer)
 
Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin Central de gestion, vous sélectionnez entre la récupération de la configuration définie est publiée à l’aide du Générateur de topologie de la centrale déjà installé et configuré Magasin de gestion, ou la lecture de la configuration définie à partir d’autres supports. Pour une machine qui se trouve sur le réseau interne de votre entreprise, sélectionnez **récupérer la configuration automatiquement à partir du magasin Central de gestion**.
  
Si vous installez un réplica du magasin Central de gestion sur un serveur Edge, vous permet de lire la copie exportée du document de configuration à partir d’un support amovible, tel qu’un lecteur flash USB, disque dur USB, CD-ROM ou autres supports. 
  
> [!IMPORTANT]
> Si vous installez le magasin de Configuration Local sur un serveur Edge, les informations de configuration doivent être dans un format qui a été exporté à partir de la direction centrale stocker en exécutant la cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Une fois que vous avez sélectionné l’option appropriée, cliquez sur **suivant**.
  

