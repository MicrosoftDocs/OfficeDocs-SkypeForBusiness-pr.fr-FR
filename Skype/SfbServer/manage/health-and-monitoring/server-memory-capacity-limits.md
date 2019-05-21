---
title: Surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Résumé: Découvrez comment surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server.'
ms.openlocfilehash: f089ab9b5be693872754691050133ad27e992896
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279822"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server
 
**Résumé:** Découvrez comment surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server.
  
> [!CAUTION]
> Les informations dans cette rubrique faisant référence à la planification de la capacité uniquement aux clients mobiles Lync 2010 et au service de mobilité (MCX). La planification de la capacité de l’API Web de communications unifiées (UCWA), qui est utilisée par les clients mobiles Lync 2013, est fournie par l’outil de planification de Lync Server 2013. 

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
Deux compteurs de performance de mobilité peuvent vous aider à déterminer votre utilisation actuelle et à planifier la capacité du service de mobilité Skype entreprise Server (MCX), ainsi que l’utilisation de la mémoire pour UCWA. Pour UCWA, la catégorie de compteur est **ls: Web-UCWA**. Pour le service de mobilité (Mcx), les compteurs se trouvent dans la catégorie **LS:WEB - Service de communication mobile**. Les compteurs à surveiller sont les suivants :
  
- **Nombre de sessions actives avec abonnements actifs aux informations de présence**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité (Mcx) dont les abonnements aux informations de présence sont actifs (nombre d’utilisateurs mobiles toujours connectés) ;
    
- **Nombre de sessions actives**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité.
    
Si la différence entre les compteurs **Nombre de sessions actives avec abonnements actifs aux informations de présence** et **Nombre de sessions actives** reste minime au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil toujours connecté, tel qu’un appareil mobile Android ou Nokia (pour Mcx uniquement). Les appareils UCWA toujours connectés incluent des appareils Apple et Android exécutant des clients mobiles Lync 2013. Si le compteur **Nombre de sessions actives** est beaucoup plus élevé que le compteur **Nombre de sessions actives avec abonnements actifs aux informations de présence**, cela indique qu’un nombre plus élevé d’utilisateurs emploient un appareil à points de terminaison en arrière-plan, tel qu’un appareil Apple iOS ou Windows Phone sous Mcx. (Windows Phone est le seul client mobile Lync 2013 qui s’inscrira comme suit).
  
Vous devez définir une limite sur le **nombre de sessions actuellement actives avec abonnements de présence actives** et compteurs de performance **actuellement nombre de sessions actives** en fonction de votre utilisation prévue, des résultats de planification de la capacité et de la surveillance en continu de Service de mobilité et autres compteurs serveur front-end. Les limites que vous définissez doivent vous permettre d’évaluer la capacité des serveurs et de déclencher des alertes quand celle-ci est dépassée.
  
Pour déterminer les limites appropriées, vous devez d’abord déterminer la quantité de mémoire disponible sur le serveur frontal pour le service de mobilité. Surveillez les compteurs afin de déterminer le besoin de prévoir une capacité supplémentaire à l’aide de la formule suivante :
  
Mémoire totale utilisée par le service de mobilité MCX (Mo) = 164 + (400 + 134)/1024 * **nombre de sessions actives avec les abonnements de présence actives** + 400/1024 * ( **actuellement** - actif nombre de sessions actives**avec Abonnements de présence actifs**)
  
> [!IMPORTANT]
> Le calculateur de capacités de Microsoft Lync Server 2010 est une feuille de calcul préremplie avec toutes les formules permettant à un planificateur de déterminer quelles sont les conditions requises pour les serveurs Skype entreprise, notamment les ressources processeur, mémoire et disque dur. Vous pouvez [Télécharger la feuille de calcul et un document associé](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Le serveur frontal doit disposer de suffisamment de mémoire pour prendre en charge le service de mobilité dans les situations de basculement. Vous pouvez contrôler la quantité de mémoire disponible sur le serveur frontal à l’aide du compteur **Mo** de mémoire vive (en anglais), ou en utilisant l’équation mentionnée plus haut, afin de planifier la quantité de mémoire que le service de mobilité doit utiliser.
  
Si le volume de mémoire disponible sur le serveur frontal est inférieur à 1 500 Mo lorsque vous planifiez le nombre d’utilisateurs de mobilité attendus, vous devez ajouter davantage de matériel pour la prise en charge du service de mobilité. Pour plus d’informations, reportez-vous à la section [surveiller la mobilité dans Skype entreprise Server](monitor-mobility-performance.md) dans la documentation sur les opérations.
  
## <a name="see-also"></a>Voir aussi

[Surveiller la mobilité des performances dans Skype entreprise Server](monitor-mobility-performance.md)
