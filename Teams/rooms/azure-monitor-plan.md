---
title: Planifier l Salles Microsoft Teams de surveillance à l’aide d’Azure Monitor
ms.author: czawideh
author: cazawideh
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: Cet article décrit la planification de l’utilisation d’Azure Monitor pour surveiller les Salles Microsoft Teams dans le Skype Entreprise de votre Teams’implémentation.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 510f249ea4aef78b898294db0a2c3fbeef8fc283
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504121"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planifier l Salles Microsoft Teams de surveillance à l’aide d’Azure Monitor
 
 Cet article décrit la planification de l’utilisation du moniteur Azure pour administrer Salles Microsoft Teams appareils dans votre entreprise ou Microsoft Teams votre Skype Entreprise' implémentation.

> [!NOTE]
> Vous pouvez également configurer [la surveillance de l’état d’salles Teams’aide](../alerts/device-health-status.md) Teams centre d’administration.

[Azure Monitor](/azure/azure-monitor/overview) est un ensemble de services de surveillance conçus dans le cloud depuis le début. Plutôt que de déployer et de gérer des ressources sur site, les composants du moniteur Azure sont entièrement hébergés dans Azure. La configuration est minimale et vous pouvez être opérationnel en quelques minutes. Grâce à certaines opérations de personnalisation, elle peut vous aider à surveiller les Salles Microsoft Teams en fournissant des notifications sur l’état ou les défaillances du système pour les systèmes de salle individuels, et sur une gestion de milliers d’Salles Microsoft Teams.
  
Cet article fournit une discussion sur les meilleures pratiques requises, de conception/architecture et de mise en œuvre nécessaires pour implémenter la surveillance azure monitor de Salles Microsoft Teams. Il fournit également des liens vers des articles détaillés sur l’implémentation d’Azure Monitor pour les Salles Microsoft Teams informations de référence critiques pour la surveillance continue des salles Salles Microsoft Teams'
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de la gestion Salles Microsoft Teams gestion des données à l’aide d’Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’Salles Microsoft Teams l’application écrit les événements dans Windows journal des événements. Un agent de surveillance Microsoft, une fois installé, transmet les informations au service Azure Monitor.
  
Une fois configurée correctement, l’analyse journal analyse la charge utile JSON incorporée dans les descriptions des événements pour décrire le fonctionnement d’Salles Microsoft Teams et les erreurs détectées.
  
Un administrateur qui utilise le moniteur Azure peut recevoir des notifications concernant des Salles Microsoft Teams qui sont hors connexion ou qui rencontrent des problèmes d’application, de connectivité ou de matériel, ainsi que de savoir si un système doit être redémarré. Chaque état du système est fréquemment mis à jour, de sorte que ces notifications sont proches des mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor requirements

Vous devez avoir un abonnement Azure valide pour qu’Azure Monitor utilise les fonctionnalités d’analyse de journal. Pour [créer un abonnement pour](/azure/azure-monitor/learn/quick-create-workspace) votre organisation, voir Mise en route d’un espace de travail Analyse journal.
  
Familiarisez-vous avec l’utilisation du Concepteur d’affichages log Analytics. Pour [plus d’informations, voir](/azure/azure-monitor/platform/view-designer) Affichages dans l’analyse des journaux.
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à Azure Monitor Log Analytics, créez des champs personnalisés (comme décrit dans Champs personnalisés [de carte](azure-monitor-deploy.md#Custom_fields)) nécessaires pour analyser les informations qui seront envoyées à partir de Salles Microsoft Teams. Cela inclut la compréhension du schéma JSON documenté dans [Comprendre les entrées du journal](azure-monitor-manage.md#understand-the-log-entries).
    
2. Développez un affichage Salles Microsoft Teams gestion des données dans l’analyse des journaux. Vous pouvez [créer un tableau de Salles Microsoft Teams de bord manuellement](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Exigences individuelles Salles Microsoft Teams client

Salles Microsoft Teams est une application qui s’exécute sur un ordinateur en mode borne. Comme pour toute application Windows, l’application Salles Microsoft Teams écrit des événements tels que les erreurs de démarrage et de matériel dans le Windows événement. L’ajout d’un agent de Salles Microsoft Teams Microsoft permet de collecter ces événements. (Pour [plus Connecter Windows,consultez le service Analyse journal dans Azure](/azure/azure-monitor/platform/agent-windows).)
  
## <a name="ongoing-management"></a>Gestion continue

Lorsque vous utilisez le moniteur Azure pour surveiller votre Salles Microsoft Teams, vous devez comprendre les informations contenues dans les journaux des événements qu’utilise le moniteur Azure. Pour [plus d’informations sur](azure-monitor-manage.md#understand-the-log-entries) ces messages d’état de santé, voir Comprendre les entrées du journal.
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par Salles Microsoft Teams comment les résoudre (voir la section intitulée Comprendre les entrées [du journal](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Voir aussi

[Déployer la Salles Microsoft Teams gestion des données à l’Salles Microsoft Teams Azure Monitor](azure-monitor-deploy.md)
  
[Gérer Salles Microsoft Teams appareils avec un moniteur Azure](azure-monitor-manage.md)
