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
# <a name="install-local-configuration-store-invoke-configure"></a>appel de l’installation du magasin de configurations local (configuration)
 
Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias. S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez **récupérer automatiquement la configuration dans le magasin central de gestion**.
  
Si vous installez un réplica du magasin central de gestion sur un serveur Edge, vous pouvez choisir de lire la copie exportée du document de configuration sur un support mobile, tel qu’une clé USB, un disque dur USB, un CD-ROM ou un autre support. 
  
> [!IMPORTANT]
> Si vous installez le magasin de configuration local sur un serveur Edge, les informations de configuration doivent être dans un format qui a été exporté à partir du magasin central de gestion en exécutant l’applet de cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Après avoir sélectionné l’option appropriée, cliquez sur **suivant**.
  

