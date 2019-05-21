---
title: Surveiller la mobilité des performances dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé: en savoir plus sur le service de mobilité (MCX) et l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279920"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Surveiller la mobilité des performances dans Skype entreprise Server
 
**Résumé:** En savoir plus sur le service de mobilité (MCX) et l’API Unified Communications Web API (UCWA) dans Skype entreprise Server.
  
Le service de mobilité de Skype entreprise Server (MCX) et l’API Web de communications unifiées (UCWA) augmentent la charge sur les serveurs frontaux et les listes frontales. Les appareils mobiles qui maintiennent une connexion au serveur, même lorsque l’application mobile est réduite (par exemple, les appareils Android et Nokia exécutant Lync 2010 mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 mobile, imposent un chargement supérieur aux appareils mettre fin à sa connexion au serveur lorsque l’application mobile est réduite; À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
Plusieurs limites influencent les performances de mobilité : 
  
- mémoire disponible ;
    
- limite de file d’attente des demandes ;
    
- connexions simultanées ;
    
- longueur de la file d’attente des services Internet (IIS).
    
Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server](server-memory-capacity-limits.md)
    
- [Surveiller l’utilisation du service de mobilité et de UCWA dans Skype entreprise Server](service-and-ucwa-usage.md)
    
- [Configurer le service de mobilité pour des performances élevées dans Skype entreprise Server](configure-service.md)
    
- [Surveiller les fichiers journaux de suivi de requête IIS dans Skype entreprise Server](iis-request-tracing-log-files.md)
    
- [Compteurs de performance de mobilité dans Skype entreprise Server](performance-counters.md)
    

