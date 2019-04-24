---
title: Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérer le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.'
ms.openlocfilehash: 79516ec6cf5371061a0287e70e6ed81f8b2a5395
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197498"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server
 
**Résumé :** Gérer le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
De manière continue, vous devez surveiller le processeur et la mémoire utilisée par le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée. Pour cela, vous pouvez utiliser l’un des éléments suivants :
  
 **Pour l’API web de communications unifiées (UCWA) :**
  
- Le processus de travail **LyncUcwa** dans le Gestionnaire des Services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %. Utilisation de la mémoire doit être dans les limites décrites dans [surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **LS:WEB - limitation et Authentication\WEB - nombre Total de demandes de traitement en**, qui indique le nombre de demandes web sur le serveur en attente. Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **ASP.NET\Requests Queued** (doit toujours être égal à zéro).
    
> [!NOTE]
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web. 
  
 **Pour le service de mobilité (Mcx) :**
  
- Processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le Gestionnaire des Services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %. Utilisation de la mémoire doit être dans les limites décrites dans [surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **ASP.NET v2.0.50727\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur. Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **ASP.NET\Requests Queued** (doit toujours être égal à zéro).
    
> [!NOTE]
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web. 

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
## <a name="see-also"></a>Voir aussi

[Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md)
