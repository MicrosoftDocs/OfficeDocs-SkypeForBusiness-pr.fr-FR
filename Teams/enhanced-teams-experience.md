---
title: Microsoft Teams Premium - Vue d’ensemble pour les administrateurs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: ''
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
description: Découvrez Microsoft Teams Premium pour les administrateurs et les professionnels de l’informatique.
ms.openlocfilehash: f38afe581c96cfe64bd5fd305c3d5f7f09b7c83e
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69308015"
---
# <a name="microsoft-teams-premium---overview-for-administrators"></a>Microsoft Teams Premium - Vue d’ensemble pour les administrateurs

![Icône d’informations](media/info.png) **La plupart des fonctionnalités décrites dans cet article nécessitent Teams Premium, qui est une préversion.** Quelques fonctionnalités, par exemple, certaines fonctionnalités de webinaire, sont également disponibles avec d’autres licences. Pour plus d’informations sur la disponibilité des fonctionnalités et les licences, consultez [Licences Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md).

Cet article est destiné aux professionnels de l’informatique et aux administrateurs qui déploieront et configureront les fonctionnalités Teams Premium. L’article fournit une brève description des fonctionnalités, avec des liens vers une documentation plus détaillée.

Teams Premium est une licence de module complémentaire qui fournit les améliorations suivantes à Teams :  

-   Expériences de réunion améliorées pour vos utilisateurs finaux
-   Sécurité et protection renforcées pour les réunions 
-   Prise en charge améliorée de l’administration et de la télémétrie


> [!IMPORTANT]
> Étant donné que Teams Premium est une préversion publique, en disponibilité générale, certaines fonctionnalités actuellement disponibles avec Teams le seront uniquement avec une licence Teams Premium. 

Les sections suivantes décrivent les améliorations de Teams Premium pour :

