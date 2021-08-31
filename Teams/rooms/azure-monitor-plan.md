---
title: Planifier la Salles Microsoft Teams gestion des données à l’aide d’Azure Monitor
ms.author: dstrome
author: dstrome
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
description: Cet article décrit la planification de l’utilisation du moniteur Azure pour administrer Salles Microsoft Teams appareils dans votre entreprise ou Skype Entreprise en Teams’implémentation.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cdd5d95d6f5f94bbe73da63b6d0b0f8e8e070cf9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726023"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planifier la Salles Microsoft Teams gestion des données à l’aide d’Azure Monitor
 
 Cet article décrit la planification de l’utilisation du moniteur Azure pour administrer Salles Microsoft Teams appareils dans Microsoft Teams ou Skype Entreprise implémentation.
  
[Azure Monitor](/azure/azure-monitor/overview) est un ensemble de services de gestion conçus dans le cloud depuis le début. Plutôt que de déployer et de gérer des ressources sur site, les composants du moniteur Azure sont entièrement hébergés dans Azure. La configuration est minimale et vous pouvez être opérationnel littéralement en quelques minutes. Grâce à certaines opérations de personnalisation, elle peut vous aider à gérer les systèmes de conférence Salles Microsoft Teams en fournissant des notifications en temps réel concernant l’état ou les défaillances du système pour les systèmes de salle individuels, et peut potentiellement augmenter jusqu’à la gestion de milliers de salles de conférence Salles Microsoft Teams.
  
Cet article propose une discussion sur les meilleures pratiques requises, de conception/architecture et de mise en œuvre nécessaires pour implémenter la gestion azure monitor basée sur les périphériques de conférence Salles Microsoft Teams et fournit des liens vers des articles détaillés sur l’implémentation d’Azure Monitor pour Salles Microsoft Teams et des informations de référence critiques pour la surveillance continue des salles de Salles Microsoft Teams. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de la gestion Salles Microsoft Teams gestion des données à l’aide d’Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’Salles Microsoft Teams sur l’appareil de la console écrit les événements dans Windows journal des événements. Une fois l’installation installée, un agent de surveillance Microsoft transmet les informations au service Azure Monitor. 
  
Une fois configurée correctement, l’analyse journal analyse la charge utile JSON incorporée dans les descriptions des événements pour décrire le fonctionnement de chaque système Salles Microsoft Teams et les pannes détectées. 
  
Un administrateur qui utilise un moniteur Azure peut recevoir des notifications concernant les systèmes Salles Microsoft Teams hors connexion ou qui rencontrent des problèmes d’application, de connectivité ou de matériel, ainsi que pour savoir si un système doit être redémarré. Chaque état du système est fréquemment mis à jour, de sorte que ces notifications sont proches des mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor requirements

Vous devez avoir un abonnement Azure valide pour qu’Azure Monitor utilise la fonctionnalité Analyse de journal. Pour créer un abonnement pour votre organisation, voir Mise en route [d’un](/azure/azure-monitor/learn/quick-create-workspace) espace de travail Analyse journal.
  
Familiarisez-vous si nécessaire pour utiliser le Concepteur d’affichage d’analyse de journaux. Pour [plus d’informations, voir](/azure/azure-monitor/platform/view-designer) Affichages dans l’analyse des journaux.
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à Azure Monitor Log Analytics, créez des champs personnalisés (comme décrit dans champs personnalisés [de](azure-monitor-deploy.md#Custom_fields)carte) nécessaires pour analyser les informations qui seront envoyées à partir de Salles Microsoft Teams consoles. Cela inclut la compréhension du schéma JSON documenté dans [Comprendre les entrées du journal.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Développez un affichage Salles Microsoft Teams gestion des données dans l’analyse des journaux. Vous pouvez [créer un tableau de Salles Microsoft Teams tableau de bord manuellement.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Conditions requises Salles Microsoft Teams console individuelle

Chaque console Salles Microsoft Teams est une application qui s’exécute sur un appareil Surface Pro en mode borne (normalement, elle est configurée pour être la seule qui peut s’exécuter sur l’appareil). Comme pour toute application Windows, l’application Salles Microsoft Teams écrit des événements tels que les erreurs de démarrage et de matériel dans le Windows événement. L’ajout d’un agent microsoft monitor sur Salles Microsoft Teams appareil permet de collecter ces événements. (Pour [plus Connecter Windows, consultez](/azure/azure-monitor/platform/agent-windows) le service Analyse journal dans Azure.)
  
## <a name="ongoing-management"></a>Gestion continue

Lors de l’utilisation du moniteur Azure pour gérer Salles Microsoft Teams appareils mobiles, vous devez comprendre les informations contenues dans les journaux des événements qu’azure Monitor utilise. Pour [plus d’informations sur](azure-monitor-manage.md#understand-the-log-entries) ces messages d’état de santé, voir Comprendre les entrées du journal.
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par Salles Microsoft Teams comment les résoudre (voir la section intitulée Comprendre les entrées [du journal)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Voir aussi

[Déployer la Salles Microsoft Teams gestion des ordinateurs avec Azure Monitor](azure-monitor-deploy.md)
  
[Gérer Salles Microsoft Teams appareils avec le moniteur Azure](azure-monitor-manage.md)
