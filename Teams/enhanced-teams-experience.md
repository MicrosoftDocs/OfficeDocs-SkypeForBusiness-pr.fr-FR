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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
description: Découvrez les Microsoft Teams Premium pour les administrateurs et les professionnels de l’informatique.
ms.openlocfilehash: 2abcdd1c9f9df0101bbf7d0e22720c71375728d0
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800279"
---
# <a name="microsoft-teams-premium---overview-for-administrators"></a>Microsoft Teams Premium - Vue d’ensemble pour les administrateurs

![Icône d’informations](media/info.png) **La plupart des fonctionnalités décrites dans cet article nécessitent Teams Premium, qui est une préversion.** Quelques fonctionnalités, par exemple, certaines fonctionnalités de webinaire, sont également disponibles avec d’autres licences. Pour plus d’informations sur la disponibilité des fonctionnalités et les licences, consultez [licences Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md).

Cet article s’adresse aux professionnels de l’informatique et aux administrateurs qui déploieront et configureront Teams Premium fonctionnalités. L’article fournit une brève description des fonctionnalités, avec des liens vers une documentation plus détaillée.

Teams Premium est une licence de module complémentaire qui apporte les améliorations suivantes à Teams :  

-   Expériences de réunion améliorées pour vos utilisateurs finaux
-   Sécurité et protection renforcées pour les réunions 
-   Prise en charge améliorée de l’administration et de la télémétrie


> [!IMPORTANT]
> Étant donné que Teams Premium est une préversion publique, en disponibilité générale, certaines fonctionnalités actuellement disponibles avec Teams le seront uniquement avec une licence Teams Premium. 

Les sections suivantes décrivent les améliorations Teams Premium pour :

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


