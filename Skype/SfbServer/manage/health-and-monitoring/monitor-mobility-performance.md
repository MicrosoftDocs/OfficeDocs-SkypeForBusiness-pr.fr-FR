---
title: Surveiller la mobilité pour les performances dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.'
ms.openlocfilehash: e2da6f073dc14268442e3c49273189b002eaadc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902832"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Surveiller la mobilité pour les performances dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.
  
Le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée augmente la charge sur les pools frontaux et les serveurs frontaux. Les appareils mobiles maintient une connexion au serveur même lorsque l’application mobile est réduite, tels que les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus importante que les périphériques qui mettre fin à leur connexion au serveur lors de l’application mobile est réduite. À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
Plusieurs limites influencent les performances de mobilité : 
  
- mémoire disponible ;
    
- limite de file d’attente des demandes ;
    
- connexions simultanées ;
    
- longueur de la file d’attente des services Internet (IIS).
    
Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md)
    
- [Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server](service-and-ucwa-usage.md)
    
- [Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server](configure-service.md)
    
- [Surveillance des demandes IIS le suivi des fichiers journaux dans Skype pour Business Server](iis-request-tracing-log-files.md)
    
- [Compteurs de performances de mobilité dans Skype pour Business Server](performance-counters.md)
    

