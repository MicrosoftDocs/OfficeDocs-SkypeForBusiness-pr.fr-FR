---
title: Installer le magasin de configurations local
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Pour commencer l’installation d’un nouveau Skype pour le serveur de rôle Business Server 2015, vous devez d’abord installer le serveur SQL local qui va héberger le magasin de configurations local. Le magasin de configurations local agira comme un réplica en lecture seule de la Skype pour le magasin Central de gestion de Business Server (CMS). Vous devez être connecté au serveur que vous exécutez l’étape installer le magasin de configurations Local en tant qu’administrateur local sur l’ordinateur et avez appartenir au groupe RTCUniversalServerAdmins ou le groupe RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie est lu à partir du document exporté définition plutôt qu’à partir du magasin Central de gestion. Pour exporter le document de définition du Générateur de topologie et la rendre disponible pour les serveurs de périphérie, consultez la rubrique Exporter votre topologie et les copie il sur un support externe de l’Installation Edge.
ms.openlocfilehash: adce98e053b6959c3513885fc53f1616df1c1125
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="install-local-configuration-store"></a>Installer le magasin de configurations local
 
Pour commencer l’installation d’un nouveau Skype pour le serveur de rôle Business Server 2015, vous devez d’abord installer le serveur SQL local qui va héberger le magasin de configurations local. Le magasin de configurations local agira comme un réplica en lecture seule de la Skype pour le magasin Central de gestion de Business Server (CMS). Vous devez être connecté au serveur décrit à l’étape **Installer le magasin de configurations local** en tant qu’administrateur local de l’ordinateur ; en outre, vous devez être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie est lu à partir du document exporté définition plutôt qu’à partir du magasin Central de gestion. Pour exporter le document de définition du Générateur de topologie et la rendre disponible pour les serveurs de périphérie, consultez la rubrique[exporter votre topologie et copie sur un support externe de l’Installation Edge](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).
  
Pour commencer l’installation :
  
1. Sur la Skype pour Business Server 2015 page, à côté **étape 1 : installer le magasin de Configuration Local**, cliquez sur **exécuter**.
    
2. Dans la page **Configuration du serveur local** assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.
    
3. Une fois l’installation terminée, cliquez sur **Terminer**.
    
> [!NOTE]
> L’installation de SQL Server local peut prendre un certain temps. Vous ne verrez pas les mises à jour sur progression dans l’écran Résumé pendant l’installation de SQL Server. Si vous souhaitez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller l’installation de SQL Server. 
  

