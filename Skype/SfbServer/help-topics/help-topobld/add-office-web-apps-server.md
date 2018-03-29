---
title: Ajouter Office Web Apps Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'L’Assistant de définir un serveur Office Web Apps définit un serveur Office Web Apps dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: df8f2ba98215a597e9532e636b022edf9cb1ec19
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-office-web-apps-server"></a>Ajouter Office Web Apps Server
 
L’Assistant de **Définir un serveur Office Web Apps** définit un serveur Office Web Apps dans votre déploiement. Vous devez fournir les informations suivantes :
  
 **FQDN de serveur Office Web Apps**: tapez le nom de domaine complet du serveur qui hébergera le serveur Office Web Apps
  
 **URL de découverte de serveur de Office Web Apps**: tapez le localisateur complète uniform resource identifier (URL) du serveur Office Web Apps
  
> [!TIP]
> Le comportement par défaut de l' **URL de découverte de serveur de Office Web Apps** est pour créer l’URL basé sur le nom de domaine complet du serveur Office Web Apps dans le format : `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Dans la plupart des cas, vous ne devrez pas modifier le format par défaut. Vous devrez peut-être modifier le format par défaut dans le cas où un serveur Office Web Apps et l’URL de découverte d’Office Web Apps Server doivent être différents. Par exemple, votre serveur Office Web Apps Server est placé dans le réseau de périmètre et aura une URL différente en fonction de l’emplacement.
  
 **Office Web Apps Server est déployé dans un réseau externe (c'est-à-dire, périmètre Internet)**: sélectionnez la case à cocher si votre serveur Office Web Apps Server est placée à l’extérieur de votre pare-feu interne, comme le réseau de périmètre, réseau externe ou autre zone réseau qui n’est pas le même que votre réseau interne.
  
## <a name="see-also"></a>Voir aussi

#### 

[Les composants et les Topologies pour la conférence](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)

