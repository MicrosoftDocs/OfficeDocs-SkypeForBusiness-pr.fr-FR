---
title: Planification de la gestion de Skype Room Systems v2 avec OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: " Cet article traite des aspects liés à la planification de l’utilisation d’Operations Management Suite pour administrer les appareils Skype Room Systems v2 au sein de votre implémentation Skype Entreprise Server 2015."
ms.openlocfilehash: e6409370da3597623526379581081e617f48dd81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>Planification de la gestion de Skype Room Systems v2 avec OMS
 
  Cet article traite des aspects liés à la planification de l’utilisation d’Operations Management Suite pour administrer les appareils Skype Room Systems v2 au sein de votre implémentation Skype Entreprise Server 2015.
  
[Suite de gestion des opérations](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview) (OMS) est un ensemble de services de gestion qui ont été conçus dans le nuage à partir du début. Au lieu de déploiement et de gestion des ressources sur site, OMS composants sont entièrement hébergés dans Azure. La configuration est minime, et vous pouvez être en cours d’exécution littéralement dans quelques minutes. Avec un travail de personnalisation, il peut vous aider dans la gestion des systèmes de conférence v2 Skype salle systèmes grâce à des notifications en temps réel de l’état du système ou des défauts pour les systèmes individuels d’espace, et il peut potentiellement évoluer à la gestion de milliers de systèmes de salle de Skype salles de conférence v2.
  
Cet article fournit une description des exigences, conception/architecture et meilleures pratiques d’implémentation nécessaires pour implémenter la gestion d’OMS de dispositifs de conférence Skype salle systèmes v2 et fournit des liens vers des articles détaillés sur l’implémentation d’OMS informations pour la gestion de salles de systèmes de salle Skype v2 OMS de référence de gestion pour systèmes de salle Skype v2 et critiques. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de gestion SRS à l’aide d’OMS](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application v2 de systèmes de salle Skype sur le périphérique de console écrit des événements dans son journal des événements Windows. Une fois installé, un agent OMS transfère les informations à OMS. 
  
Une fois correctement configuré, analyse OMS la charge utile JSON incorporé dans l’événement descriptions, pour décrire le fonctionne de chaque système v2 de systèmes de salle Skype et les erreurs sont détectées. 
  
Un administrateur à l’aide d’OMS peut obtenir des notifications de Skype salle v2 systèmes qui sont en mode hors connexion ou est rencontre des applications, la connectivité ou pannes matérielles ainsi savoir si un système doit être redémarré. Le statut de chaque système est mis à jour toutes les cinq minutes de sorte que ces notifications sont étroitement associées aux mises à jour en temps réel.
  
## <a name="oms-requirements"></a>Configuration requise pour OMS

Vous devez posséder un abonnement valide pour OMS pour utiliser cette fonctionnalité. Reportez-vous à la section [mise en route avec un espace de travail du journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) pour créer un abonnement pour votre organisation.
  
Vous devez vous familiariser autant que nécessaire avec l’utilisation du concepteur de vue d’OMS. Pour les détails, reportez-vous à la section [vues dans les solutions de gestion des opérations de gestion Suite (OMS)](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views) .
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à OMS, créez des champs personnalisés (décrites dans les [champs personnalisés](../../deploy/deploy-clients/with-oms.md#Custom_fields)) nécessaires pour analyser les informations qui seront envoyées à partir de consoles v2 de systèmes de salle de Skype. Cela inclut la présentation du schéma JSON documenté dans [comprendre les entrées du journal](../../manage/skype-room-systems-v2/oms.md#Telemetry).
    
2. Créer une vue de gestion de systèmes de salle Skype v2 dans OMS (voir [vues de définir le v2 SRS dans OMS](../../deploy/deploy-clients/with-oms.md#Views)) en utilisant le Concepteur de vue mentionné précédemment.
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Individuels Skype salle v2 Console requise

Chaque console v2 de systèmes de salle de Skype est une application qui s’exécute sur un périphérique 4 de la Surface en mode plein écran (en règle générale, il est configuré pour être la seule application pouvant s’exécuter sur le périphérique). Comme avec n’importe quelle application Windows, l’application v2 de systèmes de salle Skype écrit les événements tels que des erreurs matérielles et de démarrage dans le journal des événements Windows. Ajout d’un agent de l’OMS sur votre appareil v2 de systèmes de salle Skype permet de ces événements à collecter par l’OMS. (Pour plus d’informations, voir [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents) .)
  
## <a name="ongoing-management"></a>Gestion continue

Lorsque vous utilisez OMS pour gérer vos périphériques de conférence Skype salle systèmes v2, vous devez comprendre les informations contenues dans les journaux des événements utilisés par l’OMS. Pour plus d’informations sur ces messages d’état de santé, voir [comprendre les entrées du journal](../../manage/skype-room-systems-v2/oms.md#Telemetry) .
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par les systèmes de salle Skype v2 et comment y remédier (voir la section [comprendre les entrées du journal](../../manage/skype-room-systems-v2/oms.md#Telemetry))
    
## <a name="see-also"></a>Voir aussi

#### 

[Déployer une gestion systèmes de salle Skype v2 avec OMS](../../deploy/deploy-clients/with-oms.md)
  
[Gérer les périphériques de v2 Skype salle systèmes avec OMS](../../manage/skype-room-systems-v2/oms.md)