| Fonctionnalité/tâche  | Documentation pour les administrateurs | Documentation pour vos utilisateurs finaux
| -------------------- | ----------- | ------------ |
| Étiquettes de confidentialité | [Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md) | |
| Filigranes | [Exiger un filigrane pour les réunions](watermark-meeting-content-video.md) | [Filigranes pour les réunions](https://support.microsoft.com/office/watermark-for-teams-meetings-a9166432-f429-4a19-9a72-c9e8fdf4f589)|
| Chiffrement de bout en bout (E2EE) | [Chiffrement pour les réunions sensibles](end-to-end-encrypted-meetings.md) | [Utiliser le chiffrement](https://support.microsoft.com/office/use-end-to-end-encryption-for-teams-meetings-a8326d15-d187-49c4-ac99-14c17dbd617c)  |
| Modèles, étiquettes et stratégies | [Modèles, étiquettes de confidentialité et stratégies](meeting-templates-sensitivity-labels-policies.md)  | [Utiliser des modèles personnalisés](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f) |
| Restreindre les personnes autorisées à enregistrer | [Gérer les enregistrements pour les réunions sensibles](manage-meeting-recording-options.md) | [Enregistrer une réunion](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24?storagetype=stage#bkmk_whocanstartorstoparecording) |


## <a name="custom-meetings"></a>Réunions personnalisées

Teams Premium fournit les fonctionnalités supplémentaires suivantes pour la personnalisation des réunions :

- **Modèles de réunion** : utilisés pour contrôler les paramètres de réunion que l’organisateur de la réunion contrôle normalement. Avec les modèles, vous pouvez créer des expériences de réunion cohérentes dans votre organisation et vous aider à appliquer les exigences de conformité et les règles métier.

- **Thèmes de réunion** : permet à votre organisation d’étendre ses identités visuelles à l’ensemble de l’expérience de réunion. Vous pouvez configurer et créer des thèmes de réunion pour une variété d’unités commerciales et de services au sein d’un seul locataire.

- **Arrière-plans de réunion personnalisés pour les organisations** : vous pouvez créer et définir des arrière-plans de réunion personnalisés qui sont ensuite disponibles pour vos utilisateurs finaux avec une licence Teams Premium.

- **Scènes personnalisées en mode ensemble pour les organisations** : vous pouvez créer, personnaliser ou accepter des scènes personnalisées en mode ensemble pour les réunions qui sont ensuite disponibles pour vos utilisateurs finaux avec une licence Teams Premium.


| Fonctionnalité/tâche | Documentation pour les administrateurs | Documentation pour vos utilisateurs finaux
| -------------------- | ----------- | ------------ |
| Modèles de réunion | - [Aperçu](custom-meeting-templates-overview.md)<br>- [Créer un modèle de réunion personnalisé](create-custom-meeting-template.md)| [Utiliser des modèles personnalisés](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f)
| Thèmes de réunion | [Thèmes pour les réunions Teams](meeting-themes.md) | [Utiliser des thèmes de réunion](https://support.microsoft.com/office/use-meeting-themes-for-teams-meetings-fbfd826d-1112-4790-918a-5a82cac8250e) |
| Arrière-plans de réunion personnalisés pour les organisations | [Arrière-plans de réunion](custom-meeting-backgrounds.md)| |
| Scènes personnalisées en mode ensemble pour les organisations | [Contenu pour vous et vos développeurs](/microsoftteams/platform/apps-in-teams-meetings/teams-together-mode)| |





## <a name="premium-events"></a>Événements Premium

Teams Premium fournit une expérience de webinaire avancée pour vos utilisateurs avec la nouvelle stratégie d’événements Teams. Tout en continuant à prendre en charge l’inscription et le suivi, la nouvelle stratégie fournira également des fonctionnalités pour les organisateurs de réunions et les organisateurs, telles que :

- **Question personnalisée sur les conditions générales** : à présenter aux participants.
- **Biographie du présentateur** : pour inclure des informations sur les présentateurs.
- **Bannière, logo et couleur prédéfinie** : pour présenter une expérience de webinaire visuelle personnalisée.
- **Fonctionnalités d’inscription avancées** : notamment l’approbation manuelle, la liste d’attente, la date d’inscription et la limite d’heure.
- **Vue d’ensemble et gestion de l’inscription** : pour chaque événement, un résumé de l’état d’inscription avec des listes de participants dans différents états d’inscription, en fonction des fonctionnalités d’inscription activées.


| Fonctionnalité/tâche | Documentation pour les administrateurs | Documentation pour vos utilisateurs finaux
| -------------------- | ----------- | ----------- |
| Comprendre les réunions, les webinaires et les événements en direct | [Démarrage rapide](quick-start-meetings-live-events.md) | |
| Configurer des webinaires | [Configurer des webinaires](set-up-webinars.md) | - [Gérer l’inscription au webinaire](https://support.microsoft.com/office/manage-webinar-registration-923f382a-0cca-433a-b38d-7461971192d1) <br> - [Gérer ce que voient les participants](https://support.microsoft.com/office/manage-what-attendees-see-in-teams-meetings-19bfd690-8122-49f4-bc04-c2c5f69b4e16)|
| Stratégie de réunion pour les webinaires | [Stratégies de réunion](meeting-policies-in-teams-general.md) | |




## <a name="advanced-virtual-appointments"></a>Rendez-vous virtuels avancé

Avec n’importe quelle licence Microsoft 365, vos utilisateurs finaux peuvent utiliser des fonctionnalités de Rendez-vous virtuels de base pour planifier et participer à des réunions entre les entreprises et les clients. Par exemple, les utilisateurs peuvent planifier des rendez-vous dans le calendrier Bookings et les participants externes peuvent y participer via un navigateur sans avoir à télécharger Teams. 

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

- [Microsoft Teams Premium site du produit](https://www.microsoft.com/microsoft-teams/premium)
- [blog Microsoft Teams Premium](https://www.microsoft.com/microsoft-365/blog/2022/10/12/introducing-microsoft-teams-premium-the-better-way-to-meet/)



