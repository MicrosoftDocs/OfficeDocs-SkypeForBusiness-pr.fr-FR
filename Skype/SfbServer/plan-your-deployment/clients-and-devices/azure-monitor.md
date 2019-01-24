---
title: Planifier la gestion des systèmes de salle Skype v2 avec Azure moniteur
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: Cet article décrit les considérations de planification pour l’utilisation du moniteur d’Azure pour administrer les périphériques v2 de systèmes de salle Skype dans votre Skype pour l’implémentation des équipes ou de l’entreprise.
ms.openlocfilehash: 53f77f1353668e4887a6ff41efd040dc8f418c7e
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448450"
---
# <a name="plan-skype-room-systems-v2-management-with-azure-monitor"></a>Planifier la gestion des systèmes de salle Skype v2 avec Azure moniteur
 
 Cet article décrit les considérations de planification pour l’utilisation du moniteur d’Azure pour administrer les périphériques v2 de systèmes de salle Skype dans votre Skype d’implémentation Business Server.
  
[Moniteur Azure](https://docs.microsoft.com/azure/azure-monitor/overview) est un ensemble de services de gestion qui ont été conçus dans le nuage à partir du début. Au lieu de déploiement et la gestion des ressources dans les locaux, moniteur Azure composants sont entièrement hébergés dans Azure. Configuration est minime, et vous pouvez être en cours d’exécution en réalité dans quelques minutes. Certaines tâches de personnalisation, il peut faciliter la gestion des systèmes de conférence v2 Skype salle systèmes en fournissant des notifications en temps réel de l’intégrité du système ou erreurs pour les systèmes de salle individuels et peut potentiellement évoluer à la gestion des milliers de systèmes de salle de Skype salles de conférence v2.
  
Cet article fournit une description de la configuration requise, conception/architecture et meilleures pratiques d’implémentation nécessaires pour implémenter la gestion d’Azure moniteur en fonction des périphériques de conférence Skype salle systèmes v2 et fournit des liens vers des articles détaillés sur implémentation de moniteur Azure pour v2 Skype salle systèmes et informations de référence critique pour la surveillance continue de salles de v2 Skype salle systèmes. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de la gestion de SRS à l’aide d’Azure moniteur](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application v2 de systèmes de salle Skype sur l’appareil de console écrit les événements dans le journal des événements Windows. Un agent Microsoft Monitoring, une fois installé, transmet les informations sur le service de surveillance Azure. 
  
Une fois configuré correctement, analyse Analytique journal la charge utile JSON incorporée dans l’événement descriptions pour décrire comment fonctionne chaque système v2 de systèmes de salle Skype et les erreurs détectées. 
  
Administrateur de l’utilisation du moniteur Azure peuvent obtenir des notifications de Skype salle v2 systèmes qui sont en mode hors connexion ou est rencontre des défaillances matérielles, la connectivité ou application ainsi savoir si un système doit être redémarré. Chaque état du système est mis à jour fréquemment, afin que ces notifications sont Fermer pour mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Exigences de surveillance Azure

Vous devez disposer d’un abonnement Azure valide pour surveiller Azure utiliser la fonctionnalité de journal Analytique. Consultez Prise en main d’un espace de travail Log Analytics pour créer un abonnement pour votre entreprise.
  
Vous devez vous familiariser nécessaires sur l’utilisation du Concepteur de vues Analytique journal. Pour les plus d’informations, voir [vues dans le journal Analytique](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à Azure moniteur journal Analytique, créer des champs (comme décrit dans les [champs personnalisés](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) nécessaires pour analyser les informations qui seront envoyées à partir de consoles v2 de systèmes de salle Skype. Cela inclut la présentation du schéma JSON documenté dans [comprendre les entrées du journal](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).
    
2. Développer une vue de gestion de systèmes de salle Skype v2 dans journal Analytique. Vous pouvez [créer un tableau de bord v2 Skype salle de systèmes à l’aide de la méthode import](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) ou [créer un tableau de bord v2 Skype salle systèmes manuellement](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Individuels Skype salle v2 Console requise

Chaque console v2 de systèmes de salle Skype est une application en cours d’exécution sur un appareil Surface Pro en mode plein écran (normalement, il est configuré pour être la seule application peut s’exécuter sur le périphérique). Comme avec toute application Windows, l’application v2 de systèmes de salle Skype écrit des événements tels que des erreurs matérielles et de démarrage dans le journal des événements Windows. Ajout d’un agent Microsoft Monitor sur votre appareil v2 de systèmes de salle Skype permet de ces événements doivent être collectés. (Pour plus d’informations, consultez [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Gestion continue

Lorsque vous utilisez moniteur Azure pour gérer vos périphériques v2 de systèmes de salle Skype, vous devez comprendre les informations contenues dans les journaux des événements utilisés par l’analyseur Azure. Pour plus d’informations sur ces messages d’intégrité, voir [comprendre les entrées du journal](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par des systèmes de salle Skype v2 et comment les résoudre (voir la section intitulée [comprendre les entrées du journal](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))
    
## <a name="see-also"></a>Voir aussi

[Déployer une gestion Skype salle systèmes v2 avec Azure moniteur](../../deploy/deploy-clients/azure-monitor.md)
  
[Gérer les systèmes de salle Skype v2 périphériques avec Azure moniteur](../../manage/skype-room-systems-v2/azure-monitor.md)