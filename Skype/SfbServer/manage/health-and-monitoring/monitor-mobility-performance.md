---
title: Surveiller les performances de la mobilité dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : Découvrez le service de mobilité (Mcx) et l’API UCWA (Unified Communications Web API) dans Skype Entreprise Server.'
ms.openlocfilehash: 5f8adbbdc653d8cdf2e19ce3f82fc4fdb0383505
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746920"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Surveiller les performances de la mobilité dans Skype Entreprise Server
 
**Résumé :** Découvrez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.
  
Le service Skype Entreprise Server Mobility Service (Mcx) et l’API web de communications unifiées (UCWA) augmentent la charge sur les serveurs frontux et les pools frontux. Les appareils mobiles qui maintiennent une connexion au serveur même lorsque l’application mobile est réduite, comme les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus élevée que les appareils qui terminent leur connexion au serveur lorsque l’application mobile est réduite. À mesure que votre utilisation de la mobilité augmente, vous devez surveiller les performances de mobilité pour déterminer quand vous devez augmenter votre capacité.

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
Plusieurs limites influencent les performances de mobilité : 
  
- Mémoire disponible
    
- Limite de file d’attente des demandes
    
- Connexions simultanées
    
- Longueur de file d’attente IIS
    
Les autres limites sur les serveurs qui peuvent influencer les performances de mobilité sont un maximum de 12 ouvertures de session, authentifications, renouvellements de session et résiliations simultanées. Ces valeurs maximales n’ont pas besoin d’être modifiées pour la plupart des déploiements.
  
## <a name="in-this-section"></a>Dans cette section

- [Surveiller les limites de capacité de mémoire du serveur dans Skype Entreprise Server](server-memory-capacity-limits.md)
    
- [Surveiller l’utilisation du service de mobilité et de l’UCWA dans Skype Entreprise Server](service-and-ucwa-usage.md)
    
- [Configurer le service de mobilité pour des performances élevées dans Skype Entreprise Server](configure-service.md)
    
- [Surveillance des fichiers journaux de suivi des demandes IIS dans Skype Entreprise Server](iis-request-tracing-log-files.md)
    
- [Compteurs de performances de mobilité dans Skype Entreprise Server](performance-counters.md)
    

