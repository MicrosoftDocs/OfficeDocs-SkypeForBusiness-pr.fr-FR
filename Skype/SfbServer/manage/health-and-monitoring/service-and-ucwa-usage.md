---
title: Surveiller l’utilisation du service de mobilité et de l’UCWA dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.'
ms.openlocfilehash: d7596bfaf4e90f0eef25dbc625719f8739255858
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393766"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Surveiller l’utilisation du service de mobilité et de l’UCWA dans Skype Entreprise Server
 
**Résumé :** Gérez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
Régulièrement, vous devez surveiller le processeur et la mémoire utilisés par le service de mobilité Skype Entreprise Server (Mcx) et l’API web de communications unifiées (UCWA). Pour surveiller l’utilisation, vous pouvez utiliser les ressources suivantes :
  
 **Pour l’API web de communications unifiées (UCWA) :**
  
- Processus **de travail LyncUcwa** dans Internet Information Services (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur UCWA doit être inférieure à 15 % en moyenne. L’utilisation de la mémoire doit être dans les limites décrites dans [monitor for server memory capacity limits in Skype Entreprise Server](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performance suivants pour déterminer quand un serveur est surchargé de demandes :
  
- **LS:WEB - Limitation et authentification\WEB - Nombre total** de demandes en cours de traitement, ce qui indique le nombre de demandes web en attente sur le serveur. Lorsque ce compteur atteint 10 000, les demandes suivantes échouent, avec le message d’erreur « 503 - Service indisponible ».
    
- **ASP.NET\Requests Queued** (doit toujours être égal à zéro).
    
> [!NOTE]
> Si vous respectez ou dépassez ces valeurs, vous devez revoir et re calculer votre planification de la capacité pour le resserrage correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services web. 
  
 **Pour le service de mobilité (Mcx) :**
  
- Processus **de travail CSIntMcxAppPool** et **CSExtMcxAppPool** dans Internet Information Services (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur du service de mobilité doit être inférieure à 15 % en moyenne. L’utilisation de la mémoire doit être dans les limites décrites dans [monitor for server memory capacity limits in Skype Entreprise Server](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **ASP.NET v2.0.50727\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur. Lorsque ce compteur atteint 5 000, les demandes suivantes échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **ASP.NET\Requests Queued** (doit toujours être égal à zéro).
    
> [!NOTE]
> Si vous respectez ou dépassez ces valeurs, vous devez revoir et recompiler votre planification de capacité pour le recalcul correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services web. 

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
## <a name="see-also"></a>Voir aussi

[Surveiller les limites de capacité de mémoire du serveur dans Skype Entreprise Server](server-memory-capacity-limits.md)
