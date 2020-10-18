---
title: Utiliser Advisor for Teams pour faciliter le déploiement de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: Utilisez Advisor for Teams pour faciliter la planification et l’exécution de votre déploiement de Microsoft Teams.
ms.openlocfilehash: 00ec8303c73df100b93808f5fdc1e775f80ec289
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503421"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Utiliser Advisor for Teams pour faciliter le déploiement de Microsoft Teams

Advisor for Teams vous guide tout au long du processus de déploiement de Microsoft Teams. Il évalue l’environnement de votre organisation Microsoft 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams. Advisor for Teams crée ensuite une équipe Déploiement (dans Teams) avec des canaux pour chaque charge de travail à déployer. Chaque charge de travail de l’équipe Déploiement s’accompagne d’un plan complet du Planificateur qui comprend toutes les tâches de déploiement pour chaque charge de travail.  Ce plan du Planificateur vous permet d’affecter des tâches aux différentes personnes responsables de chaque phase du déploiement, à savoir le responsable du projet, les administrateurs de Teams, les personnes en charge du support technique et votre équipe d’adoption et de préparation des utilisateurs. Chaque tâche de déploiement contient toutes les ressources et tous les conseils dont vous avez besoin pour la mener à bien.

Advisor for Teams fait partie intégrante du [Centre d’administration Teams](https://admin.teams.microsoft.com). Vous aurez besoin d’une licence Microsoft 365 Business Basic au minimum pour profiter de l’intégration d’Advisor pour Teams avec Forms et le Planificateur. Pour commencer à utiliser Advisor for Teams, cliquez sur le bouton **Démarrer** dans le widget **Déploiement de charges de travail Teams** situé dans le tableau de bord. Ou accédez à **Planification** > **Teams Advisor**.

> [!IMPORTANT]
> Advisor for Teams n’est pas disponible pour les déploiements Microsoft 365 Secteur Public (GCC High ou DoD).

Pour une vue d’ensemble guidée de l’expérience Advisor for Teams, consultez la vidéo [déployer & configurer Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) sur les Mécanismes Microsoft.

## <a name="using-advisor-for-teams"></a>Utilisation d’Advisor for Teams

**Les équipes, les formulaires et les licences Planner sont nécessaires pour utiliser Advisor pour Teams.** Cependant, vous n’avez pas besoin d’être administrateur de Teams pour utiliser Advisor for Teams. Toutes les personnes de votre organisation peuvent l’utiliser. Nous avons créé des autorisations spéciales pour permettre aux utilisateurs non administrateurs d’accéder à Advisor for Teams, même si ce conseiller figure dans le Centre d’administration Teams. Vous DEVEZ être un administrateur Teams, un administrateur de service Teams ou un administrateur général pour ouvrir des évaluations de préparation du client (en raison du fait que les rôles spéciaux non administrateurs n’ont pas accès aux API Microsoft Graph sous-jacentes aux évaluations).

> [!IMPORTANT]
> Si **Teams Advisor** n’apparaît pas sous **Planification** dans le centre d’administration Teams, cela signifie que l’utilisateur n’est pas titulaire d’une licence Teams.

À la première utilisation de Advisor for Teams, une équipe déploiement sera créée automatiquement dans Teams. Un canal se crée pour chaque charge de travail sélectionnée.

> [!IMPORTANT]
> Si une équipe de déploiement a déjà été créée et qu’un autre utilisateur tente de la créer, un message d’erreur lui indique de contacter son équipe de support technique. Ceci empêche Teams de divulguer par inadvertance des informations sur l’équipe existante ainsi que ses membres. Demandez au propriétaire de l’équipe de déploiement de vous ajouter, ou contactez le support technique pour obtenir de l’aide.

## <a name="available-advisor-for-teams-plans"></a>Plans Advisor for Teams disponibles

Advisor for Teams fournit actuellement les plans suivants :

1. Conversations, équipes, canaux et applications
    - Évaluation du client
    - Plan du Planificateur, y compris les tâches d’adoption
    - Enquête utilisateur Forms
    - Bot Advisor for Teams
1. Réunions et conférences
    - Évaluation du client
    - Plan du Planificateur, y compris les tâches d’adoption
    - Enquête utilisateur Forms
    - Bot Advisor for Teams
1. Mise à niveau de Skype Entreprise
    - Évaluation du client
    - Plan du Planificateur, y compris les tâches d’adoption
    - Enquête utilisateur Forms
    - Bot Advisor for Teams
    - Conçu pour les clients qui utilisent actuellement Skype Entreprise Online ou des environnements locaux Skype Entreprise, le plan de mise à niveau Skype Entreprise vous aide à éliminer vos activités de mise à niveau. Tirant parti d’un cadre de réussite éprouvé pour l’implémentation des modifications, le plan vous guide tout au long du processus étape par étape, que vous débutiez avec Teams, que vous utilisiez déjà Teams parallèles à Skype Entreprise, ou que vous soyez prêt à procéder à la mise à niveau. Le plan vous permet également de vous connecter à [conseils et pratiques recommandées en ligne](https://aka.ms/SkypeToTeams), [biens téléchargeables](https://aka.ms/UpgradeSuccessKit), [live 1 : nombreux ateliers de planification](https://aka.ms/UpgradeWorkshops)et des ressources supplémentaires pour vous aider.

Nous vous recommandons de commencer par le plan Conversations, équipes, canaux et applications. Une fois que vous avez déployé cette charge de travail, revenez à Advisor for Teams et cliquez sur **Ajouter un canal** pour enchaîner sur la charge de travail suivante.

## <a name="tenant-assessment"></a>Évaluation du client
Chaque plan comprend une évaluation de la préparation du client dont vous pouvez vous servir pour identifier rapidement les aspects de votre environnement pouvant nécessiter des corrections avant de déployer Teams. Les évaluations comportent des conditions préalables et des pratiques recommandées. Chaque test d’évaluation présente une coche verte ou un triangle d’avertissement orange. 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Une coche verte signifie que votre client a réussi un certain test. 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Un triangle d’avertissement orange indique une suggestion de suivi pour déterminer si une action est nécessaire (par exemple, une stratégie d’expiration de groupe Microsoft 365 est recommandée, bien qu’elle ne soit pas obligatoire).

> [!IMPORTANT]
> Lorsqu’un utilisateur doté d’un rôle d’administrateur démarre Advisor for Teams, toutes les évaluations s’exécutent en arrière-plan. Si vous mettez à jour ou corrigez quelque chose, il est possible que cela ne se reflète pas dans vos évaluations pendant 24 heures.

Les sections ci-dessous décrivent chaque évaluation, notamment s’il s’agit d’une condition préalable ou des pratiques recommandées, de la façon dont les vérifications d’évaluation sont effectuées et pourquoi, ainsi que des conseils pour la correction si besoin.

### <a name="assessment-tests-for-all-workloads"></a>Test d’évaluation pour toutes les charges de travail

|Test d’évaluation  |Ce qu’il vous indique  |
|---------|---------|
|Domaine personnalisé configuré     |Si un domaine autre que @onmicrosoft.com est configuré pour votre client (par exemple, @contoso.onmicrosoft.com). Vous pouvez utiliser le domaine @onmicrosoft.com bien sûr, ou configurer un domaine personnalisé de votre choix. Pour en savoir plus, lire [Ajouter un domaine à Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). |
|Licences Teams     |Il s’agit d’une condition préalable : vous **devez avoir** des licences Teams pour déployer Teams. Interroger Microsoft Graph pour déterminer si vous avez des licences Teams (avec au moins une licence disponible à attribuer). Pour plus d’informations, lire [Description du service Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).    |
|Licences Exchange Online     |Si vous disposez d’un abonnement actif avec des licences Exchange Online disponibles. Même si Exchange n’est pas nécessaire pour les fonctionnalités Teams de base, l’intégration avec Exchange offre une expérience Teams optimale. Interroger Microsoft Graph pour analyser les abonnements associés à votre client et vérifier si vous avez des abonnements ayant une licence Exchange Online valide (avec au moins une licence disponible à attribuer). Pour en savoir plus, lire [Interaction de Exchange et Teams](exchange-teams-interact.md).    |
|Licences SharePoint Online     |Si vous disposez d’un abonnement actif avec des licences SharePoint Online disponibles. Nous recommandons un licence SharePoint Online par utilisateur afin de fournir OneDrive Entreprise pour le stockage de fichiers dans des conversations. Interroger Microsoft Graph pour déterminer si vous avez des licences SharePoint Online (avec au moins une licence disponible à attribuer). Pour en savoir plus, voir [Intéraction de SharePoint Online et OneDrive Entreprise avec Teams](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact).    |
|Accès invité activé     |Si l’[accès invité](guest-access.md) est activé. Accès invité vous permet d’inviter des utilisateurs externes à rejoindre vos équipes. Consultez [Collaborer avec des invités au sein d’une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) pour parcourir l’activation de l’accès invité dans Teams. La liste de contrôle inclut les configurations Azure AD requises. |
|Accès externe configuré     |Si l’[accès externe](manage-external-access.md) est activé. Il est activé par défaut et la fédération est ouverte. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Évaluations pour les conversations, équipes, canaux et applications

Outre les [tests d’évaluation de pour toutes les charges de travail](#assessment-tests-for-all-workloads), les évaluations supplémentaires suivantes sont exécutées pour la charge de travail de conversations, d’équipes, de canaux et d’applications :

|Test d’évaluation  |Ce qu’il vous indique  |
|---------|---------|
|Stratégie de nommage de Groupe Microsoft 365 configurée     |Si les standards d’attribution de noms ont été configurés pour les Groupes Microsoft 365. La stratégie de noms de Groupes Microsoft 365 permet à votre organisation d’appliquer une stratégie d’attribution de noms cohérente avec les équipes créées par l’utilisateur et elle s’applique également aux autres charges de travail de groupes (notamment Outlook, SharePoint, Planner et Yammer). Ce test interroge Azure AD via Microsoft Graph pour vérifier l’existence de stratégies d’attribution de nom qui s’appliquent aux Groupes Microsoft 365. Si vous voulez en savoir plus, consultez [Stratégie de noms de groupes](https://docs.microsoft.com/microsoft-365/admin/create-groups/groups-naming-policy).    |
|Stratégie d’Expiration de Groupe Microsoft 365 configurée     |Si une stratégie d’expiration de groupe a été définie pour les Groupes Microsoft 365. Cela permet à votre organisation de supprimer automatiquement des Teams inactives. Cette option est désactivée par défaut. Ce test interroge Azure AD via Microsoft Graph et indique si la valeur a été modifiée par rapport à celle par défaut. Pour en savoir plus, consultez [Stratégie d’Expiration de groupes Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Évaluations pour réunions et conférences

Outre les [Tests d’évaluation pour toutes les charges de travail](#assessment-tests-for-all-workloads), les évaluations supplémentaires suivantes sont exécutées pour les charges de travail relatives à des réunions et à des conférences :

|Test d’évaluation  |Ce qu’il vous indique  |
|---------|---------|
|Licences d’audioconférences    |Si vous disposez d’un abonnement en cours avec des licences d’audioconférence. Il s’agit d’une condition préalable si vous déployez des ponts d’audioconférence. Interroge Microsoft Graph pour déterminer si vous disposez de licences d’audioconférence (avec au moins une licence disponible pour l’attribution). Pour plus d’informations, consultez [Licences de composants additionnels Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).    |
|Licences Stream     |Si vous disposez d’un abonnement actif avec des licences Microsoft Stream. Il s’agit d’une condition préalable si vous voulez activer Enregistrement de la réunion. Interroger Microsoft Graph pour déterminer si vous avez des licences Microsoft Stream (avec au moins une licence disponible à attribuer). Pour plus d’informations sur Stream et son activation, consultez [Enregistrement de réunions Teams sur le cloud](cloud-recording.md).

### <a name="assessments-for-skype-for-business-upgrade"></a>Évaluations pour la mise à niveau de Skype Entreprise
Outre les [Test d’évaluation pour toutes les charges de travail](#assessment-tests-for-all-workloads), la mise à niveau de Skype Entreprise inclut également des évaluations utilisées dans les réunions et le plan de conférence.

### <a name="advisor-for-teams-bot"></a>Bot Advisor for Teams

Une fois l’équipe déploiement créée par Advisor for Teams, le bot Advisor affiche le message suivant sur le canal général :

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

## <a name="frequently-asked-questions"></a>Questions fréquemment posées
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quelles sont les conditions d’octroi de licences pour Advisor for Teams ?
Vous aurez besoin, au minimum, de Microsoft 365 Business Basic pour profiter de l’intégration d’Advisor pour Teams avec Forms et le Planificateur.

### <a name="can-i-delete-the-deployment-team"></a>Puis-je supprimer l’équipe déploiement ?
Une fois que votre équipe déploiement a été créée par Advisor for Teams, vous pouvez la gérer comme n’importe quelle autre équipe (et donc la supprimer). Notez cependant que si vous ne supprimez pas l’équipe à partir du Centre d’administration Teams, l’équipe y sera présentée comme existante.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Puis-je ajouter ou supprimer des canaux dans l’équipe déploiement ?
Oui. Une fois l’équipe déploiement créée, vous pouvez gérer les canaux comme n’importe quelle autre équipe.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Puis-je ajouter ou supprimer des membres de l’équipe du projet dans l’équipe déploiement ?
Oui. Une fois l’équipe déploiement créée, vous pouvez la gérer comme n’importe quelle autre équipe.

### <a name="can-i-modify-the-planner-plans"></a>Puis-je modifier les plans du Planificateur ?
Oui. Une fois que votre équipe déploiement a été créée par Advisor for Teams, vous devez mettre à jour le plan du Planificateur de façon à optimiser le déploiement de Teams. Vous pouvez tout modifier (compartiments, tâches, détails des tâches) comme n’importe quel autre plan du Planificateur.

### <a name="can-i-modify-the-forms-survey"></a>Puis-je modifier l’enquête Forms ?
Oui, après création de votre équipe déploiement par Advisor for Teams, vous pouvez modifier l’enquête Forms selon vos besoins.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>Y a-t-il des différences entre les conseillers pour Teams au sein de CCG ?
Oui, les formulaires d’enquête utilisateur sont créés, mais ne sont pas épinglés dans des canaux de plan, car l’application formulaires Teams n’est pas disponible au sein de GCC actuellement.

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

[Meilleurs pratiques d’organisation d’équipe dans Teams](best-practices-organizing.md)

[Noms de produits et identificateurs de plans de service pour la gestion des licences](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
