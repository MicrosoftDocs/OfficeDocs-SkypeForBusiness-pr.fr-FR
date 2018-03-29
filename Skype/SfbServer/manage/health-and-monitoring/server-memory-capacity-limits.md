---
title: Surveillance des limites de capacité de mémoire des serveurs dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Résumé : Apprenez à surveiller pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015.'
ms.openlocfilehash: df05cdf43a7f09f49760f9671c900d6a9ea992b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server-2015"></a>Surveillance des limites de capacité de mémoire des serveurs dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à surveiller pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015.
  
> [!CAUTION]
> Les informations contenues dans cette rubrique fait référence à la planification de la capacité s’applique uniquement aux clients Lync 2010 Mobile et le Service de mobilité (Mcx). Planification de la capacité pour le Unified Communications Web API (UCWA), utilisé par les clients Lync 2013 Mobile, est fournie par l’outil de planification de Lync Server 2013. 
  
Deux compteurs de performance de mobilité peuvent vous aider à déterminer votre utilisation actuelle et vous aider à planifier la capacité pour le Skype pour le Service Business Server 2015 mobilité (Mcx), ainsi que pour surveiller l’utilisation de la mémoire pour UCWA. Pour UCWA, la catégorie de compteur est **LS:WEB - UCWA**. Pour le service de mobilité (Mcx), les compteurs se trouvent dans la catégorie **LS:WEB - Service de communication mobile**. Les compteurs à surveiller sont les suivants :
  
- **Nombre de sessions actives avec abonnements actifs aux informations de présence**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité (Mcx) dont les abonnements aux informations de présence sont actifs (nombre d’utilisateurs mobiles toujours connectés) ;
    
- **Nombre de sessions actives**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité.
    
Si la différence entre les compteurs **Nombre de sessions actives avec abonnements actifs aux informations de présence** et **Nombre de sessions actives** reste minime au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil toujours connecté, tel qu’un appareil mobile Android ou Nokia (pour Mcx uniquement). UCWA toujours périphériques comprennent les périphériques Apple et Android clients Lync 2013 Mobile en cours d’exécution). Si le compteur **Nombre de sessions actives** est beaucoup plus élevé que le compteur **Nombre de sessions actives avec abonnements actifs aux informations de présence**, cela indique qu’un nombre plus élevé d’utilisateurs emploient un appareil à points de terminaison en arrière-plan, tel qu’un appareil Apple iOS ou Windows Phone sous Mcx. (Windows Phone est le seul client Lync 2013 Mobile qui est considérée comme cela).
  
Vous devez définir une limite sur les compteurs de performance **Actuellement actives nombre de sessions avec les abonnements de présence Active** et le **Nombre de sessions actuellement actives** sur votre utilisation prévue pour les résultats de planification de capacité et la surveillance continue de la base Les services de mobilité et d’autres compteurs de serveur frontal. Les limites que vous définissez doivent vous permettre d’évaluer la capacité des serveurs et de déclencher des alertes quand celle-ci est dépassée.
  
Pour déterminer les limites appropriées, vous devez d’abord déterminer la quantité de mémoire est disponible sur le serveur frontal pour le Service de la mobilité. Surveillez les compteurs afin de déterminer le besoin de prévoir une capacité supplémentaire à l’aide de la formule suivante :
  
Utilisé par le Service de mobilité de Mcx (Mo) de mémoire totale = 164 + (400 + 134) / 1024 * **Actuellement actives nombre de sessions avec les abonnements de présence Active** + 400 / 1024 * ( **Nombre de sessions actuellement actives** - **nombre de sessions actuellement actives avec Les abonnements de présence Active**)
  
> [!IMPORTANT]
> La calculatrice de capacité Microsoft Lync Server 2010 est une feuille de calcul est préremplie avec toutes les formules qui permettent à un agent de planification déterminer la configuration requise pour le Skype des serveurs d’entreprise, y compris le processeur, mémoire et disque dur. Vous pouvez [Télécharger la feuille de calcul et associé à un document](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Le serveur frontal a besoin de suffisamment de mémoire pour prendre en charge le Service de la mobilité dans des situations de basculement. Vous pouvez surveiller la mémoire disponible en cours sur le serveur frontal à l’aide du compteur de **Mémoire\méga** , ou à l’aide de l’équation mentionnée précédemment, pour planifier la quantité de mémoire à laquelle le Service de la mobilité à utiliser.
  
Si la quantité de mémoire disponible sur le serveur frontal est inférieure à 1 500 Mo lorsque vous planifiez le nombre prévu d’utilisateurs de la mobilité, vous devez ajouter davantage de matériel pour prendre en charge le Service de la mobilité. Pour plus d’informations, consultez [mobilité du moniteur des performances dans Skype pour Business Server 2015](monitor-mobility-performance.md) dans la documentation sur les opérations.
  
## <a name="see-also"></a>Voir aussi

#### 

[Mobilité du moniteur des performances dans Skype pour Business Server 2015](monitor-mobility-performance.md)

