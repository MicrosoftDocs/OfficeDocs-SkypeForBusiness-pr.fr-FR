---
title: Utiliser Advisor for Teams pour faciliter le déploiement de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
- m365initiative-deployteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: Utilisez Advisor for Teams pour faciliter la planification et l’exécution de votre déploiement de Microsoft Teams.
ms.openlocfilehash: 68ac2ec927b1790502a8562c848f1e82f8913668
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594446"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Utiliser Advisor for Teams pour faciliter le déploiement de Microsoft Teams

Advisor for Teams vous guide tout au long du processus de déploiement de Microsoft Teams. Il évalue l’environnement de votre organisation Microsoft 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams. Advisor for Teams crée ensuite une équipe Déploiement (dans Teams) avec des canaux pour chaque charge de travail à déployer. Chaque charge de travail de l’équipe Déploiement s’accompagne d’un plan complet du Planificateur qui comprend toutes les tâches de déploiement pour chaque charge de travail.  Ce plan du Planificateur vous permet d’affecter des tâches aux différentes personnes responsables de chaque phase du déploiement, à savoir le responsable du projet, les administrateurs de Teams, les personnes en charge du support technique et votre équipe d’adoption et de préparation des utilisateurs. Chaque tâche de déploiement contient toutes les ressources et tous les conseils dont vous avez besoin pour la mener à bien.

