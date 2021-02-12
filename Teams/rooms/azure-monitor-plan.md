---
title: Planifier la gestion des salles Microsoft Teams à l’aide d’Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: Cet article décrit la planification de l’utilisation du moniteur Azure pour gérer les appareils Salle Microsoft Teams dans votre implémentation de Skype Entreprise ou Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137604"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planifier la gestion des salles Microsoft Teams à l’aide d’Azure Monitor
 
 Cet article décrit la planification de l’utilisation du moniteur Azure pour gérer les appareils Microsoft Teams Rooms dans votre application Microsoft Teams ou Skype Entreprise.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) est un ensemble de services de gestion conçus dans le cloud depuis le début. Plutôt que de déployer et de gérer des ressources sur site, les composants du moniteur Azure sont entièrement hébergés dans Azure. La configuration est minimale et vous pouvez être opérationnel littéralement en quelques minutes. Grâce à certaines opérations de personnalisation, elle peut vous aider à gérer les systèmes de conférence de salle Microsoft Teams en fournissant des notifications en temps réel concernant l’état ou les défaillances du système pour les systèmes de salle individuels, et peut potentiellement augmenter jusqu’à la gestion de milliers de salles de conférence Microsoft Teams.
  
Cet article fournit une discussion sur les conditions, la conception/architecture et les meilleures pratiques de mise en œuvre nécessaires pour implémenter la gestion Azure Monitor basée sur la gestion des périphériques de conférence Microsoft Teams Rooms, et fournit des liens vers des articles détaillés sur l’implémentation d’Azure Monitor pour les salles Microsoft Teams et des informations de référence critiques pour la surveillance continue des salles salles Microsoft Teams. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![Diagramme de la gestion des salles Microsoft Teams à l’aide d’Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application Salles Microsoft Teams sur l’appareil de la console écrit les événements dans son journal des événements Windows. Une fois l’installation installée, un agent de surveillance Microsoft transmet les informations au service Azure Monitor. 
  
Une fois configurée correctement, l’analyse journal analyse la charge utile JSON incorporée dans les descriptions des événements pour décrire le fonctionnement de chaque système de salles Microsoft Teams et les erreurs détectées. 
  
Un administrateur qui utilise Azure Monitor peut recevoir des notifications concernant les systèmes Salles Microsoft Teams hors connexion ou qui rencontrent des problèmes d’application, de connectivité ou de matériel, ainsi que pour savoir si un système doit être redémarré. Chaque état du système est fréquemment mis à jour, de sorte que ces notifications sont proches des mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor requirements

Vous devez avoir un abonnement Azure valide pour qu’Azure Monitor utilise la fonctionnalité Analyse des journaux. Pour créer un abonnement pour votre organisation, voir Mise en route [d’un](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) espace de travail Analyse journal.
  
Familiarisez-vous si nécessaire pour utiliser le Concepteur d’affichage d’analyse de journaux. Pour [plus d’informations, voir](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) Affichages dans l’analyse des journaux.
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à Azure Monitor Log Analytics, créez des champs personnalisés (comme décrit dans champs personnalisés [de](azure-monitor-deploy.md#Custom_fields)carte) nécessaires pour analyser les informations qui seront envoyées à partir de consoles salles Microsoft Teams. Cela inclut la compréhension du schéma JSON documenté dans [Comprendre les entrées du journal.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Développez une vue De gestion des salles Microsoft Teams dans l’analyse des journaux. Vous pouvez soit [créer un tableau de bord Salles Microsoft Teams](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) en utilisant la méthode d’importation, soit créer un tableau de bord [Salles Microsoft Teams manuellement.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Conditions individuelles requises pour la console des salles Microsoft Teams

Chaque console Salle Microsoft Teams est une application qui s’exécute sur un appareil Surface Pro en mode kiosk (normalement, elle est configurée pour être la seule application qui peut s’exécuter sur l’appareil). Comme pour toute application Windows, l’application Salles Microsoft Teams écrit des événements tels que les problèmes de démarrage et de matériel dans le journal des événements Windows. L’ajout d’un agent de moniteur Microsoft sur votre appareil Salles Microsoft Teams permet de collecter ces événements. (Pour plus [d’informations, voir Connecter](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) des ordinateurs Windows au service d’analyse journal dans Azure.)
  
## <a name="ongoing-management"></a>Gestion continue

Lorsque vous utilisez un moniteur Azure pour gérer vos appareils Microsoft Teams Rooms, vous devez comprendre les informations contenues dans les journaux des événements qu’azure Monitor utilise. Pour [plus d’informations sur](azure-monitor-manage.md#understand-the-log-entries) ces messages d’état de santé, voir Comprendre les entrées du journal.
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par les salles Microsoft Teams et comment les résoudre (voir la section intitulée Comprendre les entrées [du journal)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Voir aussi

[Déployer la gestion des salles Microsoft Teams avec Azure Monitor](azure-monitor-deploy.md)
  
[Gérer les appareils salles Microsoft Teams avec Azure Monitor](azure-monitor-manage.md)