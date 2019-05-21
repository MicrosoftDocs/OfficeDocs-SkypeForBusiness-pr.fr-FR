---
title: appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias. S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez récupérer automatiquement la configuration dans le magasin central de gestion.
ms.openlocfilehash: b4249f4968c51fb901e612b2414bb2c6921be40c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303304"
---
# <a name="install-local-configuration-store-invoke-configure"></a>appel de l’installation du magasin de configurations local (configuration)
 
Pour commencer l’installation de la base de données qui contiendra la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre l’extraction de la configuration définie publiée à l’aide du générateur de topologie à partir du centre déjà installé et configuré Magasin de gestion ou lecture de la configuration définie à partir d’autres médias. S’il s’agit d’un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez **récupérer automatiquement la configuration dans le magasin central de gestion**.
  
Si vous installez un réplica du magasin central de gestion sur un serveur Edge, vous pouvez choisir de lire la copie exportée du document de configuration sur un support mobile, tel qu’une clé USB, un disque dur USB, un CD-ROM ou un autre support. 
  
> [!IMPORTANT]
> Si vous installez le magasin de configuration local sur un serveur Edge, les informations de configuration doivent être dans un format qui a été exporté à partir du magasin central de gestion en exécutant l’applet de cmdlet Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Après avoir sélectionné l’option appropriée, cliquez sur **suivant**.
  

