---
title: Appel de l’installation du magasin de configurations local (configuration)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de la base de données qui contient la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre récupérer la configuration définie publiée à l’aide du Générateur de topologies à partir du magasin central de gestion déjà installé et configuré, ou lire la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez Récupérer la configuration automatiquement à partir du magasin central de gestion.
ms.openlocfilehash: b450a4a76dd7b43065e2784ba6f0cef9f18a1b6e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390596"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Appel de l’installation du magasin de configurations local (configuration)
 
Pour commencer l’installation de la base de données qui contient la copie locale en lecture seule du magasin central de gestion, vous devez choisir entre récupérer la configuration définie publiée à l’aide du Générateur de topologies à partir du magasin central de gestion déjà installé et configuré, ou lire la configuration définie à partir d’autres supports. Pour un ordinateur qui se trouve sur le réseau interne de votre organisation, sélectionnez Récupérer la configuration automatiquement à partir **du magasin central de gestion**.
  
Si vous installez un réplica du magasin central de gestion sur un serveur de périphérie, vous devez choisir de lire la copie exportée du document de configuration à partir d’un support portable, comme une clé USB, un disque dur USB, un CD-ROM ou un autre support. 
  
> [!IMPORTANT]
> Si vous installez le magasin de configurations local sur un serveur Edge, les informations de configuration doivent être dans un format exporté à partir du magasin central de gestion en exécutant la cmdlet Windows PowerShell :`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Une fois que vous avez sélectionné l’option qui convient, cliquez sur **Suivant**.
  

