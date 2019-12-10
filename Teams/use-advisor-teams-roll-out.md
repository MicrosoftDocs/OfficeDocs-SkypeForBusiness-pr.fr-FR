---
title: Utiliser Advisor for Teams (préversion) pour faciliter le déploiement de Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Utilisez Advisor for Teams (préversion) pour faciliter la planification et l’exécution de votre déploiement de Microsoft Teams.
ms.openlocfilehash: 63a3ae01dbe47323fd9227e65fa8c38a2d725ddf
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909470"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Utiliser Advisor for Teams pour faciliter le déploiement de Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor for Teams (préversion) vous guide tout au long du processus de déploiement de Microsoft Teams. Il évalue l’environnement de votre client Office 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams. Advisor for Teams crée ensuite une équipe Déploiement (dans Teams) avec des canaux pour chaque charge de travail à déployer. Chaque charge de travail de l’équipe Déploiement s’accompagne d’un plan complet du Planificateur qui comprend toutes les tâches de déploiement pour chaque charge de travail.  Ce plan du Planificateur vous permet d’affecter des tâches aux différentes personnes responsables de chaque phase du déploiement, à savoir le responsable du projet, les administrateurs de Teams et Office 365, les personnes en charge du support technique et votre équipe d’adoption et de préparation des utilisateurs. Chaque tâche de déploiement contient toutes les ressources et tous les conseils dont vous avez besoin pour la mener à bien.

