---
title: Ajouter Office Web Apps Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'L’Assistant définir un serveur Office Web Apps définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: cab39bf2ff44704aab37593009c381b649378532
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21064041"
---
# <a name="add-office-web-apps-server"></a>Ajouter Office Web Apps Server
 
L’Assistant **Définir un serveur Office Web Apps** définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :
  
 **Nom de domaine complet de Office Web Apps Server**: tapez le nom de domaine complet du serveur qui hébergera le serveur Office Web Apps Server
  
 **URL de découverte d’Office Web Apps Server**: tapez le localisateur complète uniform resource identifier (URL) du serveur Office Web Apps
  
> [!TIP]
> Le comportement par défaut de l' **URL de découverte d’Office Web Apps Server** consiste à créer des URL basée sur le nom de domaine complet du serveur Office Web Apps au format : `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Dans la plupart des cas, vous ne devrez pas modifier le format par défaut. Vous devrez peut-être modifier le format par défaut dans le cas où le serveur Office Web Apps Server et l’URL de découverte d’Office Web Apps Server doivent être différents. Par exemple, votre serveur Office Web Apps Server est placé dans le réseau de périmètre et aura une URL différente en fonction de l’emplacement.
  
 **Office Web Apps Server est déployé dans un réseau externe (périmètre/Internet)**: sélectionnez la case à cocher si votre serveur Office Web Apps Server est placé en dehors de votre pare-feu interne, telles que le réseau de périmètre, réseau externe ou autre zone réseau qui n’est pas le même que votre réseau interne.
  
## <a name="see-also"></a>Voir aussi

[Composants et Topologies pour la conférence](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)