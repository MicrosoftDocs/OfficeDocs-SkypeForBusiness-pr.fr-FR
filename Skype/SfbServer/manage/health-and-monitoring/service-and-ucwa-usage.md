---
title: Surveillance de l’utilisation du service de mobilité et UCWA dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérer le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a>Surveillance de l’utilisation du service de mobilité et UCWA dans Skype Entreprise Server 2015
 
**Résumé :** Gérer le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.
  
Régulièrement, vous devez analyser le processeur et la mémoire qui est utilisée par le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée. Pour cela, vous pouvez utiliser l’un des éléments suivants :
  
 **Pour l’API web de communications unifiées (UCWA) :**
  
- Le processus de travail **LyncUcwa** , dans le Gestionnaire des Services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %. Utilisation de la mémoire doit être dans les limites décrites dans le [moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **LS:WEB - la limitation et Authentication\WEB - nombre Total de demandes dans le traitement de**, qui indique le nombre de demandes web sur le serveur en attente. Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **La file d’attente ASP.NET\Requests** (doit être toujours égal à zéro).
    
> [!NOTE]
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web. 
  
 **Pour le service de mobilité (Mcx) :**
  
- Les processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le Gestionnaire des Services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %. Utilisation de la mémoire doit être dans les limites décrites dans le [moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **ASP.NET v2.0.50727\Requests actuel**, qui indique le nombre de demandes web sur le serveur en attente. Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **La file d’attente ASP.NET\Requests** (doit être toujours égal à zéro).
    
> [!NOTE]
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web. 
  
## <a name="see-also"></a>Voir aussi

#### 

[Moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015](server-memory-capacity-limits.md)

