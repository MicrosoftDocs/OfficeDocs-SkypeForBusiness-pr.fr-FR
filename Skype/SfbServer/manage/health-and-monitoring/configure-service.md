---
title: Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : En savoir plus sur le Service de mobilité dans Skype pour Business Server.'
ms.openlocfilehash: 5031d34a2fdcb1610325afbf58c5524a0ee28ca8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026805"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur le Service de mobilité dans Skype pour Business Server.
  
> [!IMPORTANT]
> Cette rubrique s’applique uniquement à la Skype pour le Service de mobilité Business Server (Mcx) et ne s’applique pas à Unified Communications Web API (UCWA), fourni dans les mises à jour cumulatives pour Lync Server 2013 : février 2013. 
  
Lorsque vous installez le Service de mobilité (Mcx) sur les Services Internet (IIS) 7.5, le programme d’installation du Service de mobilité configure certains paramètres de performances sur le serveur frontal. Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité. Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.
  
Voici les paramètres de performances :
  
### <a name="settings-for-mcx-on-iis-75"></a>Paramètres pour Mcx sur IIS 7.5

1. **maxConcurrentThreadsPerCPU** a la valeur zéro (0).
    
2. **maxConcurrentRequestsPerCPU** a la valeur zéro (0).
    
3. Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).
    
4. La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).
    