Advisor for Teams fait partie intégrante du [Centre d’administration Teams](https://admin.teams.microsoft.com). Vous aurez besoin d’une licence Microsoft 365 Business Basic au minimum pour profiter de l’intégration d’Advisor pour Teams avec Forms et le Planificateur. Pour commencer à utiliser Advisor for Teams, cliquez sur le bouton **Démarrer** dans le widget **Déploiement de charges de travail Teams** situé dans le tableau de bord. Ou accédez à **Planification** > **Teams Advisor**.

> [!IMPORTANT]
> Advisor for Teams n’est pas disponible pour les déploiements Microsoft 365 Secteur Public (GCC High ou DoD).

Pour une vue d’ensemble guidée de l’expérience Advisor for Teams, consultez la vidéo [déployer & configurer Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) sur les Mécanismes Microsoft.

## <a name="using-advisor-for-teams"></a>Utilisation d’Advisor for Teams

**Les équipes, les formulaires et les licences Planner sont nécessaires pour utiliser Advisor pour Teams.** Cependant, vous n’avez pas besoin d’être administrateur de Teams pour utiliser Advisor for Teams. Toutes les personnes de votre organisation peuvent l’utiliser. Nous avons créé des autorisations spéciales pour permettre aux utilisateurs non administrateurs d’accéder à Advisor for Teams, même si ce conseiller figure dans le Centre d’administration Teams. Vous DEVEZ être un administrateur Teams, un administrateur Teams ou un administrateur général pour ouvrir des évaluations de préparation du client (en raison du fait que les rôles spéciaux non administrateurs n’ont pas accès aux API Microsoft Graph sous-jacentes aux évaluations).

> [!IMPORTANT]
> Si **Teams Advisor** n’apparaît pas sous **Planification** dans le centre d’administration Teams, cela signifie que l’utilisateur n’est pas titulaire d’une licence Teams.

À la première utilisation de Advisor for Teams, une équipe déploiement sera créée automatiquement dans Teams. Un canal se crée pour chaque charge de travail sélectionnée.

> [!IMPORTANT]
> Si une équipe de déploiement a déjà été créée et qu’un autre utilisateur tente de la créer, un message d’erreur lui indique de contacter son équipe de support technique. Ceci empêche Teams de divulguer par inadvertance des informations sur l’équipe existante ainsi que ses membres. Demandez au propriétaire de l’équipe de déploiement de vous ajouter, ou contactez le support technique pour obtenir de l’aide.

## <a name="available-advisor-for-teams-plans"></a>Plans Advisor for Teams disponibles

Advisor for Teams fournit actuellement les plans suivants :

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
    - Conçu pour les clients qui utilisent actuellement Skype Entreprise Online ou des environnements locaux Skype Entreprise, le plan de mise à niveau Skype Entreprise vous aide à éliminer vos activités de mise à niveau. Tirant parti d’un cadre de réussite éprouvé pour l’implémentation des modifications, le plan vous guide tout au long du processus étape par étape, que vous débutiez avec Teams, que vous utilisiez déjà Teams parallèles à Skype Entreprise, ou que vous soyez prêt à procéder à la mise à niveau. Le plan vous permet également de vous connecter à [conseils et pratiques recommandées en ligne](./upgrade-start-here.md), [biens téléchargeables](https://aka.ms/UpgradeSuccessKit), [live 1 : nombreux ateliers de planification](./upgrade-workshops-landing-page.yml)et des ressources supplémentaires pour vous aider.
1. Éducation (visible uniquement pour les organismes éducatifs)
    - Évaluation du client
    - Plan du Planificateur, y compris les tâches d’adoption
    - Enquête utilisateur Forms
    - Bot Advisor for Teams
    - Conçu pour les Organisations d’enseignement, le plan Éducation vous aidera à déployer, adopter et gérer Teams dans votre établissement d’enseignement.

Pour les organisations commerciales, nous vous recommandons de commencer avec le forfait Chat, équipes, canaux et applications. Pour les établissements d'enseignement, nous vous recommandons de commencer par le plan Education. Une fois que vous avez déployé cette charge de travail, revenez à Advisor for Teams et sélectionnez **Ajouter un canal** pour enchaîner sur la charge de travail suivante.



## <a name="tenant-assessment"></a>Évaluation du client

Chaque plan comprend une évaluation de la préparation du client dont vous pouvez vous servir pour identifier rapidement les aspects de votre environnement pouvant nécessiter des corrections avant de déployer Teams. Les évaluations comportent des conditions préalables et des pratiques recommandées. Chaque test d’évaluation présente une coche verte ou un triangle d’avertissement orange.

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Une coche verte signifie que votre client a réussi un certain test.
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Un triangle d’avertissement orange indique une suggestion de suivi pour déterminer si une action est nécessaire (par exemple, une stratégie d’expiration de groupe Microsoft 365 est recommandée, bien qu’elle ne soit pas obligatoire).

> [!IMPORTANT]
> Lorsqu’un utilisateur doté d’un rôle d’administrateur démarre Advisor for Teams, toutes les évaluations s’exécutent en arrière-plan. Si vous mettez à jour ou corrigez quelque chose, il est possible que cela ne se reflète pas dans vos évaluations pendant 24 heures.

Les sections ci-dessous décrivent chaque évaluation, notamment s’il s’agit d’une condition préalable ou des pratiques recommandées, de la façon dont les vérifications d’évaluation sont effectuées et pourquoi, ainsi que des conseils pour la correction si besoin.

### <a name="assessment-tests-for-all-workloads"></a>Test d’évaluation pour toutes les charges de travail

|Test d’évaluation  |Ce qu’il vous indique  |
|---------|---------|
|Domaine personnalisé configuré     |Si un domaine autre que @onmicrosoft.com est configuré pour votre client (par exemple, @contoso.onmicrosoft.com). Vous pouvez utiliser le domaine @onmicrosoft.com bien sûr, ou configurer un domaine personnalisé de votre choix. Pour en savoir plus, lire [Ajouter un domaine à Microsoft 365](/microsoft-365/admin/setup/add-domain). |
|Licences Teams     |Il s’agit d’une condition préalable : vous **devez avoir** des licences Teams pour déployer Teams. Interroger Microsoft Graph pour déterminer si vous avez des licences Teams (avec au moins une licence disponible à attribuer). Pour plus d’informations, lire [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).    |
|Licences Exchange Online     |Si vous disposez d’un abonnement actif avec des licences Exchange Online disponibles. Même si Exchange n’est pas nécessaire pour les fonctionnalités Teams de base, l’intégration avec Exchange offre une expérience Teams optimale. Interroger Microsoft Graph pour analyser les abonnements associés à votre client et vérifier si vous avez des abonnements ayant une licence Exchange Online valide (avec au moins une licence disponible à attribuer). Pour en savoir plus, lire [Interaction de Exchange et Teams](exchange-teams-interact.md).    |
|Licences SharePoint Online     |Si vous disposez d’un abonnement actif avec des licences SharePoint Online disponibles. Nous recommandons un licence SharePoint Online par utilisateur afin de fournir OneDrive Entreprise pour le stockage de fichiers dans des conversations. Interroger Microsoft Graph pour déterminer si vous avez des licences SharePoint Online (avec au moins une licence disponible à attribuer). Pour en savoir plus, voir [Intéraction de SharePoint Online et OneDrive Entreprise avec Teams](./sharepoint-onedrive-interact.md).    |
|Accès invité activé     |Si l’[accès invité](guest-access.md) est activé. Accès invité vous permet d’inviter des utilisateurs externes à rejoindre vos équipes. Consultez [Collaborer avec des invités au sein d’une équipe](/microsoft-365/solutions/collaborate-as-team) pour parcourir l’activation de l’accès invité dans Teams. La liste de contrôle inclut les configurations Azure AD requises. |
|Accès externe configuré     |Si l’[accès externe](manage-external-access.md) est activé. Il est activé par défaut et la fédération est ouverte. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Évaluations pour les conversations, équipes, canaux et applications

Outre les [tests d’évaluation de pour toutes les charges de travail](#assessment-tests-for-all-workloads), les évaluations supplémentaires suivantes sont exécutées pour la charge de travail de conversations, d’équipes, de canaux et d’applications :

|Test d’évaluation  |Ce qu’il vous indique  |
|---------|---------|
|Stratégie de nommage de Groupe Microsoft 365 configurée     |Si les standards d’attribution de noms ont été configurés pour les Groupes Microsoft 365. La stratégie de noms de Groupes Microsoft 365 permet à votre organisation d’appliquer une stratégie d’attribution de noms cohérente avec les équipes créées par l’utilisateur et elle s’applique également aux autres charges de travail de groupes (notamment Outlook, SharePoint, Planner et Yammer). Ce test interroge Azure AD via Microsoft Graph pour vérifier l’existence de stratégies d’attribution de nom qui s’appliquent aux Groupes Microsoft 365. Si vous voulez en savoir plus, consultez [Stratégie de noms de groupes](/microsoft-365/admin/create-groups/groups-naming-policy).    |
|Stratégie d’Expiration de Groupe Microsoft 365 configurée     |Si une stratégie d’expiration de groupe a été définie pour les Groupes Microsoft 365. Cela permet à votre organisation de supprimer automatiquement des Teams inactives. Cette option est désactivée par défaut. Ce test interroge Azure AD via Microsoft Graph et indique si la valeur a été modifiée par rapport à celle par défaut. Pour en savoir plus, consultez [Stratégie d’Expiration de groupes Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Évaluations pour réunions et conférences

Outre les [Tests d’évaluation pour toutes les charges de travail](#assessment-tests-for-all-workloads), les évaluations supplémentaires suivantes sont exécutées pour les charges de travail relatives à des réunions et à des conférences :

|Test d’évaluation  |Ce qu’il vous indique  |
|---------|---------|
|Licences d’audioconférences    |Si vous disposez d’un abonnement en cours avec des licences d’audioconférence. Il s’agit d’une condition préalable si vous déployez des ponts d’audioconférence. Interroge Microsoft Graph pour déterminer si vous disposez de licences d’audioconférence (avec au moins une licence disponible pour l’attribution). Pour plus d’informations, consultez [Licences de composants additionnels Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Licences Stream     |Si vous disposez d’un abonnement actif avec des licences Microsoft Stream. Il s’agit d’une condition préalable si vous voulez activer Enregistrement de la réunion. Interroger Microsoft Graph pour déterminer si vous avez des licences Microsoft Stream (avec au moins une licence disponible à attribuer). Pour plus d’informations sur Stream et son activation, consultez [Enregistrement de réunions Teams sur le cloud](cloud-recording.md).

### <a name="assessments-for-skype-for-business-upgrade"></a>Évaluations pour la mise à niveau de Skype Entreprise

Outre les [Test d’évaluation pour toutes les charges de travail](#assessment-tests-for-all-workloads), la mise à niveau de Skype Entreprise inclut également des évaluations utilisées dans les réunions et le plan de conférence.

### <a name="advisor-for-teams-bot"></a>Bot Advisor for Teams

Une fois l’équipe déploiement créée par Advisor for Teams, le bot Advisor affiche le message suivant sur le canal général :

>**Bienvenue dans votre équipe déploiement pour Microsoft Teams !**
>  
>La finalité de cette équipe est de vous accompagner tout au long du déploiement de Teams dans votre organisation en mettant à votre disposition toutes les ressources dont vous avez besoin et en dotant l’équipe du projet d’un espace de collaboration. À chaque canal créé avec Advisor for Teams correspondent un plan du Planificateur étape par étape ainsi que d’autres ressources, comme une enquête utilisateurs Forms qui peut être utilisée tout au long de votre déploiement. Vous pouvez à tout moment revenir en arrière et examiner l’évaluation de la préparation du client ou ajouter d’autres plans de charge de travail à partir du Centre d’administration Teams.
>
>**Appel à l’action**
>
>- Si vous débutez avec Teams ou le Planificateur, consultez la [visite guidée Teams](https://teamsdemo.office.com/) et regardez les [vidéos de démarrage rapide du Planificateur](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).
>- Retrouvez l’équipe déploiement dans Teams. Sélectionnez le canal de votre charge de travail (par exemple, Conversations, équipes, canaux et applications), puis sélectionnez l’onglet **Planificateur** pour commencer.
>
>Pour en savoir plus sur Advisor for Teams, consultez [Utiliser Advisor for Teams pour déployer Microsoft Teams](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> Le bot Advisor for Teams sert uniquement à envoyer un message de bienvenue à votre équipe déploiement. Il ne collecte pas de données.

> [!IMPORTANT]
> Le bot Advisor for Teams est activé par défaut. Ne le désactivez pas si vous utilisez ou envisagez d’utiliser Advisor for Teams.

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>Conseiller pour les parcours d’apprentissage Teams et Microsoft 365

[Les parcours d’apprentissage de Microsoft 365](/office365/customlearning/) est une solution d’apprentissage à la demande que vous pouvez personnaliser pour former vos utilisateurs, et améliorer l’utilisation et l’adoption des équipes au sein de votre organisation. Utilisez les parcours d’apprentissage avec conseiller pour Teams afin de permettre à vos utilisateurs d’être rapidement opérationnels et de stimuler l’adoption.

La fonctionnalité parcours d’apprentissage vous permet de créer un modèle de site SharePoint Online et de créer facilement un site de formation pour vos utilisateurs. Vous pouvez personnaliser le portail d’apprentissage sur les parcours d’apprentissage pour y inclure une formation et du contenu de support propre aux besoins de vos utilisateurs. Utilisez les playlists Teams à partir du catalogue Microsoft Online et ajoutez les vôtres.

Vous pouvez créer un site de formation dans les parcours d’apprentissage, puis l’ajouter en tant qu’onglet à un canal en équipe pour permettre aux utilisateurs d’y accéder rapidement et facilement.

Par exemple, utilisez le conseiller pour Teams avec les parcours d’apprentissage pour former votre support technique et vos champions, puis laissez les parcours d’apprentissage prendre en charge la formation de vos utilisateurs finaux. Créez un site d'apprentissage pour aider votre service d'assistance et les champions des équipes, puis ajoutez-le sous forme d'onglet à chaque canal de charge de travail que vous déployez. Votre service d'assistance et vos champions peuvent ensuite créer une page d'assistance sur le portail de formation des parcours d'apprentissage avec des liens et des listes de lecture personnalisées pour aider vos utilisateurs dans Teams. Cette page de support peut être ajoutée à un canal de toute équipe pour former vos utilisateurs finaux.

Voici une vue d’ensemble de la façon dont vous pouvez utiliser le conseiller pour Teams avec les parcours d’apprentissage.

### <a name="get-started-in-learning-pathways"></a>Prise en main des parcours d’apprentissage

Pour commencer à utiliser les parcours d’apprentissage, consultez [Prise en main des parcours d’apprentissage](/office365/customlearning/).

Pour configurer une nouvelle solution de parcours d’apprentissage dans votre environnement, consultez [Configurer une nouvelle solution de parcours d’apprentissage](/office365/customlearning/custom_provision).

### <a name="create-a-learning-plan"></a>Créer un plan d’apprentissage

#### <a name="plan-your-learning-content"></a>Planifier le contenu d’apprentissage

Avant de créer votre site dans les parours d’apprentissage, prenez le temps de passer en revue et de collecter les ressources et les fonctionnalités de formation à votre disposition. Avec les parcours d’apprentissage, vous pouvez utiliser le contenu de la page de formation Microsoft 365 et ajouter du contenu que vous créez pour adapter votre site à vos besoins uniques.

Pour plus d’informations, consultez [Planifier le contenu de vos parcours d’apprentissage](/office365/customlearning/custom_plancontent) et [Ressources pour la prise en charge de vos employés travaillant à distance](/office365/customlearning/custom_plancontent_remoteresources).

#### <a name="explore-teams-content-in-learning-pathways"></a>Explorer le contenu Teams dans les parcours d’apprentissage

Les parcours d'apprentissage fournissent un site SharePoint avec un composant WebPart qui est connectée à un catalogue en ligne. La page formation Microsoft 365, qui héberge le composant WebPart, présente toutes les formations disponibles dans les parcours d’apprentissage. Jetez un coup d’œil pour découvrir les fonctionnalités disponibles et l’organisation du contenu.

[Accédez à votre site de parcours d’apprentissage](/office365/customlearning/custom_goto), sélectionnez **Formation Microsoft 365**, puis **Microsoft Teams** pour afficher toutes les playlists de formation Teams dans le catalogue en ligne. Sélectionnez une playlist, puis sélectionnez les boutons **Suivant** et **Précédent** pour naviguer dans la playlist. Vous pouvez également cliquer sur la flèche vers le bas pour afficher le contenu de la playlist et accéder à un sujet spécifique.

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>Retrouvez les ressources d’apprentissage Teams au sein de votre organisation

Consultez le contenu d'apprentissage Teams qui est déjà disponible dans votre organisation. Par exemple, vous avez peut-être déjà développé des éléments d’intégration, de formation ou de support personnalisés pour Teams. Vos éléments SharePoint existants peuvent être mixés avec le contenu Microsoft d’une liste de diffusion afin de créer une playlist ciblée pour votre organisation.

#### <a name="build-your-site-in-learning-pathways"></a>Créer votre site dans les parcours d’apprentissage

Le [Centre de réussite d’administration](/office365/customlearning/custom_successcenter) dans les parcours d’apprentissage fournit des conseils et des ressources pour vous aider à planifier et personnaliser les parcours d’apprentissage au sein de votre organisation. Découvrez comment [Personnaliser le site](/office365/customlearning/custom_overview), afficher et masquer du contenu, créer des sélections personnalisées, etc.

Pour accéder au Centre de ressources Success Center, sur la page d’accueil des parcours d’apprentissage, sélectionnez **Centre de ressources Success Center des administrateurs**.

#### <a name="add-your-site-to-teams"></a>Ajouter votre site à Teams

Lorsque votre site est prêt, ajoutez-le à un canal d’équipe pour y accéder rapidement et facilement.

1. Dans Teams, accédez à l’équipe, puis sélectionnez un canal.
2. Dans la partie supérieure de la page canal, sélectionnez **+** (**Ajouter un onglet**).
3. Sélectionnez **Pages SharePoint**, puis sélectionnez **Ajouter une page à partir d’un site SharePoint**.
4. Collez l’URL de votre site de parcours d’apprentissage, puis sélectionnez **Enregistrer**.

Pour plus d’informations, consultez [Ajouter une page ou une liste SharePoint à un canal dans Teams](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)

### <a name="train-your-support-team"></a>Former votre équipe de support

Utilisez les ressources de votre site de parcours d’apprentissage pour intégrer votre support et vos champions à Teams. Utilisez les outils et informations nécessaires pour prendre en charge vos utilisateurs dans Teams.

Pour obtenir des instructions et des ressources sur la préparation de votre support et de vos champions pour Teams, consultez [Former votre organisation](https://adoption.microsoft.com/microsoft-teams/#train-your-org) et [Créer des champions](https://adoption.microsoft.com/microsoft-teams/#build-champions).

En tant que contact pour vos utilisateurs pour les questions de type « Comment faire », votre support et vos champions peuvent utiliser le site des parcours d’apprentissage pour former les utilisateurs et en guise d’alternative à la création de tickets de support. Encouragez votre support et vos champions à [personnaliser votre site de parcours d’apprentissage](/office365/customlearning/) en créant une page de formation et de support, puis [l’ajouter comme onglet à un canal](#add-your-site-to-teams) dans une équipe pour permettre aux utilisateurs d’être autonomes.

### <a name="drive-adoption"></a>Favoriser l’adoption

Une fois que vous avez personnalisé votre site et rassemblé vos plans d’apprentissage, réfléchissez à la façon dont vous allez sensibiliser vos utilisateurs afin de les inciter à utiliser les parcours d’apprentissage pour les apprentissages en cours.

Utilisez vos canaux de communication pour promouvoir le site et le faire connaître. Par exemple, vous pouvez inclure un slogan standard tel que « Consultez notre site de formation et de support pour savoir comment être productif avec Teams » en communication avec vos utilisateurs.

Informez vos utilisateurs en mettant en évidence les façons dont ils peuvent collaborer dans Teams, puis redirigez-les vers le site des parcours d’apprentissage pour découvrir comment faire.

Consultez ces ressources, qui incluent des conseils, des kits d’adoption, des pratiques recommandées, etc., pour vous aider à implémenter un plan de déploiement et d’adoption réussi.  

- [Encourager l’adoption de parcours d’apprentissage](/office365/customlearning/driveadoption)
- [Adopter Teams](adopt-microsoft-teams-landing-page.md)
- [Ressources d’adoption pour Teams](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>Foire aux questions

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quelles sont les conditions d’octroi de licences pour Conseiller pour Teams

Vous aurez besoin, au minimum, de Microsoft 365 Business Basic pour profiter de l’intégration d’Advisor pour Teams avec Forms et le Planificateur.

### <a name="can-i-delete-the-deployment-team"></a>Puis-je supprimer l’équipe de déploiement

Une fois que votre équipe déploiement a été créée par Advisor for Teams, vous pouvez la gérer comme n’importe quelle autre équipe (et donc la supprimer). Notez cependant que si vous ne supprimez pas l’équipe à partir du Centre d’administration Teams, l’équipe y sera présentée comme existante.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Puis-je ajouter ou supprimer des canaux dans l’équipe déploiement

Oui. Une fois l’équipe déploiement créée, vous pouvez gérer les canaux comme n’importe quelle autre équipe.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Puis-je ajouter ou supprimer des membres de l’équipe du projet dans l’équipe déploiement

Oui. Une fois l’équipe déploiement créée, vous pouvez la gérer comme n’importe quelle autre équipe.

### <a name="can-i-modify-the-planner-plans"></a>Puis-je modifier les plans du Planificateur

Oui. Une fois que votre équipe déploiement a été créée par Advisor for Teams, vous devez mettre à jour le plan du Planificateur de façon à optimiser le déploiement de Teams. Vous pouvez tout modifier (compartiments, tâches, détails des tâches) comme n’importe quel autre plan du Planificateur.

### <a name="can-i-modify-the-forms-survey"></a>Puis-je modifier l’enquête Forms

Oui, après création de votre équipe déploiement par Advisor for Teams, vous pouvez modifier l’enquête Forms selon vos besoins.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>Y a-t-il des différences entre les conseillers pour Teams au sein de CCG

Oui, les formulaires d’enquête utilisateur sont créés, mais ne sont pas épinglés dans des canaux de plan, car l’application formulaires Teams n’est pas disponible au sein de GCC actuellement.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quelles informations Advisor for Teams recueille-t-il sur mon organisation

Advisor for Teams vous demande l’autorisation de recueillir des données autres que des informations d’identification d’utilisateur final. Les informations recueillies se présentent sous forme de données de télémétrie qui permettent à Microsoft de déterminer la contribution d’Advisor for Teams au succès de ses clients ainsi que les points susceptibles d’être améliorés. Ces mêmes données servent à identifier les possibilités pour Microsoft de collaborer de manière proactive avec votre organisation pour faciliter le déploiement.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Puis-je utiliser Advisor for Teams avec FastTrack

Oui, FastTrack met à profit Advisor for Teams pour tous les clients désireux de déployer Teams. Ils peuvent vous aider dans le cadre de la configuration initiale de votre équipe déploiement avec Advisor for Teams (si nécessaire) et offrent un support à la demande sur des questions spécifiques pendant le déploiement de Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Puis-je utiliser Advisor for Teams avec un partenaire

Oui, vous pouvez utiliser Advisor for Teams même si vous déployez Teams avec le concours d’un partenaire de déploiement. Si votre partenaire est un fournisseur de solutions cloud et gère votre client en votre nom, il peut utiliser Advisor for Teams pour créer votre équipe déploiement et vous aider à exécuter le projet total. De plus, vous pouvez collaborer avec n’importe quel partenaire et ajouter des personnes à votre équipe déploiement en tant qu’invités, ce qui leur permettra de participer en tant que membre à part entière de l’équipe du projet.

### <a name="how-do-i-use-planner"></a>Comment utiliser le Planificateur

Consultez l’[aide du Planificateur Microsoft](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) et les [vidéos de démarrage rapide du Planificateur](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).

### <a name="how-do-i-use-forms"></a>Comment utiliser Forms

Accédez au [Centre d’aide de Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Voir aussi

[Personnaliser votre conseiller pour Teams](/office365/customlearning/custom_teamsadvisor)

[Comment déployer Teams](./deploy-overview.md)

[Meilleurs pratiques d’organisation d’équipe dans Teams](best-practices-organizing.md)

[Noms de produits et identificateurs de plans de service pour la gestion des licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
