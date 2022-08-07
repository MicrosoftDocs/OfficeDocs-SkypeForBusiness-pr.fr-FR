---
title: Planifier la surveillance Salles Microsoft Teams avec Azure Monitor
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
- Teams_ITAdmin_Rooms
description: Cet article décrit les considérations relatives à la planification de l’utilisation d’Azure Monitor pour surveiller les Salles Microsoft Teams dans votre implémentation Skype Entreprise ou Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac3ac3af4e4f162238af0e9bf38c45569302fdfb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269569"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planifier la surveillance Salles Microsoft Teams avec Azure Monitor
 
 Cet article décrit les considérations relatives à la planification de l’utilisation d’Azure Monitor pour administrer Salles Microsoft Teams appareils dans votre implémentation Microsoft Teams ou Skype Entreprise.

> [!NOTE]
> Vous pouvez également [configurer la surveillance de l’intégrité des salles Teams](../alerts/device-health-status.md) à l’aide du Centre d’administration Teams.

[Azure Monitor](/azure/azure-monitor/overview) est une collection de services de supervision qui ont été conçus dans le cloud dès le début. Au lieu de déployer et de gérer des ressources locales, les composants Azure Monitor sont entièrement hébergés dans Azure. La configuration est minimale et vous pouvez être opérationnel en quelques minutes. Avec certains travaux de personnalisation, il peut faciliter la surveillance des Salles Microsoft Teams en fournissant des notifications de l’intégrité du système ou des pannes pour des systèmes individuels de salle, et il peut monter en puissance jusqu’à gérer des milliers de Salles Microsoft Teams.
  
Cet article fournit une discussion sur les exigences, la conception/l’architecture et les meilleures pratiques d’implémentation nécessaires pour implémenter la surveillance basée sur Azure Monitor de Salles Microsoft Teams. Il fournit également des liens vers des articles détaillés sur l’implémentation d’Azure Monitor pour Salles Microsoft Teams et des informations de référence critiques pour la surveillance continue des salles Salles Microsoft Teams.
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de gestion Salles Microsoft Teams à l’aide d’Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application Salles Microsoft Teams écrit des événements dans le journal des événements Windows. Une fois installé, un agent de surveillance Microsoft transmet les informations au service Azure Monitor.
  
Une fois correctement configuré, Log Analytics analyse la charge utile JSON incorporée dans les descriptions d’événements pour décrire le fonctionnement de Salles Microsoft Teams et les erreurs détectées.
  
Un administrateur qui utilise Azure Monitor peut recevoir des notifications de Salles Microsoft Teams qui sont hors connexion ou qui rencontrent des défaillances d’application, de connectivité ou de matériel, ainsi que de savoir si un système doit être redémarré. Chaque état du système étant fréquemment mis à jour, ces notifications sont proches des mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Configuration requise pour Azure Monitor

Vous devez disposer d’un abonnement Azure valide pour qu’Azure Monitor utilise des fonctionnalités Log Analytics. Consultez [Prise en main d’un espace de travail Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) pour créer un abonnement pour votre organisation.
  
Vous devez vous familiariser avec l’utilisation du Concepteur de vues Log Analytics. Pour plus d’informations [, consultez Vues dans Log Analytics](/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Tâches connexes

1. Une fois abonné à Azure Monitor Log Analytics, créez des champs personnalisés (comme décrit dans [Map custom fields](azure-monitor-deploy.md#Custom_fields)) nécessaires pour analyser les informations qui seront envoyées à partir de Salles Microsoft Teams. Cela inclut la compréhension du schéma JSON documenté dans [Comprendre les entrées de journal](azure-monitor-manage.md#understand-the-log-entries).
    
2. Développez une vue de gestion Salles Microsoft Teams dans Log Analytics. Vous pouvez [créer un tableau de bord Salles Microsoft Teams manuellement](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Exigences de Salles Microsoft Teams individuelles

Salles Microsoft Teams est une application s’exécutant sur un appareil de calcul en mode plein écran. Comme avec n’importe quelle application Windows, l’application Salles Microsoft Teams écrit des événements tels que le démarrage et les erreurs matérielles dans le journal des événements Windows. L’ajout d’un agent Microsoft Monitor sur Salles Microsoft Teams permet de collecter ces événements. (Pour plus d’informations, consultez [Connecter des ordinateurs Windows au service Log Analytics dans Azure](/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Gestion continue

Lors de l’utilisation d’Azure Monitor pour surveiller votre Salles Microsoft Teams, vous devez comprendre les informations contenues dans les journaux des événements utilisés par Azure Monitor. Pour plus d’informations sur ces messages d’intégrité, consultez [Comprendre les entrées du journal](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Tâches connexes

- Comprendre les alertes générées par Salles Microsoft Teams et comment les résoudre (voir la section intitulée [Comprendre les entrées de journal](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Voir aussi

[Déployer la gestion Salles Microsoft Teams avec Azure Monitor](azure-monitor-deploy.md)
  
[Gérer les appareils Salles Microsoft Teams avec Azure Monitor](azure-monitor-manage.md)