- [Réunions protégées](#protected-meetings)
- [Réunions personnalisées](#custom-meetings)
- [Événements Premium](#premium-events)
- [Rendez-vous virtuels](#advanced-virtual-appointments)

> [!Note]
>Nous continuerons à mettre à jour cet article. Revenez souvent pour obtenir des liens vers un nouveau contenu.

## <a name="protected-meetings"></a>Réunions protégées

Teams Premium offre des moyens supplémentaires de protéger les réunions avec les fonctionnalités clés suivantes : 

- **Étiquettes de confidentialité : fonctionnalités étendues** pour les étiquettes de confidentialité afin de contrôler les paramètres de réunion normalement contrôlés par l’organisateur de la réunion. Ces fonctionnalités incluent de nouveaux paramètres pour contrôler les fonctions de salle d’attente, de conversation, de copie de conversation, de présentation et d’enregistrement.

- **Filigrane** : appliqué via une étiquette de confidentialité. Les filigranes affichent l’adresse e-mail d’un participant à la réunion, ce qui est utile pour protéger les informations confidentielles partagées dans les réunions. 

- **Chiffrement de bout en bout** : appliqué via une étiquette de confidentialité. Le chiffrement de bout en bout offre une sécurité accrue pour les réunions qui nécessitent un niveau de protection plus élevé.




| Fonctionnalité/tâche  | Documentation pour les administrateurs |
| -------------------- | ----------- | 
| Étiquettes de confidentialité | [Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md) | 
| Filigranes | [Exiger un filigrane pour les réunions (article)](watermark-meeting-content-video.md) |
| Chiffrement de bout en bout (E2EE) | [Chiffrement pour les réunions sensibles](end-to-end-encrypted-meetings.md) | 
| Modèles, étiquettes et stratégies | [Modèles, étiquettes de confidentialité et stratégies](meeting-templates-sensitivity-labels-policies.md)
| Restreindre les personnes autorisées à enregistrer | [Gérer les enregistrements pour les réunions sensibles](manage-meeting-recording-options.md) | 


## <a name="custom-meetings"></a>Réunions personnalisées

Teams Premium fournit les fonctionnalités supplémentaires suivantes pour la personnalisation des réunions :

- **Modèles de réunion** : utilisés pour contrôler les paramètres de réunion que l’organisateur de la réunion contrôle normalement. Avec les modèles, vous pouvez créer des expériences de réunion cohérentes dans votre organisation et vous aider à appliquer les exigences de conformité et les règles métier.

- **Thèmes de réunion** : permet à votre organisation d’étendre ses identités visuelles à l’ensemble de l’expérience de réunion. Vous pouvez configurer et créer des thèmes de réunion pour une variété d’unités commerciales et de services au sein d’un seul locataire.

- **Arrière-plans de réunion personnalisés** : vous pouvez créer et définir des arrière-plans de réunion personnalisés qui sont ensuite disponibles pour vos utilisateurs finaux. 

- **Scènes personnalisées en mode ensemble** : application Teams qui permet aux développeurs de votre organisation de définir et de personnaliser des scènes vidéo pour les réunions.  

| Fonctionnalité/tâche | Documentation pour les administrateurs |
| -------------------- | ----------- | 
| Modèles de réunion | - [Aperçu](custom-meeting-templates-overview.md)<br>- [Créer un modèle de réunion personnalisé](create-custom-meeting-template.md)|
| Thèmes de réunion | [Thèmes pour les réunions Teams](meeting-themes.md) | 
| Arrière-plans de réunion personnalisés | [Arrière-plans de réunion](custom-meeting-backgrounds.md)| 
| Scènes personnalisées en mode ensemble | [Contenu pour vous et vos développeurs](/microsoftteams/platform/apps-in-teams-meetings/teams-together-mode)| 





## <a name="premium-events"></a>Événements Premium

Teams Premium fournit une expérience de webinaire avancée pour vos utilisateurs avec la nouvelle stratégie d’événements Teams. Tout en continuant à prendre en charge l’inscription et le suivi, la nouvelle stratégie fournira également des fonctionnalités pour les organisateurs de réunions et les organisateurs, telles que :

- **Question personnalisée sur les conditions générales** : à présenter aux participants.
- **Biographie du présentateur** : pour inclure des informations sur les présentateurs.
- **Bannière, logo et couleur prédéfinie** : pour présenter une expérience de webinaire visuelle personnalisée.
- **Fonctionnalités d’inscription avancées** : notamment l’approbation manuelle, la liste d’attente, la date d’inscription et la limite d’heure.
- **Vue d’ensemble et gestion de l’inscription** : pour chaque événement, un résumé de l’état d’inscription avec des listes de participants dans différents états d’inscription, en fonction des fonctionnalités d’inscription activées.


| Fonctionnalité/tâche | Documentation pour les administrateurs | 
| -------------------- | ----------- | 
| Comprendre les réunions, les webinaires et les événements en direct | [Démarrage rapide](quick-start-meetings-live-events.md) | 
| Configurer des webinaires | [Configurer des webinaires](set-up-webinars.md) | 
| Stratégie de réunion pour les webinaires | [Stratégies de réunion](meeting-policies-in-teams-general.md)




## <a name="advanced-virtual-appointments"></a>Rendez-vous virtuels avancé

Avec n’importe quelle licence Microsoft 365, vos utilisateurs finaux peuvent utiliser des fonctionnalités de Rendez-vous virtuels de base pour planifier et participer à des réunions d’entreprise à client. Par exemple, les utilisateurs peuvent planifier des rendez-vous dans le calendrier Bookings et les participants externes peuvent y participer via un navigateur sans avoir à télécharger Teams. 

Teams Premium fournit des fonctionnalités avancées de rendez-vous virtuel, telles que :

- Notifications PAR SMS
- Salle d’attente personnalisée
- Une file d’attente de rendez-vous planifiés et à la demande
- Analyse

| Fonctionnalité/tâche  | Documentation pour les administrateurs | 
| -------------------- | ----------- | 
| Notifications PAR SMS  | [Notifications par SMS](bookings-app-admin.md#sms-text-notifications) | 
| Rapports | [Rendez-vous virtuels rapport d’utilisation](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)<br>[Rapport d’activité Rendez-vous virtuels avancé](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) | 



## <a name="additional-resources"></a>Ressources supplémentaires

Vous trouverez des ressources supplémentaires ici :

- [Microsoft site du produit Teams Premium](https://www.microsoft.com/microsoft-teams/premium)
- [blog Microsoft Teams Premium](https://www.microsoft.com/microsoft-365/blog/2022/10/12/introducing-microsoft-teams-premium-the-better-way-to-meet/)



