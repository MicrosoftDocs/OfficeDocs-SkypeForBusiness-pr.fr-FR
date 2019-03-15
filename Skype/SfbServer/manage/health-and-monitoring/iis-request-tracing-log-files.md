---
title: Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) dans Skype pour Business Server 2015 prise en charge pour les clients hérités.'
ms.openlocfilehash: 72d5dc8cafc0bbf0b33533d4548f2c7f1cd2d466
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226980"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez le Service de mobilité (Mcx) dans Skype pour Business Server 2015 prise en charge pour les clients hérités.
  
Cette rubrique concerne les déploiements prenant en charge uniquement les clients Lync Mobile de Lync 2010, et en particulier le service Mcx (Mobility Service).

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
Lorsque vous activez le suivi des demandes Internet Information Services (IIS) pour le Skype pour le Service de mobilité Business Server (Mcx), les fichiers journaux générés peuvent consommer jusqu'à trois gigaoctets d’espace disque par jour. La journalisation du suivi IIS est activée par défaut. Vous devez surveiller les serveurs frontaux pour vous assurer qu’ils n’exécutent pas suffisamment d’espace disque. 
  
Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.
  
Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Pour plus d’informations sur la commande **httpLogging** , voir [la référence des commandes](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

