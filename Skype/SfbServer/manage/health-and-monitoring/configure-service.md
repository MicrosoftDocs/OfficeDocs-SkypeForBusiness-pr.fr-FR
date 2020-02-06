---
title: Configurer le service de mobilité pour des performances élevées dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : en savoir plus sur le service de mobilité dans Skype entreprise Server.'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818054"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurer le service de mobilité pour des performances élevées dans Skype entreprise Server
 
**Résumé :** En savoir plus sur le service de mobilité dans Skype entreprise Server.
  
> [!IMPORTANT]
> Cette rubrique s’applique uniquement au service de mobilité Skype entreprise Server (MCX) et ne s’applique pas à l’API Unified Communications Web API (UCWA), telle que publiée dans les mises à jour cumulatives pour Lync Server 2013 : février 2013. 
  
Lorsque vous installez le service de mobilité (MCX) sur Internet Information Services (IIS) 7,5, le programme d’installation de service de mobilité configure certains paramètres de performance sur le serveur frontal. Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité. Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.
  
Voici les paramètres de performances :
  
### <a name="settings-for-mcx-on-iis-75"></a>Paramètres pour Mcx sur IIS 7.5

1. **maxConcurrentThreadsPerCPU** est fixé sur zéro (0).
    
2. **maxConcurrentRequestsPerCPU** est fixé sur zéro (0).
    
3. Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).
    
4. La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).
    

