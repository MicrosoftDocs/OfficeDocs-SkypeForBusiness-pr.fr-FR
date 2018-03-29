---
title: Surveillance des performances de mobilité dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>Surveillance des performances de mobilité dans Skype Entreprise Server 2015
 
**Résumé :** En savoir plus sur le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.
  
Le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifié augmente la charge sur les pools de serveurs frontaux et de Front-End. Les périphériques mobiles qui maintiennent une connexion au serveur, même lorsque l’application mobile est réduite, par exemple les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que des appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus importante que les périphériques qui mettre fin à leur connexion avec le serveur lorsque l’application mobile est réduite. À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.
  
Plusieurs limites influencent les performances de mobilité : 
  
- mémoire disponible ;
    
- limite de file d’attente des demandes ;
    
- connexions simultanées ;
    
- longueur de la file d’attente des services Internet (IIS).
    
Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015](server-memory-capacity-limits.md)
    
- [Surveiller l’utilisation du Service de la mobilité et la UCWA dans Skype pour Business Server 2015](service-and-ucwa-usage.md)
    
- [Configurer le Service de la mobilité pour des performances élevées dans Skype pour Business Server 2015](configure-service.md)
    
- [IIS contrôle demande des fichiers journaux de suivi dans Skype pour Business Server 2015](iis-request-tracing-log-files.md)
    
- [Compteurs de performance de mobilité dans Skype pour Business Server 2015](performance-counters.md)
    

