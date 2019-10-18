---
title: Planifier la gestion des salles de Microsoft teams avec Azure Monitor
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: Cet article aborde les considérations relatives à la planification de l’utilisation de l’outil de contrôle Azure pour gérer les appareils de salle Microsoft teams dans votre implémentation Skype entreprise ou Teams.
ms.openlocfilehash: e605f3cba8f6e21bb1da4f8301b54922dc8804d5
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569917"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planifier la gestion des salles de Microsoft teams avec Azure Monitor
 
 Cet article aborde les considérations en matière de planification de l’utilisation de l’outil de suivi Azure pour administrer les appareils de salle Microsoft teams dans votre implémentation Microsoft teams ou Skype entreprise.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) est une collection de services de gestion conçus dans le Cloud à partir du début. Au lieu de déployer et de gérer des ressources locales, les composants de moniteur Azure sont entièrement hébergés dans Azure. La configuration est minime et vous pouvez être opérationnel en quelques minutes. Le fonctionnement de certaines tâches de personnalisation a pour but de vous aider à gérer les systèmes de conférences de Microsoft Teams, en fournissant des notifications en temps réel de l’intégrité du système ou des défauts pour les systèmes de salle individuels et peut évoluer vers la gestion des milliers de Microsoft teams Salles de conférence.
  
Cet article présente la configuration requise, la conception et l’architecture ainsi que les meilleures pratiques en matière de mise en œuvre de la gestion d’Azure Monitor des appareils de conférence de Microsoft Teams, ainsi que des liens vers des Articles détaillés sur mise en place de l’analyseur Azure pour les salles Microsoft teams et des informations de référence critiques pour la surveillance en continu des salles de salles de Microsoft Teams. 
  
## <a name="functional-overview"></a>Présentation fonctionnelle

![diagramme de la gestion de salles de Microsoft teams avec Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L’application Microsoft teams sur l’appareil console enregistre les événements dans le journal des événements Windows. Un agent de surveillance Microsoft, une fois installé, transmet les informations au service de suivi Azure. 
  
Lorsque celle-ci est correctement configurée, l’analyse du Journal analyse la charge utile JSON imbriquée dans les descriptions des événements pour décrire le fonctionnement de chaque système de salle Microsoft teams et les erreurs détectées. 
  
Un administrateur qui utilise Azure Monitor peut recevoir des notifications de systèmes de salle Microsoft teams qui sont hors ligne ou qui rencontrent des problèmes liés aux applications, à la connectivité ou au matériel, et savoir si un système doit être redémarré. Chaque statut du système est fréquemment mis à jour, de sorte que ces notifications sont proches des mises à jour en temps réel.
  
## <a name="azure-monitor-requirements"></a>Configuration requise pour le moniteur Azure

Pour pouvoir utiliser la fonctionnalité d’analyse du journal, vous devez disposer d’un abonnement Azure valide pour Azure Monitor. Voir [commencer à utiliser un espace de travail d’analyse du journal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) pour créer un abonnement pour votre organisation.
  
Vous devez vous familiariser avec l’utilisation du concepteur de vues d’analyse du journal. Pour plus d’informations, voir [vues dans l’analyse du journal](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Tâches connexes

1. Lorsque vous souscrivez un abonnement à l’analyse du journal d’Azure Monitor, vous pouvez créer des champs personnalisés (comme décrit dans la section [mappage des champs personnalisés](azure-monitor-deploy.md#Custom_fields)) nécessaires à l’analyse des informations qui seront envoyées à partir de Microsoft teams salles. Cela inclut la compréhension du schéma JSON documenté dans [les entrées du journal](azure-monitor-manage.md#understand-the-log-entries).
    
2. Développez une vue de gestion des salles de Microsoft teams dans analyse du journal. Vous pouvez [créer un tableau de bord de Microsoft teams à l’aide de la méthode d’importation](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) ou [créer manuellement un tableau de bord de salles de Microsoft teams](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Configuration requise pour la console individuelle de Microsoft teams

Chaque console de salle Microsoft teams est une application exécutée sur un appareil surface Pro en mode plein écran (il est généralement configuré pour être la seule application pouvant s’exécuter sur l’appareil). Comme pour toutes les applications Windows, l’application Microsoft teams salles enregistre des événements tels que les erreurs de démarrage et de matériel dans le journal des événements Windows. L’ajout d’un agent Microsoft Monitor sur votre appareil de salle Microsoft teams permet de collecter ces événements. (Pour plus d’informations, voir [connecter des ordinateurs Windows au service d’analyse du journal dans Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Gestion continue

Lors de l’utilisation de l’outil Moniteur Azure pour gérer vos appareils de salle Microsoft Teams, vous devez comprendre les informations contenues dans les journaux d’événements utilisés par le moniteur Azure. Pour plus d’informations sur ces messages d’État, voir [comprendre les entrées du journal](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Tâches connexes

- Comprenez les alertes générées par les salles de Microsoft teams et comment les résoudre (voir la section [Présentation des entrées du journal](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Voir aussi

[Déploiement de la gestion de salles de Microsoft teams avec Azure Monitor](azure-monitor-deploy.md)
  
[Gérer les appareils de salle Microsoft teams avec Azure Monitor](azure-monitor-manage.md)