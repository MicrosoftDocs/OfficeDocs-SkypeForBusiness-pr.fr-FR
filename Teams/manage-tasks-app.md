---
title: Gérer l’application Tasks pour votre organisation dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
audience: admin
description: Découvrez comment gérer l’application Tasks pour les utilisateurs de votre organisation.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.openlocfilehash: 74b67a71f8b93f5f0ed898ef186beede056ec31a
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047114"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Tasks pour votre organisation dans Microsoft Teams

## <a name="overview-of-tasks"></a>Présentation de Tasks

L’application Tasks apporte une expérience de gestion des tâches pertinente à Microsoft Teams, en intégrant les tâches individuelles optimisées par [Microsoft To Do](https://todo.microsoft.com/tasks/) et les tâches d’une équipe optimisées par le Planificateur dans un emplacement unique. Les utilisateurs peuvent accéder à l’application Tasks sur le côté gauche de Teams et à un onglet Tasks dans un canal au sein des équipes individuelles. Avec **Mes tâches** et **plans partagés**, les utilisateurs peuvent afficher et gérer toutes leurs tâches individuelles et d’équipe et hiérarchiser leur travail. Tasks est disponible dans les clients pour ordinateur de bureau, les clients web et les clients mobiles Teams.

> [!NOTE]
> Pendant le déploiement de l’expérience Tasks sur les clients Teams pour ordinateur de bureau, l’application sera initialement nommée **Planificateur**. Le nom sera ensuite temporairement remplacé par **Tasks par le Planificateur et To Do**, et plus tard, il sera renommé en **Tasks**. Sur les clients mobiles Teams, l’application sera toujours nommée **Tasks**. Une fois l’expérience pour ordinateur de bureau disponible, un court délai peut exister avant que l’expérience mobile soit disponible.

:::image type="content" source="media/manage-tasks-app-tasks.png" alt-text="Capture d’écran de l’affichage liste des tâches." lightbox="media/manage-tasks-app-tasks.png":::

Pour les organisations qui souhaitent simplifier la gestion des tâches pour les travailleurs de première ligne, Tasks comprend également des fonctionnalités qui vous permettent de cibler, publier et suivre les tâches de vos employés de première ligne. Par exemple, les dirigeants d’entreprise et les responsables régionaux peuvent créer et publier des listes de tâches ciblées sur des emplacements pertinents, tels que des magasins de détail spécifiques, et suivre les progrès grâce à des rapports en temps réel. Les N+1 peuvent attribuer des tâches à leur personnel et diriger les activités depuis leur bureau. Les travailleurs de première ligne, eux, disposent d’une liste hiérarchisée des tâches qui leur sont attribuées sur leur mobile ou leur ordinateur de bureau. Pour activer la [publication des tâches](#task-publishing), vous devez d’abord configurer une hiérarchie de ciblage d’équipe pour votre organisation, qui définit la manière dont toutes les équipes dans la hiérarchie sont liées entre elles.

## <a name="what-you-need-to-know-about-tasks"></a>Ce que vous devez savoir sur Tasks

Tasks est disponible sous forme d’application et sous forme d’onglet dans un canal. L’application affiche les tâches individuelles To Do et les tâches d’équipe du Planificateur. L’onglet affiche uniquement les tâches de l’équipe.

Avec Tasks, les utilisateurs bénéficient d’une expérience web, mobile et pour ordinateur de bureau. Si Tasks est installé sur le client Teams pour ordinateur de bureau, les utilisateurs le verront également sur leurs clients Teams web et mobiles. L’exception est les invités. Il est important de savoir que les invités ne peuvent accéder aux tâches qu’avec l’application, à partir du client mobile Teams. Les invités verront les onglets Tasks sur les clients Teams web et pour ordinateur de bureau.

L’espace **Mes tâches** affiche les tâches individuelles d’un utilisateur. L’espace **Plans partagés** affiche les tâches sur lesquelles toute l’équipe travaille et inclut toute liste de tâches ajoutée en tant qu’onglet Tasks à un canal. Notez les relations suivantes entre les tâches dans Tasks, To Do et Planner :

- Les listes de tâches créées par un utilisateur dans l’application Tasks apparaîtront également dans les clients To Do pour cet utilisateur. De même, les listes de tâches créées par un utilisateur dans To Do apparaîtront dans **Mes tâches** dans Tasks pour cet utilisateur. Il en va de même pour les tâches individuelles.

- Les onglets Tasks ajoutés à un canal apparaissent également dans les clients du Planificateur. Lorsqu’un utilisateur crée un plan dans le Planificateur, le plan n’apparaîtra pas dans l’application Tasks ou Planificateur, sauf s’il est ajouté en tant qu’onglet à un canal. Lorsqu’un utilisateur ajoute un nouvel onglet Tasks, il peut créer une nouvelle liste ou un nouveau plan ou en choisir un existant.

## <a name="set-up-tasks"></a>Configurer Tasks

> [!IMPORTANT]
> Les paramètres et les stratégies que vous avez configurés pour le Planificateur s’appliqueront également à Tasks.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Activer ou désactiver Tasks dans votre organisation

Tasks est activé par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **Applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, effectuez l’une des actions suivantes :

    - Pour désactiver Tasks pour votre organisation, recherchez l’application Tasks, sélectionnez-la, puis cliquez sur **Bloquer**.
    - Pour activer les Tasks pour votre organisation, recherchez l’application Tasks, sélectionnez-la, puis cliquez sur **Autoriser**.

> [!NOTE]
> Si vous ne trouvez pas l’application Tasks, recherchez les noms présentés dans la première remarque de cet article. La modification du nom de l’application n’a peut-être pas encore été effectuée.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Activer ou désactiver les Tasks pour des utilisateurs spécifiques de votre organisation

To allow or block specific users in your organization from using Tasks, make sure Tasks is turned on for your organization on the [Manage apps](manage-apps.md) page, and then create a custom app permission policy and assign it to those users. To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).

### <a name="pin-tasks-to-teams"></a>Épingler des tâches à Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-tasks-and-other-apps-to-teams"></a>Utiliser l’expérience d’application de première ligne personnalisée pour épingler Tasks et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent Tasks, Walkie Talkie, Shifts et Approvals. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prêt à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre de l’application , la barre située sur le côté du client de bureau Teams et en bas des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Personnaliser les applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Utiliser une stratégie de configuration d’application pour épingler Tasks dans Teams

Les stratégies d’installation d’application vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs dans vos utilisateurs.

To pin the Tasks app for your users, you can edit the global (Org-wide default) policy or create and assign a custom app setup policy. To learn more, see [Manage app setup policies in Teams](teams-app-setup-policies.md).

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>L’espace Mes tâches d’un utilisateur est visible si l’utilisateur dispose d’une licence pour Exchange Online

Si vous ne souhaitez pas qu’un utilisateur voie l’espace **Mes tâches**, vous pouvez le masquer. Pour masquer **Mes tâches**, [supprimer la licence Exchange Online de l’utilisateur](/microsoft-365/admin/manage/remove-licenses-from-users). Il est important de savoir qu’après la suppression de la licence Exchange Online, l’utilisateur n’a plus accès à sa boîte aux lettres.  Les données de la boîte aux lettres sont conservées pendant 30 jours, après quoi les données seront supprimées et ne pourront pas être récupérées à moins que la boîte aux lettres ne soit placée en [Conservation inaltérable ou en Conservation pour litige](/exchange/security-and-compliance/in-place-and-litigation-holds).

Nous vous déconseillons de supprimer une licence Exchange Online pour les travailleurs de l’information, mais dans certains scénarios, vous pouvez masquer **Mes tâches** de cette façon, par exemple pour les employés de première ligne qui ne dépendent pas de la messagerie.

## <a name="task-publishing"></a>Publication de tâches

Avec la publication de tâches, votre organisation peut publier des listes de tâches ciblées sur des emplacements spécifiques (des équipes) au sein de votre organisation pour définir et partager un programme de travail à réaliser à ces emplacements.

- Les membres de l’équipe de publication, comme les dirigeants d’entreprise ou les responsables régionaux, peuvent créer des listes de tâches et les publier dans des équipes spécifiques.

    :::image type="content" source="media/manage-tasks-app-publish.png" alt-text="Capture d’écran de la publication de tâches." lightbox="media/manage-tasks-app-publish.png":::
- Les N+1 des équipes destinataires peuvent consulter les listes de tâches publiées et attribuer des tâches individuelles aux membres de l’équipe.
    :::image type="content" source="media/manage-tasks-app-assign.png" alt-text="Capture d’écran de l’attribution d’une tâche." lightbox="media/manage-tasks-app-assign.png":::
- Les travailleurs de première ligne ont une expérience mobile simple pour voir les tâches qui leur sont assignées. Ils peuvent joindre des photos pour montrer leur travail le cas échéant et marquer leurs tâches comme terminées.
- Les éditeurs et les N+1 peuvent afficher des rapports pour voir l’état d’affectation et d’achèvement des tâches à chaque niveau, y compris par emplacement (équipe), liste de tâches et tâche individuelle.
    :::image type="content" source="media/manage-tasks-app-reporting.png" alt-text="Capture d’écran des tâches publiées." lightbox="media/manage-tasks-app-reporting.png":::

Les utilisateurs créent, gèrent et publient des listes de tâches dans l’onglet **Listes publiées** de l’application Tasks. Cet onglet ne s’affiche pour un utilisateur que si votre organisation [a configuré une hiérarchie de ciblage d’équipe](#set-up-your-team-targeting-hierarchy) et que l’utilisateur fait partie d’une équipe incluse dans la hiérarchie. La hiérarchie détermine si l’utilisateur peut publier ou recevoir des listes de tâches et afficher des rapports pour les listes reçues.

### <a name="example-scenario"></a>Exemple de scénario

Voici un exemple du fonctionnement de la publication de tâches.

Contoso lance une nouvelle promotion de plats à emporter et de livraison. Pour maintenir une expérience de marque cohérente, ils doivent coordonner l’exécution cohérente du déploiement dans plus de 300 magasins.

L’équipe marketing partage les détails de la promotion et la liste des tâches correspondante avec le directeur des communications commerciales. Le Gestionnaire de communications au détail, qui garde le contrôle des magasins, passe en revue les informations. Ensuite, ils créent une liste de tâches pour la promotion et une tâche pour chaque unité de travail que les magasins concernés doivent effectuer. Une fois la liste des tâches terminée, ils doivent sélectionner les magasins qui doivent terminer le travail. Dans ce cas, la promotion ne s’applique qu’aux magasins aux États-Unis qui ont un restaurant à l’intérieur du magasin. Dans Tâches, ils filtrent la liste des magasins en fonction de l’attribut de restaurant dans le magasin, sélectionnent les emplacements États-Unis correspondants dans la hiérarchie, puis publient la liste des tâches dans ces magasins.

Les responsables de magasin de chaque site reçoivent une copie des tâches publiées et attribuent ces tâches aux membres de leur équipe. Les responsables peuvent utiliser l’expérience Tasks pour appréhender tout le travail requis dans leur magasin. Ils peuvent également utiliser les filtres disponibles pour se concentrer sur un ensemble de travaux spécifique, comme le travail devant être effectué aujourd’hui ou le travail dans un domaine particulier.

Les employés de première ligne de chaque magasin disposent désormais d’une liste hiérarchisée de leur travail dans Tasks sur leur appareil mobile. Lorsqu’ils terminent une tâche, ils la marquent comme terminée. Ils peuvent même choisir de charger et d’attacher une photo à la tâche pour montrer leur travail.

Le siège social de Contoso et les responsables intermédiaires peuvent afficher des rapports pour consulter le statut d’affectation et d’achèvement des tâches dans chaque magasin et entre les magasins. Ils peuvent également explorer une tâche spécifique pour consulter son état dans différents magasins. À mesure que la date de lancement approche, ils peuvent repérer les anomalies et se renseigner auprès de leurs équipes au besoin. Cette visibilité permet à Contoso d’améliorer l’efficacité du déploiement et de fournir une expérience plus cohérente dans ses magasins.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurer la hiérarchie de ciblage de votre équipe

Pour activer la publication de tâches dans votre organisation, vous devez d’abord configurer votre schéma de ciblage d’équipe dans un fichier au format .CSV. Le schéma définit la façon dont toutes les équipes de votre hiérarchie sont liées les unes aux autres et définit également les attributs qui peuvent être utilisés pour filtrer et sélectionner des équipes. Après avoir créé le schéma, téléchargez-le dans Teams pour l’appliquer à votre organisation. Les membres de l’équipe de publication, tels que le directeur des communications commerciales dans l’exemple de scénario, peuvent ensuite filtrer les équipes par hiérarchie, attributs ou une combinaison des deux pour sélectionner les équipes appropriées devant recevoir les listes de tâches, puis publier les listes de tâches dans ces équipes.

Pour savoir comment configurer la hiérarchie de ciblage de votre équipe, consultez l’article [Configurer la hiérarchie de ciblage de votre équipe](set-up-your-team-hierarchy.md).

## <a name="power-automate-and-graph-api"></a>API Power Automate et Graph

Tasks supports Power Automate for To Do and Graph APIs for Planner. To learn more, see:

- [Présentation de l’API des tâches et des plans du Planificateur](/graph/planner-concept-overview)
- [Utiliser Microsoft To Do avec Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
