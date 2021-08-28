---
title: Configurer le service de mobilité pour des performances élevées dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : Découvrez le service de mobilité dans Skype Entreprise Server.'
ms.openlocfilehash: da2685faae6bf44fee212132dba6a0f7e0fe2e76
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621030"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurer le service de mobilité pour des performances élevées dans Skype Entreprise Server
 
**Résumé :** Découvrez le service de mobilité dans Skype Entreprise Server.
  
> [!IMPORTANT]
> Cette rubrique s’applique uniquement au service de mobilité Skype Entreprise Server (Mcx) et ne s’applique pas à l’API web de communications unifiées (UCWA), comme remis dans les mises à jour cumulatives pour Lync Server 2013 : février 2013. 
  
Lorsque vous installez le service de mobilité (Mcx) sur Internet Information Services (IIS) 7.5, le programme d’installation du service de mobilité configure certains paramètres de performances sur le serveur frontal. Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité. Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.
  
Voici les paramètres de performances :
  
### <a name="settings-for-mcx-on-iis-75"></a>Paramètres mcx sur IIS 7.5

1. **maxConcurrentThreadsPerCPU** a la valeur zéro (0).
    
2. **maxConcurrentRequestsPerCPU** a la valeur zéro (0).
    
3. Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).
    
4. La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).
    

