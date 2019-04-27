---
title: Planifier la gestion des salles d’équipes Microsoft Azure moniteur
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: Cet article décrit les considérations de planification pour l’utilisation du moniteur d’Azure pour administrer les périphériques de salles d’équipes Microsoft dans votre Skype pour l’implémentation des équipes ou de l’entreprise.
ms.openlocfilehash: 67a74d0bd02465d1a84856238e3e65a049b23ab4
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362769"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planifier la gestion des salles d’équipes Microsoft Azure moniteur
 
 Cet article décrit les considérations de planification pour l’utilisation du moniteur d’Azure pour administrer des équipements locaux des équipes Microsoft au Microsoft Teams ou Skype pour l’implémentation de l’activité.
  
[Moniteur Azure](https://docs.microsoft.com/azure/azure-monitor/overview) est un ensemble de services de gestion qui ont été conçus dans le nuage à partir du début. Au lieu de déploiement et la gestion des ressources dans les locaux, moniteur Azure composants sont entièrement hébergés dans Azure. Configuration est minime, et vous pouvez être en cours d’exécution en réalité dans quelques minutes. Certaines tâches de personnalisation, il peut faciliter la gestion des systèmes de conférence Microsoft équipes salles en fournissant des notifications en temps réel de l’intégrité du système ou erreurs pour les systèmes de salle individuels et peut potentiellement évoluer à la gestion des milliers de Microsoft Teams Salles de conférence de salles.
  
Cet article fournit une description de la configuration requise, conception/architecture et meilleures pratiques d’implémentation nécessaires pour implémenter la gestion d’Azure moniteur en fonction des périphériques de conférence Microsoft équipes salles et fournit des liens vers des articles détaillés sur l’implémentation de moniteur Azure pour les salles d’équipes Microsoft et des informations de référence critiques l’analyse continue de salles de salles d’équipes Microsoft. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de la gestion de salles d’équipes Microsoft à l’aide d’Azure moniteur](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application Microsoft équipes salles sur l’appareil de console écrit les événements dans le journal des événements Windows. Un agent Microsoft Monitoring, une fois installé, transmet les informations sur le service de surveillance Azure. 
  
Une fois configuré correctement, analyse Analytique journal la charge utile JSON incorporée dans l’événement descriptions pour décrire comment fonctionne chaque système salles d’équipes Microsoft et les erreurs détectées. 
  
Administrateur de l’utilisation du moniteur Azure peuvent obtenir des notifications de systèmes de salles d’équipes Microsoft qui sont en mode hors connexion ou est rencontre des défaillances matérielles, la connectivité ou application ainsi savoir si un système doit être redémarré. Chaque état du système est mis à jour fréquemment, afin que ces notifications sont Fermer pour mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Exigences de surveillance Azure

Vous devez disposer d’un abonnement Azure valide pour surveiller Azure utiliser la fonctionnalité de journal Analytique. Voir [commencer avec un espace de travail journal Analytique](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) pour créer un abonnement pour votre organisation.
  
Vous devez vous familiariser nécessaires sur l’utilisation du Concepteur de vues Analytique journal. Pour les plus d’informations, voir [vues dans le journal Analytique](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à Azure moniteur journal Analytique, créer des champs (comme décrit dans les [champs personnalisés](azure-monitor-deploy.md#Custom_fields)) nécessaires pour analyser les informations qui seront envoyées à partir de consoles salles d’équipes Microsoft. Cela inclut la présentation du schéma JSON documenté dans [comprendre les entrées du journal](azure-monitor-manage.md#understand-the-log-entries).
    
2. Développer une vue de gestion Microsoft équipes salles dans journal Analytique. Vous pouvez [créer un tableau de bord Microsoft équipes salles à l’aide de la méthode import](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) ou [créer un tableau de bord Microsoft équipes salles manuellement](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Besoins individuels de Console de salles d’équipes Microsoft

Chaque console salles d’équipes Microsoft est une application en cours d’exécution sur un appareil Surface Pro en mode plein écran (normalement, il est configuré pour être la seule application peut s’exécuter sur le périphérique). Comme avec toute application Windows, l’application Microsoft équipes salles écrit des événements tels que des erreurs matérielles et de démarrage dans le journal des événements Windows. Ajout d’un agent Microsoft Monitor sur votre appareil Microsoft équipes salles permet de ces événements doivent être collectés. (Pour plus d’informations, consultez [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Gestion continue

Lorsque vous utilisez moniteur Azure pour gérer vos périphériques salles des équipes Microsoft, vous devez comprendre les informations contenues dans les journaux des événements utilisés par l’analyseur Azure. Pour plus d’informations sur ces messages d’intégrité, voir [comprendre les entrées du journal](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par Microsoft équipes salles et comment les résoudre (voir la section intitulée [comprendre les entrées du journal](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Voir aussi

[Déployer la gestion des salles d’équipes Microsoft Azure moniteur](azure-monitor-deploy.md)
  
[Gérer les périphériques de salles d’équipes Microsoft Azure moniteur](azure-monitor-manage.md)