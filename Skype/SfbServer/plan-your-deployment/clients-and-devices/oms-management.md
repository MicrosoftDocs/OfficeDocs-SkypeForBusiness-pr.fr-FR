---
title: Planification de la gestion de Skype Room Systems v2 avec OMS
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: Cet article décrit les considérations de planification pour l’utilisation de la Suite de gestion des opérations pour administrer les périphériques v2 de systèmes de salle Skype dans votre Skype d’implémentation Business Server.
ms.openlocfilehash: 14f6ba95e5b2bcf7619002bb2dbc1e9ae3eb474a
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295623"
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>Planification de la gestion de Skype Room Systems v2 avec OMS
 
 Cet article décrit les considérations de planification pour l’utilisation de la Suite de gestion des opérations pour administrer les périphériques v2 de systèmes de salle Skype dans votre Skype d’implémentation Business Server.
  
[Suite de gestion des opérations](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview) (OMS) est un ensemble de services de gestion qui ont été conçus dans le nuage à partir du début. Au lieu de déploiement et la gestion des ressources dans les locaux, OMS composants sont entièrement hébergés dans Azure. Configuration est minime, et vous pouvez être en cours d’exécution en réalité dans quelques minutes. Certaines tâches de personnalisation, il peut faciliter la gestion des systèmes de conférence v2 Skype salle systèmes en fournissant des notifications en temps réel de l’intégrité du système ou erreurs pour les systèmes de salle individuels et peut potentiellement évoluer à la gestion des milliers de systèmes de salle de Skype salles de conférence v2.
  
Cet article fournit une description de la configuration requise, conception/architecture et meilleures pratiques d’implémentation nécessaires pour implémenter la gestion des périphériques de conférence v2 Skype salle systèmes d’OMS et fournit des liens vers des articles détaillés sur l’implémentation OMS gestion de projets pour v2 Skype salle systèmes et informations de référence critiques pour une gestion courante OMS de salles de v2 Skype salle systèmes. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de gestion SRS à l’aide d’OMS](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application v2 de systèmes de salle Skype sur l’appareil de console écrit les événements dans le journal des événements Windows. Une fois installé, un agent OMS transfère les informations à OMS. 
  
Une fois configuré correctement, analyse OMS la charge utile JSON incorporée dans l’événement descriptions pour décrire comment fonctionne chaque système v2 de systèmes de salle Skype et les erreurs détectées. 
  
Un administrateur à l’aide d’OMS peut obtenir des notifications de Skype salle v2 systèmes qui sont en mode hors connexion ou est rencontre des défaillances matérielles, la connectivité ou application ainsi savoir si un système doit être redémarré. Le statut de chaque système est mis à jour toutes les cinq minutes de sorte que ces notifications sont étroitement associées aux mises à jour en temps réel.
  
## <a name="oms-requirements"></a>Configuration requise pour OMS

Vous devez posséder un abonnement valide pour OMS pour utiliser cette fonctionnalité. Consultez [Prise en main d’un espace de travail Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) pour créer un abonnement pour votre entreprise.
  
Vous devez vous familiariser autant que nécessaire avec l’utilisation du concepteur de vue d’OMS. Consultez [Vues dans des solutions de gestion dans Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views) pour en savoir plus.
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à OMS, créer des champs (comme décrit dans les [champs personnalisés](../../deploy/deploy-clients/with-oms.md#Custom_fields)) nécessaires pour analyser les informations qui seront envoyées à partir de consoles v2 de systèmes de salle Skype. Cela inclut la présentation du schéma JSON documenté dans [comprendre les entrées du journal](../../manage/skype-room-systems-v2/oms.md#Telemetry).
    
2. Développer un affichage de gestion des systèmes de salle Skype v2 dans OMS. Vous pouvez [créer un tableau de bord v2 Skype salle de systèmes à l’aide de la méthode import](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) ou [créer un tableau de bord v2 Skype salle systèmes manuellement](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Individuels Skype salle v2 Console requise

Chaque console v2 de systèmes de salle Skype est une application en cours d’exécution sur un périphérique 4 Surface en mode plein écran (normalement, il est configuré pour être la seule application peut s’exécuter sur le périphérique). Comme avec toute application Windows, l’application v2 de systèmes de salle Skype écrit des événements tels que des erreurs matérielles et de démarrage dans le journal des événements Windows. Ajout d’un agent OMS sur votre appareil v2 de systèmes de salle Skype permet de ces événements être collectés par OMS. (Pour plus d’informations, consultez [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents) .)
  
## <a name="ongoing-management"></a>Gestion continue

Lorsque vous utilisez OMS pour gérer vos périphériques de conférence Skype salle systèmes v2, vous devez comprendre les informations contenues dans les journaux des événements utilisés par OMS. Pour plus d’informations sur ces messages d’intégrité, voir [comprendre les entrées du journal](../../manage/skype-room-systems-v2/oms.md#Telemetry) .
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par des systèmes de salle Skype v2 et comment les résoudre (voir la section intitulée [comprendre les entrées du journal](../../manage/skype-room-systems-v2/oms.md#Telemetry))
    
## <a name="see-also"></a>Voir aussi

[Déploiement de la gestion de Skype Room Systems v2 avec OMS](../../deploy/deploy-clients/with-oms.md)
  
[Gestion des appareils Skype Room Systems v2 avec OMS](../../manage/skype-room-systems-v2/oms.md)