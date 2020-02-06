---
title: appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias. S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez récupérer automatiquement la configuration dans le magasin central de gestion.
ms.openlocfilehash: 7638ab56e2ddcc8951ae989de11e72e0817a20bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823638"
---
# <a name="install-local-configuration-store-invoke-configure"></a>appel de l’installation du magasin de configurations local (configuration)
 
Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias. S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez **récupérer automatiquement la configuration dans le magasin central de gestion**.
  
Si vous installez un réplica du magasin central de gestion sur un serveur Edge, vous pouvez choisir de lire la copie exportée du document de configuration sur un support mobile, tel qu’une clé USB, un disque dur USB, un CD-ROM ou un autre support. 
  
> [!IMPORTANT]
> Si vous installez le magasin de configuration local sur un serveur Edge, les informations de configuration doivent être dans un format qui a été exporté à partir du magasin central de gestion en exécutant l’applet de cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Après avoir sélectionné l’option appropriée, cliquez sur **suivant**.
  