Advisor for Teams fait partie intégrante du [Centre d’administration Teams](https://admin.teams.microsoft.com). Pour commencer à utiliser Advisor for Teams, cliquez sur le bouton **Start** (Démarrer) dans le widget **Deploying Teams workload** (Déploiement de charge de travail Teams) situé dans le tableau de bord. Vous pouvez aussi accéder à **Planning** (Planification) > **Advisor** (Conseiller).

> [!IMPORTANT]
> Advisor for Teams n’est pas disponible pour Microsoft 365 Government – Déploiements GCC High ou DoD.

Consultez la rubrique sur Advisor for Teams dans cette vidéo d’[introduction sur le déploiement et la configuration de Teams](https://youtu.be/o2mlsUubIO4?t=44) (Advisor for Teams est traité à 0:50-3:15 minutes).

## <a name="using-advisor-for-teams-preview"></a>Utilisation d’Advisor for Teams (préversion)

Vous n’avez pas besoin d’être administrateur de Teams pour utiliser Advisor for Teams. Toutes les personnes de votre organisation peuvent l’utiliser. Nous avons créé des autorisations spéciales pour permettre aux utilisateurs non administrateurs d’accéder à Advisor for Teams, même si ce conseiller figure dans le Centre d’administration Teams. En revanche, vous DEVEZ être administrateur de Teams, administrateur du service Teams ou administrateur général pour pouvoir ouvrir les évaluations de la préparation du client.

À la première utilisation de Advisor for Teams, une équipe déploiement sera créée automatiquement dans Teams. Des canaux sont ajoutés pour chaque charge de travail que vous voulez déployer. 


## <a name="available-advisor-for-teams-plans"></a>Plans Advisor for Teams disponibles

Même si Advisor for Teams est disponible en préversion, nous proposons ces deux plans :

1. Conversations, équipes, canaux et applications
    - Évaluation du client
    - Plan du Planificateur, y compris les tâches d’adoption
    - Enquête utilisateur Forms
1. Réunions et conférences
    - Évaluation du client
    - Plan du Planificateur, y compris les tâches d’adoption
    - Enquête utilisateur Forms

Nous vous recommandons de commencer par le plan Conversations, équipes, canaux et applications. Une fois que vous avez déployé cette charge de travail, revenez à Advisor et cliquez sur **Add channel** (Ajouter un canal) pour enchaîner sur la charge de travail suivante. 

## <a name="tenant-assessment"></a>Évaluation du client
Chaque plan comprend une évaluation de la préparation du client dont vous pouvez vous servir pour identifier les déficiences de votre environnement et y remédier avant de déployer Teams. Voici ce qui est vérifié pendant l’évaluation :

### <a name="chat-teams-channels-and-apps"></a>Conversations, équipes, canaux et applications


|Évaluation  |Ce qu’elle vous indique  |
|---------|---------|
|Licences Teams     |Si vous disposez d’un abonnement actif avec des licences Teams disponibles. |
|Licences Exchange     |Si vous disposez d’un abonnement actif avec des licences Exchange Online disponibles. Même si Exchange n’est pas nécessaire pour les fonctionnalités Teams de base, l’intégration avec Exchange offre une expérience Teams optimale.         |
|Licences SharePoint Online     | Si vous disposez d’un abonnement actif avec des licences SharePoint Online disponibles. Vous avez besoin d’une licence SharePoint Online par utilisateur pour le stockage de fichiers, la collaboration entre les canaux et les conversations. 
|Accès invité activé     |Si l’accès invité est activé dans Teams. Les paramètres d’accès invité ne sont pas examinés pour Azure Active Directory.   |
|Domaine personnalisé configuré     |Si un domaine autre que @onmicrosoft.com est configuré pour votre client.  |
|Standard de nommage de groupe Office 365 configuré     | Si les standards de nommage ont été configurés pour les groupes Office 365.        |
|Expiration de groupe Office 365 configurée     |  Si une stratégie d’expiration de groupe a été définie pour les groupes Office 365. Si ce n’est pas le cas, la valeur est définie sur jamais.        |
|Accès externe configuré     |Si l’accès externe est activé pour vous permettre de communiquer avec des organisations externes dans Teams.          |

### <a name="meetings-and-conferencing"></a>Réunions et conférences


|Évaluation  |Ce qu’elle vous indique  |
|---------|---------|
|Licences Teams     |Si vous disposez d’un abonnement actif avec des licences Teams disponibles. |
|Licences Exchange     |Si vous disposez d’un abonnement actif avec des licences Exchange Online disponibles. Même si Exchange n’est pas nécessaire pour les fonctionnalités Teams de base, l’intégration avec Exchange offre une expérience Teams optimale. |
|Licences d’audioconférence    |Si vous disposez d’un abonnement actif avec des licences d’audioconférence. |
|Licences Stream     |Si vous avez un abonnement actif avec des licences Stream, qui peuvent servir en cas de besoin de l’enregistrement de réunion. |
|Accès invité     |Si l’accès invité est activé dans Teams. Les paramètres d’accès invité ne sont pas examinés pour Azure Active Directory.|
|Domaine personnalisé     |Si un domaine autre que @onmicrosoft.com est configuré pour votre client.  |
|Accès externe     |Si l’accès externe est activé pour vous permettre de communiquer avec des organisations externes dans Teams. |


### <a name="advisor-bot"></a>Bot Advisor
Une fois l’équipe déploiement créée, le bot Advisor affiche le message suivant.

>**Bienvenue dans votre équipe déploiement pour Microsoft Teams !**
>  
>La finalité de cette équipe est de vous accompagner tout au long du déploiement de Teams dans votre organisation en mettant à votre disposition toutes les ressources dont vous avez besoin et en dotant l’équipe du projet d’un espace de collaboration. À chaque canal créé avec Advisor for Teams correspondent un plan du Planificateur étape par étape ainsi que d’autres ressources, comme une enquête utilisateurs Forms qui peut être utilisée tout au long de votre déploiement. Vous pouvez à tout moment revenir en arrière et examiner l’évaluation de la préparation du client ou ajouter d’autres plans de charge de travail à partir du Centre d’administration Teams. 
> 
>**Appel à l’action** 
>- Si vous débutez avec Teams ou le Planificateur, consultez la [visite guidée Teams](https://teamsdemo.office.com/) et regardez les [vidéos de démarrage rapide du Planificateur](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 
>- Retrouvez l’équipe déploiement dans Teams. Sélectionnez le canal de votre charge de travail (par exemple, Conversations, équipes, canaux et applications), puis sélectionnez l’onglet **Planificateur** pour commencer.
> 
>Pour en savoir plus sur Advisor for Teams, consultez [Utiliser Advisor for Teams pour déployer Microsoft Teams](use-advisor-teams-roll-out.md).
>
> [!IMPORTANT]
> Le bot Advisor for Teams sert uniquement à envoyer un message de bienvenue à votre équipe déploiement. Il ne recueille pas de données.

> [!IMPORTANT]
> Le bot Advisor for Teams est activé par défaut. Ne le désactivez pas si vous utilisez ou envisagez d’utiliser Advisor for Teams.


## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quelles sont les conditions d’octroi de licences pour Advisor for Teams ?
Il n’existe pas de conditions d’octroi de licences particulières, outre la nécessité de disposer d’une licence Teams.

### <a name="can-i-delete-the-deployment-team"></a>Puis-je supprimer l’équipe déploiement ?
Une fois que votre équipe déploiement a été créée par Advisor for Teams, vous pouvez la gérer comme n’importe quelle autre équipe (et donc la supprimer). Notez cependant que si vous ne supprimez pas l’équipe à partir du Centre d’administration Teams, l’équipe sera présentée comme existante.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Puis-je ajouter ou supprimer des canaux dans l’équipe déploiement ?
Oui. Une fois l’équipe déploiement créée, vous pouvez gérer les canaux comme n’importe quelle autre équipe.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Puis-je ajouter ou supprimer des membres de l’équipe du projet dans l’équipe déploiement ?
Oui. Une fois l’équipe déploiement créée, vous pouvez la gérer comme n’importe quelle autre équipe.

### <a name="can-i-modify-the-planner-plans"></a>Puis-je modifier les plans du Planificateur ?
Oui. Une fois que votre équipe déploiement a été créée par Advisor for Teams, vous devez mettre à jour le plan du Planificateur de façon à optimiser le déploiement de Teams. Vous pouvez tout modifier (compartiments, tâches, détails des tâches) comme n’importe quel autre plan du Planificateur.


### <a name="can-i-modify-the-forms-survey"></a>Puis-je modifier l’enquête Forms ?
Oui, après création de votre équipe déploiement par Advisor for Teams, vous pouvez modifier l’enquête Forms selon vos besoins.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quelles informations Advisor for Teams recueille-t-il sur mon organisation ?
Advisor for Teams vous demande l’autorisation de recueillir des données autres que des informations d’identification d’utilisateur final. Les informations recueillies se présentent sous forme de données de télémétrie qui permettent à Microsoft de déterminer la contribution d’Advisor for Teams au succès de ses clients ainsi que les points susceptibles d’être améliorés. Ces mêmes données servent à identifier les possibilités pour Microsoft de collaborer de manière proactive avec votre organisation pour faciliter le déploiement.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Puis-je utiliser Advisor for Teams avec FastTrack ?
Oui, FastTrack met à profit Advisor for Teams pour tous les clients désireux de déployer Teams. Ils peuvent vous aider dans le cadre de la configuration initiale de votre équipe déploiement avec Advisor for Teams (si nécessaire) et offrent un support à la demande sur des questions spécifiques pendant le déploiement de Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Puis-je utiliser Advisor for Teams avec un partenaire ?
Oui, vous pouvez utiliser Advisor for Teams même si vous déployez Teams avec le concours d’un partenaire de déploiement. Si votre partenaire est un fournisseur de solutions cloud et gère votre client en votre nom, il peut utiliser Advisor for Teams pour créer votre équipe déploiement et vous aider à exécuter le projet total. De plus, vous pouvez collaborer avec n’importe quel partenaire et ajouter des personnes à votre équipe déploiement en tant qu’invités, ce qui leur permettra de participer en tant que membre à part entière de l’équipe du projet.

### <a name="how-do-i-use-planner"></a>Comment utiliser le Planificateur ?
Consultez l’[aide du Planificateur Microsoft](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) et les [vidéos de démarrage rapide du Planificateur](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 

### <a name="how-do-i-use-forms"></a>Comment utiliser Forms ?
Accédez au [Centre d’aide de Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Voir aussi

[Comment déployer Teams](How-to-roll-out-teams.md)
