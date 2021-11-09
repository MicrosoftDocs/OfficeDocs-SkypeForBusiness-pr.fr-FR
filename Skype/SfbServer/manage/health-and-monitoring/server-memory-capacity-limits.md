---
title: Surveiller les limites de capacité de mémoire du serveur dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Résumé : Découvrez comment surveiller les limites de capacité de mémoire des serveurs dans Skype Entreprise Server.'
ms.openlocfilehash: e66d1fd318af5848b91110780d325fa78e3d21ce
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860081"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Surveiller les limites de capacité de mémoire du serveur dans Skype Entreprise Server
 
**Résumé :** Découvrez comment surveiller les limites de capacité de mémoire des serveurs dans Skype Entreprise Server.
  
> [!CAUTION]
> Les informations de cette rubrique qui font référence à la planification de la capacité concernent uniquement les clients Lync 2010 Mobile et le service de mobilité (Mcx). La planification de la capacité pour l’API web de communications unifiées (UCWA), utilisée par les clients Lync 2013 Mobile, est fournie par l’outil de planification Lync Server 2013. 

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
Deux compteurs de performances de mobilité peuvent vous aider à déterminer votre utilisation actuelle et à planifier la capacité du service Skype Entreprise Server Mobility Service (Mcx), ainsi qu’à surveiller l’utilisation de la mémoire pour UCWA. Pour UCWA, la catégorie de compteur est **LS:WEB - UCWA**. Pour le service de mobilité (Mcx), les compteurs sont sous la catégorie **LS:WEB - Mobile Communication Service**. Les compteurs à surveiller sont :
  
- Nombre de sessions actuellement actives avec **abonnements** de présence actifs, qui est le nombre actuel de points de terminaison enregistrés via UCWA ou le service de mobilité (Mcx) qui disposent d’abonnements de présence actifs (nombre d’utilisateurs mobiles toujours connectés)
    
- **Nombre de sessions** actuellement actives, qui est le nombre actuel de points de terminaison enregistrés via UCWA ou le service de mobilité
    
Si la différence entre le nombre de **sessions actives** avec abonnements de présence actifs et le nombre de **sessions** actives est faible au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil toujours connecté, tel qu’un appareil mobile Android ou Nokia (pour Mcx uniquement). Les appareils UCWA toujours connectés incluent les appareils Apple et Android exécutant des clients Lync 2013 Mobile). Si le nombre de **sessions** actuellement actives est beaucoup plus élevé que le nombre de **sessions actives** avec abonnements de présence actifs, cela indique que plus d’utilisateurs utilisent un appareil de point de terminaison en arrière-plan, tel qu’un appareil Apple iOS ou Windows Phone sous Mcx. (Windows Phone est le seul client Lync 2013 Mobile à s’inscrire comme ceci).
  
Vous devez définir une limite sur le nombre de  **sessions actives** avec abonnements de présence actifs et compteurs de performances nombre de sessions actives en fonction de votre utilisation attendue, des résultats de planification de la capacité et de la surveillance continue du service de mobilité et d’autres compteurs de serveur frontal. Les limites que vous définissez doivent vous permettre d’évaluer la capacité du serveur et de créer des alertes lorsque la capacité est dépassée.
  
Pour déterminer les limites appropriées, vous devez d’abord déterminer la quantité de mémoire disponible sur le serveur frontal pour le service de mobilité. Surveillez les compteurs pour déterminer quand vous devez planifier une capacité supplémentaire, selon la formule suivante :
  
Mémoire totale utilisée par le service de mobilité Mcx (Mo) = 164 + (400 + 134) / 1024 * Nombre de **sessions actives** avec abonnements de présence actifs + 400 / 1024 * ( Nombre de **sessions** actuellement actives avec abonnements de présence  -  **actifs)**
  
> [!IMPORTANT]
> La calculatrice de capacité Microsoft Lync Server 2010 est une feuille de calcul prérepxée avec toutes les formules qui permettent à un planificateur de déterminer les conditions requises pour les serveurs Skype Entreprise, y compris le processeur, la mémoire et le disque dur. Vous pouvez [télécharger la feuille de calcul et un document associé.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
Le serveur frontal a besoin de suffisamment de mémoire disponible pour prendre en charge le service de mobilité en cas de panne. Vous pouvez surveiller la mémoire disponible actuelle sur le serveur frontal à l’aide du compteur **Memory\Available Mbytes,** ou à l’aide de l’équation mentionnée précédemment, pour planifier la quantité de mémoire que le service de mobilité utilisera.
  
Si la quantité de mémoire disponible sur le serveur frontal est inférieure à 1 500 Mo lorsque vous planifiez le nombre attendu d’utilisateurs de mobilité, vous devez ajouter du matériel supplémentaire pour prendre en charge le service de mobilité. Pour plus d’informations, voir [Monitor mobility for performance in Skype Entreprise Server](monitor-mobility-performance.md) in the Operations documentation.
  
## <a name="see-also"></a>Voir aussi

[Surveiller les performances de la mobilité dans Skype Entreprise Server](monitor-mobility-performance.md)
