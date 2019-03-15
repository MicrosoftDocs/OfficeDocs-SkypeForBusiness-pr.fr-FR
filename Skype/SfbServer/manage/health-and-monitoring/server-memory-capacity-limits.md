---
title: Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Résumé : Apprenez à analyser pour les limites de capacité de mémoire de serveur dans Skype pour Business Server.'
ms.openlocfilehash: 6eb60d48e9da0736ac8753000343b5dc1458bacf
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226973"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server
 
**Résumé :** Apprenez à surveiller pour les limites de capacité de mémoire de serveur dans Skype pour Business Server.
  
> [!CAUTION]
> Les informations contenues dans cette rubrique fait référence à la planification de la capacité s’applique uniquement aux clients Lync 2010 Mobile et le Service de mobilité (Mcx). Planification de la capacité pour la Unified Communications Web API (UCWA), utilisé par les clients Lync 2013 Mobile, est fournie par l’outil de planification Lync Server 2013. 

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
Deux compteurs de performances de mobilité peuvent vous aider à déterminer votre utilisation actuelle et vous aider à planifier la capacité pour la Skype pour le Service de mobilité Business Server (Mcx), ainsi que pour surveiller l’utilisation de la mémoire pour UCWA. Pour UCWA, la catégorie de compteur est **LS:WEB - UCWA**. Pour le service de mobilité (Mcx), les compteurs se trouvent dans la catégorie **LS:WEB - Service de communication mobile**. Les compteurs à surveiller sont les suivants :
  
- **Nombre de sessions actives avec abonnements actifs aux informations de présence**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité (Mcx) dont les abonnements aux informations de présence sont actifs (nombre d’utilisateurs mobiles toujours connectés) ;
    
- **Nombre de sessions actives**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité.
    
Si la différence entre les compteurs **Nombre de sessions actives avec abonnements actifs aux informations de présence** et **Nombre de sessions actives** reste minime au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil toujours connecté, tel qu’un appareil mobile Android ou Nokia (pour Mcx uniquement). Les périphériques de toujours connectés UCWA incluent des appareils Apple et Android qui exécutent des clients Lync 2013 Mobile). Si le compteur **Nombre de sessions actives** est beaucoup plus élevé que le compteur **Nombre de sessions actives avec abonnements actifs aux informations de présence**, cela indique qu’un nombre plus élevé d’utilisateurs emploient un appareil à points de terminaison en arrière-plan, tel qu’un appareil Apple iOS ou Windows Phone sous Mcx. (Windows Phone est le seul client Lync 2013 Mobile qui est considérée comme ceci).
  
Vous devez définir une limite sur les compteurs de performance de **Sessions actuellement actives** et les **Sessions actuellement actives avec abonnements de présence actif** en fonction de votre utilisation prévue, résultats de la planification de la capacité et la surveillance en cours de Service de mobilité et d’autres compteurs de serveur frontal. Les limites que vous définissez doivent vous permettre d’évaluer la capacité des serveurs et de déclencher des alertes quand celle-ci est dépassée.
  
Pour déterminer les limites appropriées, vous devez d’abord déterminer la quantité de mémoire est disponible sur le serveur frontal pour le Service de mobilité. Surveillez les compteurs afin de déterminer le besoin de prévoir une capacité supplémentaire à l’aide de la formule suivante :
  
Nombre total de mémoire utilisée par le Service de mobilité Mcx (Mo) = 164 + (134 + 400) / 1024 * **Sessions actuellement actives avec abonnements de présence actif** + 400 / 1024 * ( **Sessions actuellement actives** - **nombre de sessions actuellement actives avec Abonnements de présence actifs**)
  
> [!IMPORTANT]
> Les capacités Microsoft Lync Server 2010 est une feuille de calcul est prérempli avec toutes les formules qui permettent d’un module afin de déterminer la configuration requise pour le Skype des serveurs d’entreprise, notamment le processeur, la mémoire et sur le disque dur. Vous pouvez [Télécharger la feuille de calcul et associé à un document](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Le serveur frontal doit suffisamment de mémoire pour prendre en charge le Service de mobilité dans les situations de basculement. Vous pouvez analyser la mémoire disponible en cours sur le serveur frontal à l’aide du compteur **Memory\Available Mbytes** , ou à l’aide de l’équation mentionnée plus haut, pour planifier la quantité de mémoire que vous prévoyez d’utiliser le Service de mobilité.
  
Si la quantité de mémoire disponible sur le serveur frontal est inférieure à 1 500 Mo lorsque vous planifiez le nombre prévu d’utilisateurs de mobilité, vous devez ajouter davantage de matériel pour prendre en charge le Service de mobilité. Pour plus d’informations, voir [mobilité Analyseur de performances dans Skype pour Business Server](monitor-mobility-performance.md) dans la documentation des opérations.
  
## <a name="see-also"></a>Voir aussi

[Surveiller la mobilité pour les performances dans Skype pour Business Server](monitor-mobility-performance.md)