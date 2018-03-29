---
title: Configuration du service de mobilité pour de hautes performances dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : En savoir plus sur le Service de la mobilité dans Skype pour Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>Configuration du service de mobilité pour de hautes performances dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur le Service de la mobilité dans Skype pour Business Server 2015.
  
> [!IMPORTANT]
> Cette rubrique s’applique uniquement à la Skype pour Service de mobilité 2015 Business Server (Mcx) et ne s’applique pas aux Unified Communications Web API (UCWA), fourni dans les mises à jour cumulatives de Lync Server 2013 : février 2013. 
  
Lorsque vous installez le Service de mobilité (Mcx) sur les Services Internet (IIS) 7.5, le programme d’installation du Service de la mobilité configure certains paramètres de performances sur le serveur frontal. Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité. Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.
  
Voici les paramètres de performances :
  
### <a name="settings-for-mcx-on-iis-75"></a>Paramètres pour Mcx sur IIS 7.5

1. **maxConcurrentThreadsPerCPU** a la valeur zéro (0).
    
2. **maxConcurrentRequestsPerCPU** a la valeur zéro (0).
    
3. Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).
    
4. La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).
    

